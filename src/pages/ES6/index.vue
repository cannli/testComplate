<template>
  <div>
    <table class="reference">
      <tbody><tr>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Points</th>
      </tr>
      <tr>
        <td>Jill</td>
        <td>Smith</td>
        <td>50</td>
      </tr>
      <tr>
        <td>Eve</td>
        <td>Jackson</td>
        <td>94</td>
      </tr>
      <tr>
        <td>John</td>
        <td>Doe</td>
        <td>80</td>
      </tr>
      <tr>
        <td>Adam</td>
        <td>Johnson</td>
        <td>67</td>
      </tr>
      </tbody></table>
  </div>
</template>

<script>
  export default {
    name: "index",
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
      var nodeList = new Set([...document.querySelectorAll('*')].map(v => v.nodeName))
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
      console.log(Reflect.has(b1, 'name'))
    },
  }
</script>

<style scoped>
  .language-javascript {
    background: #666666;
  }
</style>
