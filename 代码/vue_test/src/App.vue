<template>
  <div>
		<h1>名字：{{person.name}}</h1>
		<h1 v-show="person.age">年龄：{{person.age}}</h1>
		<h1 v-show="person.sex">性别：{{person.sex}}</h1>
		<h1>爱好：{{hobby}}</h1>
    <button @click = "addSex">添加性别</button>
  </div>
</template>

<script>
	export default {
		name:'App',
    data(){
      return {
        person: {
          name: "李四",
          age: "6"
        },
        hobby:['学习','吃饭']
      }
    },
    methods:{
      addSex(){
        // this.person.sex = "男"  不会生效
        this.$set(this.person,'sex','男')
        // delete this.person.age  不会生效
        this.$delete(this.person,'age')
      },
      deleteHobby(){
        // delete this.hobby[0]  不会生效
        //删除
        // this.hobby.splice(0,1)
        //修改
        this.hobby.splice(0,1,"逛街")
      }
    }
	}
</script>
