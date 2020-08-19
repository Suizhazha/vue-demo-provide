<template>
  <div :class="`app theme-${themeName} fontSize-${fontSize}`">
    <Child1/>
    <button>x</button>
    <Child2/>
    <button>x</button>
    <Child3/>
    <button>x</button>
    <Child4/>
    <button>x</button>
    <Child5/>
    <button>x</button>
  </div>
</template>

<script>
import Child1 from "@/components/Child1.vue"
import Child2 from "./components/Child2.vue";
import Child3 from "./components/Child3.vue";
import Child4 from "./components/Child4.vue";
import Child5 from "./components/Child5.vue";

export default {
  name: 'App',
  provide(){
return {
  themeName: this.themeName,
  changeTheme:this.changeTheme,
  changeFontsize:this.changeFontsize
}
  },
  data(){
    return {
      themeName:'blue', //red
      fontSize:'normal', // 'big'| 'small'
    }
  },
  methods:{
    changeTheme(){
      this.themeName = this.themeName === "blue" ? "red" : "blue"
    },
    changeFontsize(size){
       if (['normal','big','small'].indexOf(size)>=0){
        this.fontSize = size
       }
    }
  },
  components: {
    Child1,
    Child2,
    Child3,
    Child4,
    Child5
  }
}
</script>

<style lang="scss">
.app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

// 满足app元素同时是theme-blue的
// 一个元素同时满足app和theme-blue
// 同时满足中间不能有空格
// 后面有空格表示该元素内部的button
.app.theme-blue button {
  background: blue;
  color: white;
}
.app.theme-blue {
  color: darkblue;
}

.app.theme-red button {
  background: red;
  color: white;
}
.app.theme-red {
  color: darkred;
}
.app.fontSize-normal{
  font-size: 16px;
}
.app.fontSize-big{
  font-size: 26px;
}
.app.fontSize-small{
   font-size: 10px;
 }
//按钮继承app的字体大小
.app button{
  font-size: inherit;
}
</style>
