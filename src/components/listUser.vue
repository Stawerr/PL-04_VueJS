<template>
        <div class="card grid-item">
            <img :src="user.picture?.large" alt="Avatar" style="width:100%">
            <h4><b>{{user.name?.first}} {{user.name?.last}}</b></h4> 
            <p>{{user.location?.country}}</p> 
            <button @click="nameAlert">Alert</button>
        </div>
</template>

<script>

export default {
    props:{
    user: ''
  },
  methods: {
    nameAlert(){
      alert(this.user.name.first);
    }
  },

}
</script>

<style scoped>

.grid-item {
  text-align: center;
}
.card {
    margin-top: 40px;
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    transition: 0.3s;
    width: 60%;
    margin-left: auto;
    margin-right: auto;
}

.card:hover {
    box-shadow: 0 8px 16px 0 rgba(223, 8, 8, 0.2);
}

.container {
   
}
</style>