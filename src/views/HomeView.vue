<template>
  <div class="container">
    <div class="mb-2">
      <h1>Search Data</h1>
      <div class="input-group mb-3">
        <input type="text" class="form-control" placeholder="search.." v-model="dataCari">
      </div>
    </div>
  <!--   <button class="btn btn-sm btn-outline-primary" :onClick="searchData">Search</button>
   --></div>
  <div class="container mt-2">
    <ul>
      <li v-for="item in searchData" :key="item.index">{{item}}</li>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
  components: {
    
  },
  data(){
    return{
      dataCari:[],
      data : [
        'Danawi Liam',
        'Tarjaya',
        'Daruna',
        'Warsoni',
        'John Wick',
        'Hadi PS',
        'Derian Lekso'
        ]
    }
  },
  methods:{

  },
  computed:{
    searchData(){
     return this.data.filter((item)=>{
       return item.match(this.dataCari);
     })
      
    }
  }
}
</script>
