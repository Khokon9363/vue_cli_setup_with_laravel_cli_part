<template>
  <div>
    <h1>My Component</h1>
    <h3 v-for="user in users" :key="user.id">{{ user.name }}</h3>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'MyComponent',
  props: {
    
  },
  data(){
    return{
      users : [],
      BASE_URL : 'http://localhost:8000/',
    }
  },
  created(){
    this.getData()
  },
  methods:{
    getData(){
      axios.get(this.BASE_URL+'api/vue')
           .then(res => {
             if (res.data.success == true) {
                 this.users = res.data.data
             }
           })
           .catch(err => {
             console.error(err)
           })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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