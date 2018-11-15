<template>
  <div class="hello">
	<ul>
	    
		<li>

	    <el-row>
		    <el-col :span="12">
			<el-input type="text" v-model="inputValue"/>
		
			</el-col>
			<el-col :span="8">
			<el-button type="primary" v-on:click="handleClick" aria-label="Click">Clicked Me</el-button>
			</el-col>
		</el-row>
		<ul>
		  <todolist v-for="(item,index) in listValues" :key="index" :index="index" :content="item" @itemclick="handleItemclick"></todolist>
		</ul>
		</li>
	</ul>
  </div>
</template>

<script>
import todolist from './todolist'
export default {
  name: 'HelloWorld',
  components:{todolist:todolist},
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
	  listValues:[],
	  inputValue:''
    }
  },
  methods:{
     handleClick:function(){
	    this.listValues.push(this.inputValue);
		this.inputValue='';
	 },
	 handleItemclick:function(el){
	   console.log('调用界面处理函数Callback');
	   console.log(el);
	 }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
