<template>
  <div class="container">
    <h1>Biodata</h1>
    <table class="table table-striped">
      <thead>
      <tr>
        <th>Nama</th>
        <th>Email</th>
        <th>Gender</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="item in bio" :key="item.id">
        <td>{{item.name}}</td>
        <td>{{item.email}}</td>
        <td>{{item.gender}}</td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: "about",
  data(){
    return {
      bio : [],
    };
  },
  methods:{
    setBio(data){
      this.bio = data;
    }
      
  },
  mounted(){
   axios.get('https://gorest.co.in/public/v2/users')
    .then((response) => {
      //console.log("success : ",response);
      this.setBio(response.data);
    })
    .catch((error) => {
      console.log("error : ",error);
    });
  },
}
</script>
