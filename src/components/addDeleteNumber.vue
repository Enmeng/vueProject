<template>
　　<div id="firstcomponent">
    <button v-on:click="add">Add</button>
    <button v-on:click="remove">Remove</button>
    <transition-group name="list" tag="p">
     <span v-for="item in items" v-bind:key="item" class="list-item">{{item}}</span>
   </transition-group>
    </div>
</template>




<script type="text/javascript">
import Vue from "vue"
export default({
  name:"firstcomponent",
  data(){
    return {
      items:[1,2,3,4,5,6,7,8,9],
      nextNum:10
    }
  },
  methods:{
    randomIndex:function(){
      return Math.floor(Math.random()*this.items.length);
    },
    add:function(){
      this.items.splice(this.randomIndex(),0,this.nextNum++);
    },
    remove:function(){
      this.items.splice(this.randomIndex(),1);
    }
  }
});
</script>

<style>
.list-item{
  display: inline-block;
  margin-right:10px;
  transition:all 1s;
}
.list-leave-active{
  position:absolute;
}
.list-enter,.list-leave-to{
  opacity:0;
  transform:translateY(30px);
}
</style>
