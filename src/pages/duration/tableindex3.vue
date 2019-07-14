<template>
  <div>
    <my-table :col="col" :data="data"></my-table>
    <titleC title="用Promise.all加载图片"></titleC>
  </div>
</template>

<script>
  import MyTable from './components/myTable'
  import titleC from '@/components/common/components/title.vue'

  export default {
    components: {
      MyTable, titleC
    },
    data() {
      return {
<<<<<<< HEAD
        col: [
          /*{prop: 'num1', label: ''},
          {
            label: '税费',
=======

        /* repayListData : [
           {
             staticRepayRow: [
               {
                 subHierarchyOrder: 2,
                 subHierarchy: "PRIOR_A",
                 principal: "-",
                 interest: "-",
                 coverageRate: "-",
                 itemId: 115,
                 bondName: "4333"
               },
               {
                 subHierarchyOrder: 1,
                 subHierarchy: "CIJI",
                 principal: 23456,
                 interest: 12345,
                 coverageRate: "-",
                 itemId: 116,
                 bondName: "74次级"
               }
             ],
             paymentDay: "2019-03-03"
           },
           {
             staticRepayRow: [
               {
                 subHierarchyOrder: 2,
                 subHierarchy: "PRIOR_A",
                 principal: 45678,
                 interest: 34567,
                 coverageRate: "-",
                 itemId: 115,
                 bondName: "4333"
               },
               {
                 subHierarchyOrder: 1,
                 subHierarchy: "CIJI",
                 principal: "-",
                 interest: "-",
                 coverageRate: "-",
                 itemId: 116,
                 bondName: "74次级"
               }
             ],
             paymentDay: "2019-03-04"
           }
         ],*/

        col: [
          {prop: 'date', label: '日期'},
          {
            label: '优A',
>>>>>>> 12fc93e548f8bf9a792f32c040d85fe8698a576e
            children: [
              {prop: 'num2', label: '税费'},
            ]
          },
          {
<<<<<<< HEAD
            label: '费用',
=======
            label: '优B',
>>>>>>> 12fc93e548f8bf9a792f32c040d85fe8698a576e
            children: [
              {prop: 'num3', label: '托管费'},
              {prop: 'num4', label: '技术服务费'},
              {prop: 'num5', label: '信托费'}
            ]
          },
          {prop: 'num6', label: '加权平均利率'},*/
        ],
        data: [
          /* {
             date: '2016-05-03',

             provinceA: '上海A',
             cityA: '普陀区A',
             addressA: '上海市普陀区金沙江路 1518 弄A',

             provinceB: '上海B',
             cityB: '普陀区B',
             addressB: '上海市普陀区金沙江路 1518 弄B'
           },
           {
             date: '2016-05-02',

             provinceA: '上海A2',
             cityA: '普陀区A2',
             addressA: '上海市普陀区金沙江路 1518 弄A2',

             provinceB: '上海B2',
             cityB: '普陀区B2',
             addressB: '上海市普陀区金沙江路 1518 弄B2'
           }*/
        ],

        aaa: [
          {
            cashFlowTypeName: "税费",
            dataList: [{
              taxFeeType: "VALUE_ADDED_TAX",
              taxFeeName: "税费",
              currentPayAmountSum: 0,
              annualRate: 0.00,
              cashFlowType: "TAX",
              feeId: 104
            }]
          },
          {
            cashFlowTypeName: "费用",
            dataList: [
              {
                taxFeeType: "TECHSUPPORT_CONSULTANT_FEE",
                taxFeeName: "技术服务费",
                currentPayAmountSum: 162955.78,
                annualRate: 0.42,
                cashFlowType: "FEE",
                feeId: 103
              }, {
                taxFeeType: "TRUSTEESHIP_FEE",
                taxFeeName: "托管费",
                currentPayAmountSum: 7132.55,
                annualRate: 0.02,
                cashFlowType: "FEE",
                feeId: 102
              }, {
                taxFeeType: "TURST_MANAGEMENT_FEE",
                taxFeeName: "信托费",
                currentPayAmountSum: 285301.73,
                annualRate: 0.73,
                cashFlowType: "FEE",
                feeId: 101
              }]
          },
          {
            cashFlowTypeName: "加权平均利率",
            dataList: [{
              taxFeeName: "加权平均利率",
              currentPayAmountSum: "-",
              annualRate: 7.56,
              cashFlowType: "加权平均利率"
            }]
          }
        ],
        // 图片数组
        urls: ["https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3293635140,3955114282&fm=26&gp=0.jpg",
          "https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1019333328,1858047370&fm=26&gp=0.jpg"
        ],
        imgArr: undefined

      }
    },
<<<<<<< HEAD
    mounted() {
      console.log(this.aaa[1])
      let val = this.aaa
      let head = [{prop: 'num1', label: ''},]
      let data = [{num1: '金额'}, {num1: '年化%'}]
      let cua = 1
      for (let x in val) {
        head.push({label: val[x].cashFlowTypeName})
        if (val[x].dataList) {
          head[x * 1 + 1].children = []
          let dataList = val[x].dataList
          for (let y in dataList) {
            cua++
            head[x * 1 + 1].children.push(
              {prop: `num${cua}`, label: dataList[y].taxFeeName}
            )
            data[0][`num${cua}`] = dataList[y].currentPayAmountSum
            data[1][`num${cua}`] = dataList[y].annualRate
          }
        }
      }
      alert(cua)
      this.col = head
      this.data = data
      console.log(head, 999999)
=======
    created() {
      //  this.loadAll(this.urls)
    },
    mounted() {
      this.imgFn()
    },
    methods: {
      loadImageAsync(url) {
        return new Promise(function (resolve, reject) {
          const image = new Image();

          image.onload = function () {
            resolve(image);
          };

          image.onerror = function () {
            reject(new Error('Could not load image at ' + url));
          };

          image.src = url;
        });
      },
      // 图片加载promise
      loadImg(url) {
        let img = new Image()
        img.src = url
        return new Promise((resolve, reject) => {
          img.onload = () => {
            resolve(img)
          }
          img.onerror = (e) => {
            reject(e)
          }
        })
      },

      loadAll(arr) {
        let self = this
        let result = []
        arr.forEach(item => {
          let p = self.loadImg(item).then((img) => {
            console.log(img, 'img')
          })
          //存储当前Promise对象
          console.log(p, '存储当前Promise对象')
          result.push(p)
        });
        Promise.all(result).then((res) => {
          //全部完成

          console.log("done")
        }).catch((err) => {
          // 有失败的情况
          console.log(err)
        });
      },

      imgFn() {
      let self = this
        self.loadAll(self.urls).then((res) => {
          self.imgArr = res
          console.log(self.imgArr, 99999)
        }).catch(err => {
          console.log(err)
        })
      }
      // loadAll(urls)

>>>>>>> 12fc93e548f8bf9a792f32c040d85fe8698a576e
    }

  }
</script>
<style>
</style>
