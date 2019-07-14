<!--
butName.length的长度跟heiSty控制组件的高度
iconClass是class控制icon
butShow控制按钮的显示隐藏
-->
<template>
  <div class="ext-sub-title-ant"
       :style="{marginBottom: marginBot + 'px', height: butName.length>0 && !heiSty?'32px':'18px'}">
    <div class="title-box">
      <span class="arr" v-show="arrShow"></span>
      <span class="title" :style="{left: !arrShow && '0'}">{{title}}</span>
      <span class="status"><slot></slot></span>
      <div class="link">
        <a v-show="butShow" @click="butNameFn" :class="classType" class="buttonSty"><i
          :style="{marginRight: !iconClass?'0' : '5px'}" :class="iconClass"></i>{{butName}}</a>
        <slot name="one"></slot>
      </div>
      <slot name="explain"></slot>
    </div>

  </div>
</template>

<script>
  export default {
    components: {},
    props: {
      butShow: {
        type: Boolean,
        default: false
      },
      title: {
        type: String,
        default: ''
      },
      butName: {
        type: String,
        default: ''
      },
      iconClass: {
        type: String,
        default: 'el-icon-plus'
      },
      classType: {
        type: String,
        default: ''
      },
      marginBot: {
        type: Number,
        default: 20
      },
      heiSty: {
        type: Boolean,
        default: false
      },
      arrShow: {
        type: Boolean,
        default: true
      }
    },
    data() {
      return {}
    },
    created() {
    },
    mounted() {
      this.$nextTick(() => {
      })
    },
    beforeUpdate() {
    },
    updated() {
    },
    beforeDestroy() {
    },
    destroyed() {
    },
    computed: {},
    watch: {},
    methods: {
      butNameFn() {
        this.$emit('butNameFn')
      }
    }
  }
</script>

<style scoped lang="scss" type="text/scss" rel="stylesheet/scss">
  .title-box {
    font-size: 16px;
  }

  .but_sty {
    border-radius: 0;
    background: none;
  }

  .buttonSty {
    min-width: 60px;
  }

  .ext-sub-title-ant { /*88888888*/
  margin-top: 20px;
    .title-box {
      box-sizing: border-box;
      width: 100%;
      height: 100%;
      display: inline-block;
      margin-top: 0;
      font-size: 18px;
      border-bottom: none;
      position: relative;
      .arr {
        display: inline-block;
        width: 6px;
        height: 18px;
        background: #00A2FF;
        border-radius: 3px;
        position: absolute;
        top: 50%;
        transform: translate(0, -50%);
      }
      .title {
        color: rgba(0, 0, 0, 0.85);
        font-size: 16px;
        font-weight: bold;
        position: absolute;
        top: 50%;
        left: 12px;
        transform: translate(0, -50%);
      }
      .status {
        /* display: inline-block;
         margin-left: 20px;*/
        position: absolute;
        top: 50%;
        transform: translate(0, -50%);
        left: 120px;
      }

      .link {
        font-size: 14px;
        float: right;
        a {
          display: inline-block;
          box-sizing: border-box;
          padding: 0 10px;
          height: 32px;
          padding: 0 15px;
          border-radius: 2px;
          text-align: center;
          line-height: 32px;
          border: 1px solid #00A2FF;
          font-size: 14px;
        }
        .primary {
          color: #ffffff;
          background: #00A2FF;
        }
        .default {
          color: #00A2FF;
          background: #fff;
        }
      }
      .link:after {
        content: "";
        height: 0;
        line-height: 0;
        display: block;
        visibility: hidden;
        clear: both
      }
    }
  }

</style>
