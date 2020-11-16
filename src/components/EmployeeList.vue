<template>
    
    <div id="app">


     <h1>Employee List</h1>

       <table border="1px">
         <tr>
             
             <td>Name</td>
             <td>Salary</td>
             <td>Age</td>

      
          </tr>   

        <tr  v-for="item in list" v-bind:key="item.id">


                  <td>{{item.id}}</td>
             <td>{{item.name}}</td>
             <td>{{item.detail}}</td>



            </tr> 


        </table>   

     



        </div>


</template>

<script>

import Vue from 'vue';
import VueAxios from 'vue-axios'
import axios from 'axios';
Vue.use(VueAxios,axios)

export default {
    
  name:"EmployeeList",
  data(){
   

      return{

          list:undefined
      }

  },

  mounted()
  {

      Vue.axios.get('http://127.0.0.1:8000/api/products')
      .then(resp=>{
          this.list=resp.data.data
          console.warn(resp.data.data)
      })
  }

}
</script>
