<template>
  <div class="input-msg mailbox"
       ref="msg"
       contenteditable="plaintext-only"
       @input="changeText"
       @keydown.enter.prevent="enterMsg">{{value}}</div>
</template>

<script>
  export default {
    name: 'editDiv',
    props: {
      value: {
        type: String,
        default: ''
      }
    },
    data() {
      return {
      //  myValue: this.value
      }
    },
    watch: {
      value(newvalue) {
        console.log(newvalue);
        // if (!this.isLocked && !this.innerText) {
        if (!newvalue) {
          // 清空节点内所有html来清空文本
          this.$refs.msg.innerHTML = '';
        } else {
          this.keepLastIndex(this.$refs.msg);
        }
      //  this.myValue = newvalue
      }
    },
    methods: {
      changeText(event) {
        this.$emit('input', this.$el.innerHTML);
      },

      enterMsg(event) {
        this.$emit('send');
      },
      keepLastIndex(obj) {
        if (window.getSelection) {
          //ie11 10 9 ff safari
          obj.focus(); // 解决ff不获取焦点无法定位问题
          var range = window.getSelection(); //创建range
          range.selectAllChildren(obj); //range 选择obj下所有子内容
          range.collapseToEnd(); //光标移至最后
        } else if (document.selection) {
          //ie10 9 8 7 6 5
          var range = document.selection.createRange(); //创建选择对象
          //var range = document.body.createTextRange();
          range.moveToElementText(obj); //range定位到obj
          range.collapse(false); //光标移至最后
          range.select();
        }
      }
    }
  };
</script>

<style scoped>
 /* .input-msg {
    line-height: 17px;
    min-height: 17px;
    border: 0;
    display: block;
    flex: 1;
    width: 0;
    max-height: 57px;
    overflow-y: scroll;
    overflow-x: hidden;
    background-color: #f9f8fa;
    padding: 2px 2px 0 2px;
    user-select: text;
    -webkit-user-modify: read-write-plaintext-only;
  }

  .input-msg:focus {
    border: 0;
    outline: 0;
  }

  .input-msg:empty:before {
    content: '';
  }*/
 .mailbox {
   width: 100%;
   min-height: 60px;
   max-height: 150px;
   overflow: hidden;
   overflow-y: scroll;
   box-sizing: border-box;
   border: 1px solid #dcdfe6;
   line-height: 20px;
   padding: 5px 15px;

   outline: none;
 // border-radius: 2px;
 }

 .mailbox:focus {
   border: 1px solid #409EFF;
 }
</style>
