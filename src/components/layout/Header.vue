<template>
    <header class="card-panel teal lighten-2 black-text center-align ">
        <div class="card-content">
      <h1> TodoList</h1>
      </div>
      
          <div class="card-tabs text-large ">
      <ul class="tabs tabs-fixed-width ">
      <li class="tab"><router-link to="/">Home</router-link></li>
      <li class="tab"><router-link to="/about">About</router-link></li>
      </ul>
    
    
    
      </div>
    </header>
</template>
<script>
export default {
    name: "Header"
}
</script>

<style scoped>
header{
    text-align: center;
    padding: 10px;
    margin: 1%;
}

.tab a{
    color:black;
    
}


</style>