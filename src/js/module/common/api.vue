<template>
    <div>
        <div v-if="options">
            <h3 class="pt3">{{name || ''}}Options</h3>
            <table class="table">
                <thead>
                    <tr>
                        <th style="width:100px;">参数</th>
                        <th style="width:600px;">说明</th>
                        <th style="width:100px;">类型</th>
                        <th style="width:100px;">可选值</th>
                        <th style="width:100px;">默认值</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in options">
                        <td>{{item.name}}</td>
                        <td>{{item.desc}}</td>
                        <td>{{item.type}}</td>
                        <td>{{item.default}}</td>
                        <td>{{item.all}}</td>
                    </tr>
                </tbody>
            </table> 
        </div>
        <div v-if="attrs">
            <h3 class="pt3">{{name || ''}} Attributes</h3>
            <table class="table">
                <thead>
                    <tr>
                        <th style="width:100px;">参数</th>
                        <th style="width:600px;">说明</th>
                        <th style="width:100px;">类型</th>
                        <th style="width:100px;">可选值</th>
                        <th style="width:100px;">默认值</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in attrs">
                        <td>{{item.name}}</td>
                        <td>{{item.desc}}</td>
                        <td>{{item.type}}</td>
                        <td>{{item.all}}</td>
                        <td>{{item.default}}</td>
                    </tr>
                </tbody>
            </table> 
        </div>
        <div v-if="events">
            <h3 class="pt3">{{name || ''}} Events</h3>
            <table class="table">
                <thead>
                    <tr>
                        <th>名称</th>
                        <th>说明</th>
                        <th>参数</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in events">
                        <td>{{item.name}}</td>
                        <td>{{item.desc}}</td>
                        <td>{{item.params}}</td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div v-if="slots">
            <h3 class="pt3">{{name || ''}} Slots</h3>
            <table class="table">
                <thead>
                    <tr>
                        <th>名称</th>
                        <th>说明</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in slots">
                        <td>{{item.name}}</td>
                        <td>{{item.desc}}</td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div v-if="methods">
            <h3 class="pt3">{{name || ''}} Methods</h3>
            <table class="table">
                <thead>
                    <tr>
                        <th style="width:100px;">名称</th>
                        <th style="width:600px;">说明</th>
                        <th style="width:100px;">参数</th>
                        <th style="width:100px;">返回值</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in methods">
                        <td>{{item.name}}</td>
                        <td>{{item.desc}}</td>
                        <td>{{item.params}}</td>
                        <td>{{item.rt}}</td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div v-if="texts">
            <h3 class="pt3">{{name || ''}} 文本</h3>
            <p v-if="desc">{{desc}}</p>
            <table class="table">
                <thead>
                    <tr>
                        <th style="width:200px;">名称</th>
                        <th style="width:600px;">说明</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in texts">
                        <td>{{item.name}}</td>
                        <td>{{item.desc}}</td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div v-if="fonts">
            <h3 class="pt3">{{name || ''}} 字体</h3>
            <slot name="desc"></slot>
            <p v-if="desc">{{desc}}</p>
            <table class="table">
                <thead>
                    <tr>
                        <th style="width:200px;">名称</th>
                        <th style="width:600px;">说明</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in fonts">
                        <td v-html="item.name"></td>
                        <td>{{item.desc}}</td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div v-if="interactives">
            <h3 class="pt3">{{name || ''}} 交互</h3>
            <p v-if="desc">{{desc}}</p>
            <table class="table">
                <thead>
                    <tr>
                        <th style="width:200px;">名称</th>
                        <th style="width:600px;">说明</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in interactives">
                        <td>{{item.name}}</td>
                        <td>{{item.desc}}</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {

        };
    },
    props: ['name', 'options', 'attrs', 'events', 'slots', 'methods', 'texts', 'desc', 'fonts', 'interactives']
};
</script>

