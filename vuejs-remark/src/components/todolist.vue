<template>
<li v-on:click="handleClick">
  <el-button type="primary">{{content}}</el-button>

</li>
</template> 
<script>
export default {
   props:['content','index'],
   methods:{
     handleClick:function(){
	    console.log('委托父组件的处理方法');
	     this.$emit('itemclick',this.index);
	 }
   }
}
</script>
<style scoped></style>
