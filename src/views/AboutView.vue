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
      <tr v-for="item in bio" :key="item.index">
        <td>{{item.nama}}</td>
        <td>{{item.email}}</td>
        <td>{{item.gender}}</td>
      </tr>
      </tbody>
    </table>
    <button class="btn btn-sm btn-outline-danger">Delete</button>
  </div>
</template>

<script>
import axios from 'axios'
import {onMounted, ref} from 'vue'

export default {
  name: "about",
  data(){
    return {
      bio : [
        {
          id:"1",
          nama:"selfhy",
          email: "s@gmail",
          gender: "female",
        },
        {
          id:"2",
          nama:"defhy",
          email: "d@gmail",
          gender: "female",
        },
        {
          id:"3",
          nama:"bana",
          email: "b@gmail",
          gender: "male",
        }
      ],
    };
  },
}
</script>
