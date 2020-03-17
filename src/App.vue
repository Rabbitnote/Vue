<template>
  <div id="app">
    <input v-model="x" /> 
    {{op}}
    <input v-model="y" />
    <button @click="showingNum(num)" v-for="num in arrNums" :key="num">{{num}}</button>
    <button @click="operation(op)" v-for="op in arr" :key="op">{{op}}</button>
    <button @click="calculate(op)">Calculate</button>
    <p>{{result}}</p>
  </div>
</template>

<script>
export default{
/*  eslint-disable*/
data(){
  return {
    x:"",
    y:"",
    arr:['+','-','*','/'],
    result:0,
    arrNums:['1','2','3','4','5','6','7','8','9'],
    First:true,
    op:'+'
    
    }
},
methods:{
  operation(op){
    
  if(op=='+'){
      this.op='+'
      this.First=false
  }else if(op=='-'){
      this.op='-'
     this.First=false
  }else if(op=='*'){
    this.op='*'
    this.First=false
  }else if(op=='/'){
    this.op='/'
    this.First=false
     }
    },
    showingNum(num){
      this.x += ""
      this.y += ""
      if(this.First){
        this.x+=num
      }else{
        this.y+=num    
    }
  },
  calculate(op){
    this.x=parseInt(this.x)
    this.y=parseInt(this.y)
    if(this.op=='+'){
      this.result=this.x+this.y
  }else if(this.op=='-'){
    this.result=this.x-this.y
    }else if(this.op=='*'){
      this.result=this.x*this.y
      }else if(this.op=='/'){
        this.result=this.x/this.y
        }
}
}
}
</script>

<style>

</style>
