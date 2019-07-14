<template>
  <div>
    <el-tabs type="border-card">
      <el-tab-pane label="正常">
        <table class="reference">
          <tbody>
          <tr>
            <th>序号</th>
            <th>拖动以调整优先级</th>
          </tr>
          <tr class="content-box" v-for="(item, index) in list" :key="index" v-if="item.itemObj.length>0">
            <td class="num">{{index+1}}</td>
            <td class="content">

              <div class="drag">
               <!-- <div class="dragBox" v-for="(item, index) in list" :key="index">-->
                 <!-- <draggable
                    :list="item.itemObj"
                    :options="options"
                    :move="getdata"
                    class="board-column-content">
                    <el-button type="primary" size="medium" v-for="x in item.itemObj" v-show="x.status">{{x.name}}
                    </el-button>
                  </draggable>-->
                </div>
            <!--  </div>-->

          <!--    <div>
                {{list}}
              </div>-->
            </td>
          </tr>
          </tbody>
        </table>
      </el-tab-pane>
      <el-tab-pane label="违约">违约</el-tab-pane>
      <el-tab-pane label="角色管理">角色管理</el-tab-pane>
      <el-tab-pane label="定时任务补偿">定时任务补偿</el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
  import draggable from 'vuedraggable'

  export default {
    name: "index",
    components: {draggable},
    data() {
      return {
        options: {
          group: 'mission',
        },
        list: [
          {
            itemObj: [
              {name: '信托保管费1', id: 1, status: true, type: 'A'},
              {name: '信托保管费2', id: 2, status: true, type: 'A'},
              {name: '信托保管费3', id: 3, status: true, type: 'A'},
              {name: '信托保管费4', id: 4, status: true, type: 'A'},
              {name: '信托保管费5', id: 5, status: true, type: 'A'}
            ]
          },
          {
            itemObj: [
              {name: '优先C2-利息5', id: 5, status: true, type: 'B'},
              {name: '优先C2-利息6', id: 6, status: true, type: 'B'},
              {name: '优先C2-利息7', id: 7, status: true, type: 'B'},
              {name: '优先C2-利息8', id: 8, status: true, type: 'B'},
              {name: '优先C2-利息9', id: 9, status: true, type: 'B'}
            ]
          }
        ],
      }
    },
    mounted() {
      // 数组解构
      // let [a, b, c] = [1, 2, 3]
      // console.log(a, b, c)
      // 对象解构
      // let {a, b, c} = {a: '22', b:'11', c:'33'}
      //  console.log(a,b,c)
      /* let { log, sin, cos } = Math
       console.log(log,99)*/

      /*  const pipeline = (...funcs) =>
          val => funcs.reduce((a, b) => b(a), val);

        const plus1 = a => a + 1;
        const mult2 = a => a * 2;
        const addThenMult = pipeline(plus1, mult2);

        console.log(addThenMult(5))*/
      // ...扩展符的运用
      /* const [first, ...rest] = [1, 2, 3, 4, 5]
       console.log(...rest)
       let ss = [...'hello']
       console.log(ss)*/
// 获取页面的元素
      /* var nodeList = new Set([...document.querySelectorAll('*')].map(v => v.nodeName))
       console.log(nodeList)
       const a1 = [
         {name: '头前倾', val: 19},
         {name: '头晕', val: 2},
         {name: '头痛', val: 3},
         {name: '耳鸣', val: 10},
         {name: '骨刺', val: 7},
         {name: '腰痛', val: 1},
         {name: '手脚麻', val: 4},
         {name: '腰痛', val: 1}]
       console.log(a1, 'a1')

       for (let x of a1.values()) {
         console.log(x, 'keys222222')
       }

       let aSet = new Set(a1)
       console.log(aSet.keys(), 'a1keys')
       console.log(aSet.values(), 'val')
       // console.log(aSet,'aSet')
       console.log(a1, 'a1')
       // 克隆数组
       const a2 = [...a1]
       a2.push({name: '头晕2', val: 5})
       console.log(a2)

       // （3）与解构赋值结合
       const [a3, ...a4] = a1
       console.log(a3)
       console.log(a4)
       console.log(typeof (a3))
       // es6中解构后的数据类型
       let [name, age, sex] = a1;
       console.log(name, 'name');
       console.log(age, 'age');
       console.log(sex, 'sex');
       console.log(typeof (sex), 'sex')

       //字符串类型
       let [a, b, c] = "这是一个字符串"
       console.log(a)
       console.log(b)
       console.log(c)

       // 获取对象里面的可key 跟 value
       let b1 = {name: 'lican', sex: '男', age: 12}
       console.log(Reflect.has(b1, 'name')) */
    },
    methods:{
      // getdata(evt) {
      //   console.log(evt, 8888888)
      //   console.log(evt.draggedContext.type,877777777777)
      //   //  return (evt.draggedContext.element.id== 3)  relatedContext
      //   //   alert(evt.relatedContext.list[0].type== 'B')
      //   //   alert(evt.draggedContext.type== 'A')
      //   if (evt.relatedContext.list[1].type=== 'B' && evt.draggedContext.element.type === 'A') {
      //     //  alert('不能拖拽')
      //     //   this.$message({
      //     //     type: 'info',
      //     //     message: `不能拖拽`
      //     //   });
      //     this.$alert('这是一段内容', '标题名称', {
      //       confirmButtonText: '确定',
      //       // callback: action => {
      //       //   this.$message({
      //       //     type: 'info',
      //       //     message: `action: ${ action }`
      //       //   });
      //       // }
      //     });
      //     //   this.type = false
      //     return false
      //   }
      //   //   return (evt.relatedContext.list[0].type== 'C')
      // },getdata

      getdata(){}
    }
  }
</script>

<style lang="scss" type="text/scss" rel="stylesheet/scss">
  .content-box {
    height: auto;
    .num {
      width: 100px;
    }
    .content {
      .drag {

        .dragBox {
          min-height: 50px;
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
