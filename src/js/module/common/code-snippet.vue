<template lang="html">
<div>
  <div v-show="isShow">
      <blockquote class="clip-b">
      <a href="javascript:;" class="clip" ref="clipbtn"> 复制代码 </a>
  </blockquote>
  <div class="highlight">
    <pre>
      <code class="html" ref="code"><slot></slot></code>
    </pre>
  </div>
  </div>
  <div @click="isShow=!isShow" class="toggle-btn">{{isShow?'隐藏代码':'显示代码'}}</div> 
</div>
</template>
<script>
export default {
    data(){
        return {
            isShow: false
        };
    },
    mounted() {
        const { hljs, Clipboard } = window;

        hljs.highlightBlock(this.$refs.code);

        const clipboard = new Clipboard(this.$refs.clipbtn, {
            text: () => {
                return $(this.$refs.code).text();
            }
        });

        clipboard.on('success', function(e) {
            new MiniMsg({
                content: '复制成功'
            }).animation();
            e.clearSelection();
        });
    }
};
</script>

<style lang="css">
    .toggle-btn{
        text-align: center;
    color: #5491ee;
    border-top: 1px #eee solid;
    padding: 10px 0;
    cursor: pointer;
    transition: .2s;
    }
    .toggle-btn:hover{
        background-color: #f3f3f3;
    }
</style>
