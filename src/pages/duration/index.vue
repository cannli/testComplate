<template>
  <div>
    <table class="reference">
      <tbody>
      <tr>
        <th>序号</th>
        <th>拖动以调整优先级</th>
      </tr>
      <tr class="content-box">
        <td class="num">Jill</td>
        <td class="content">

          <div class="drag">
            <div class="dragBox" v-for="(item, index) in list" :key="index">
              <draggable
                :list="item.itemObj"
                :options="options"
                :move="getdata"
                class="board-column-content">
                <el-button type="primary" size="medium" v-for="x in item.itemObj" v-show="x.status">{{x.name}}
                </el-button>
              </draggable>
            </div>
            <!--<div class="dragBox">-->
            <!--<draggable-->
            <!--:options="options">-->
            <!--<el-button type="primary" size="medium">主要按钮1</el-button>-->
            <!--<el-button type="success" size="medium">成功按钮1</el-button>-->
            <!--<el-button type="info" size="medium">信息按钮1</el-button>-->
            <!--<el-button type="warning" size="medium">警告按钮1</el-button>-->
            <!--</draggable>-->
            <!--</div>-->
          </div>

          <div>
            {{list}}
          </div>
        </td>
        <!--  <td class="content">

            <div class="drag">
              <div class="dragBox">
                <draggable
                  :options="options"
                  class="board-column-content">
                  <el-button type="primary" size="medium">主要按钮1</el-button>
                  <el-button type="success" size="medium">成功按钮1</el-button>
                  <el-button type="info" size="medium">信息按钮1</el-button>
                  <el-button type="warning" size="medium">警告按钮1</el-button>
                </draggable>
              </div>
              &lt;!&ndash;<div class="dragBox">&ndash;&gt;
              &lt;!&ndash;<draggable&ndash;&gt;
              &lt;!&ndash;:options="options">&ndash;&gt;
              &lt;!&ndash;<el-button type="primary" size="medium">主要按钮1</el-button>&ndash;&gt;
              &lt;!&ndash;<el-button type="success" size="medium">成功按钮1</el-button>&ndash;&gt;
              &lt;!&ndash;<el-button type="info" size="medium">信息按钮1</el-button>&ndash;&gt;
              &lt;!&ndash;<el-button type="warning" size="medium">警告按钮1</el-button>&ndash;&gt;
              &lt;!&ndash;</draggable>&ndash;&gt;
              &lt;!&ndash;</div>&ndash;&gt;
            </div>

            <div>
              {{list}}
            </div>
          </td>-->
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  import draggable from 'vuedraggable'

  export default {
    name: "index",
    components: {
      draggable
    },
    data() {
      return {
        options: {
          group: 'mission',
        },
        list: [
          {
            itemObj: [
              {name: '信托保管费1', id: 1, status: true, type:'A'},
              {name: '信托保管费2', id: 2, status: true, type:'A'},
              {name: '信托保管费3', id: 3, status: true, type:'A'},
              {name: '信托保管费4', id: 4, status: true, type:'A'},
              {name: '信托保管费5', id: 5, status: false, type:'A'}
            ]
          },
          {
            itemObj: [
              {name: '优先C2-利息5', id: 5, status: true, type:'B'},
              {name: '优先C2-利息6', id: 6, status: true, type:'B'},
              {name: '优先C2-利息7', id: 7, status: true, type:'B'},
              {name: '优先C2-利息8', id: 8, status: true, type:'B'},
              {name: '优先C2-利息9', id: 9, status: false, type:'B'}
            ]
          }
        ],
        type:true
      }
    },
    methods: {
      getdata(evt) {
        console.log(evt, 8888888)
          console.log(evt.draggedContext.type,877777777777)
        //  return (evt.draggedContext.element.id== 3)  relatedContext
     //   alert(evt.relatedContext.list[0].type== 'B')
     //   alert(evt.draggedContext.type== 'A')
        if (evt.relatedContext.list[1].type=== 'B' && evt.draggedContext.element.type === 'A') {
        //  alert('不能拖拽')
        //   this.$message({
        //     type: 'info',
        //     message: `不能拖拽`
        //   });
          this.$alert('这是一段内容', '标题名称', {
            confirmButtonText: '确定',
            // callback: action => {
            //   this.$message({
            //     type: 'info',
            //     message: `action: ${ action }`
            //   });
            // }
          });
       //   this.type = false
          return false
        }
     //   return (evt.relatedContext.list[0].type== 'C')
      },
    }
  }
</script>

<style lang="scss" type="text/scss" rel="stylesheet/scss">
  .content-box {
    height: 500px;
    .num {
      width: 100px;
    }
    .content {
      .drag {

        .dragBox {
          height: 50px;
          background: #cccccc;
          line-height: 48px;
          margin-top: 5px;
        }
      }
    }

  }

  table.reference, table.tecspec {
    border-collapse: collapse;
    width: 100%;
    margin-bottom: 4px;
    margin-top: 4px;
  }

  table.reference tr:nth-child(odd) {
    background-color: #f6f4f0;
  }

  table.reference tr:nth-child(even) {
    background-color: #fff;
  }

  table.reference th {
    color: #000;
    background-color: #cccccc;
    border: 1px solid #555;
    font-size: 12px;
    padding: 3px;
    vertical-align: top;
    text-align: center;
  }

  table.reference td {
    line-height: 2em;
    min-width: 24px;
    border: 1px solid #d4d4d4;
    padding: 5px;
    padding-top: 7px;
    padding-bottom: 7px;
    vertical-align: top;
  }

  .board-column-content {
    height: auto;
    overflow: hidden;
    // border: 10px solid transparent;
    min-height: 60px;
    //  display: flex;
    //  justify-content: flex-start;
    flex-direction: column;
    align-items: center;
  }
</style>
