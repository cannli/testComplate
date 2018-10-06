<template>
  <div>
<<<<<<< HEAD
    <h2>你好ES6</h2>
=======
    <pre onclick="hljs.copyCode(event)"><code class="language-javascript hljs"><ol class="hljs-ln"><li><div
      class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="1"></div></div><div
      class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-built_in">console</span>.log(...[<span
      class="hljs-number">1</span>, <span class="hljs-number">2</span>, <span class="hljs-number">3</span>])</div></div></li><li><div
      class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="2"></div></div><div
      class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">// 1 2 3</span></div></div></li><li><div
      class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="3"></div></div><div
      class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-built_in">console</span>.log(<span
      class="hljs-number">1</span>, ...[<span class="hljs-number">2</span>, <span class="hljs-number">3</span>, <span
      class="hljs-number">4</span>], <span class="hljs-number">5</span>)</div></div></li><li><div
      class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="4"></div></div><div
      class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">// 1 2 3 4 5</span></div></div></li><li><div
      class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="5"></div></div><div
      class="hljs-ln-code"><div class="hljs-ln-line">[...document.querySelectorAll(<span
      class="hljs-string">'div'</span>)]</div></div></li><li><div class="hljs-ln-numbers"><div
      class="hljs-ln-line hljs-ln-n" data-line-number="6"></div></div><div class="hljs-ln-code"><div
      class="hljs-ln-line"><span class="hljs-comment">// [&lt;div&gt;, &lt;div&gt;, &lt;div&gt;]</span></div></div></li></ol></code><div
      class="hljs-button" data-title="复制"></div></pre>

    <el-row :gutter="50">
      <el-col :span="12">
        <div class="a-row">
          <titleText title="es6：...扩展"></titleText>
          <p>1.如果将扩展运算符用于数组赋值，只能放在参数的最后一位，否则会报错。</p>
          <pre style="background: #666666; color: #fffdef"><code class="language-javascript hljs"><ol class="hljs-ln"><li>
            <div
              class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="1"></div></div><div
            class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-keyword">const</span> [...butLast, last] = [<span
            class="hljs-number">1</span>, <span class="hljs-number">2</span>, <span class="hljs-number">3</span>, <span
            class="hljs-number">4</span>, <span class="hljs-number">5</span>];</div></div></li><li><div
            class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="2"></div></div><div
            class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">//  报错</span></div></div></li><li><div
            class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="3"></div></div><div
            class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-keyword">const</span> [first, ...middle, last] = [<span
            class="hljs-number">1</span>, <span class="hljs-number">2</span>, <span class="hljs-number">3</span>, <span
            class="hljs-number">4</span>, <span class="hljs-number">5</span>];</div></div></li><li><div
            class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="4"></div></div><div
            class="hljs-ln-code"><div class="hljs-ln-line"><span
            class="hljs-comment">//  报错</span></div></div></li></ol></code><div class="hljs-button"
                                                                                data-title="复制"></div></pre>
        </div>
        <p>
          2.字符串
          扩展运算符还可以将字符串转为真正的数组。
        </p>
      </el-col>
      <el-col :span="12">
        <titleText title="es6：解构" class="a-row"></titleText>
      </el-col>
    </el-row>
>>>>>>> 227bb5cee4e747450177e7ebe7489520ee1c5527
  </div>
</template>

<script>
<<<<<<< HEAD
  export default {
    name: "index",
    mounted() {
      console.log(22222222)
    }
=======
  import titleText from '@/components/common/components/title.vue'

  export default {
    components: {
      titleText
    },
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
      console.log(a1,'a1')

      for (let x of a1.values()){
        console.log(x,'keys222222')
      }

      let aSet =new Set(a1)
      console.log(aSet.keys(),'a1keys')
      console.log(aSet.values(),'val')
     // console.log(aSet,'aSet')
      console.log(a1,'a1')
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
      let [name,age,sex]=a1;
      console.log(name,'name');
      console.log(age,'age');
      console.log(sex,'sex');
      console.log(typeof (sex),'sex')

      //字符串类型
      let [a,b,c]="这是一个字符串"
      console.log(a)
      console.log(b)
      console.log(c)

      // 获取对象里面的可key 跟 value
      let b1 = {name:'lican', sex : '男', age:12}
      console.log(Reflect.has(b1,'name'))
    },
>>>>>>> 227bb5cee4e747450177e7ebe7489520ee1c5527
  }
</script>

<style scoped>
  .language-javascript {
    background: #666666;
  }
</style>
