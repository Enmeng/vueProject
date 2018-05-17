<template>
　　<div id="firstcomponent">
    <input v-model="newTitle" v-on:keyup.enter="addNewItem" placeholder="Add a new item"/>
     <ul>
       <li is="todo-item" v-for="(item,index) in items" v-bind:key="item.id" v-bind:title="item.text" v-on:remove="items.splice(index,1)">

       </li>
     </ul>
　　</div>
</template>

<script type="text/javascript">
import Vue from "vue"
Vue.component('todo-item',{
  props:['title'],
  template:'<li>{{title}}<button v-on:click="$emit(\'remove\')">X</button></li>'
});
export default({
  name:"firstcomponent",
  data(){
    return {
      newTitle:"",
      items:[{id:0,text:"Milk"},{id:1,text:"Bread"},{id:2,text:"Chooise"},{id:3,text:"Fruit"}],
      nextItemId:4
    }
  },
  methods:{
    addNewItem:function(){
      this.items.push({id:this.nextItemId++,text:this.newTitle});
      this.newTitle="";
    }
  }
})
</script>

<style>
</style>
