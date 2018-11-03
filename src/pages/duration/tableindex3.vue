<template>
  <div>
    <my-table :col="col"
              :data="data">
    </my-table>
  </div>
</template>

<script>
  import MyTable from './components/myTable'

  export default {
    components: {
      MyTable
    },
    data() {
      return {

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
          {label: '优A',
            children: [
              {prop: 'provinceA', label: '省份'},
              {prop: 'cityA', label: '市区'},
              {prop: 'addressA', label: '地址'}
            ]
          },
          {label: '优B',
            children: [
              {prop: 'provinceB', label: '省份'},
              {prop: 'cityB', label: '市区'},
              {prop: 'addressB', label: '地址'}
            ]
          }
        ],
        data: [
          {
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
          }
        ]
      }
    }
  }
</script>
<style>
</style>
