<template>
    <div class="navbar">
        <div class="logo">
            <img alt="CinemaPal logo" src="./assets/cinemapallogo.png" width="100px"/>
        </div>
        <div class="nav-links">
            <a href="#"> Movie Genre </a>
            <a href="#"> Year of Release </a>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'NavBar',
        data(){
            return{
                genre: String,
                yor: String 
            }  
        },  
         
    }
</script>
  
  <style scoped>
  .navbar {
    position: fixed;
    top: 0;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #333;
    color: #fff;
    padding: 10px;
  }
  
  .logo {
    font-size: 24px;
  }
  
  .nav-links a {
    color: #fff;
    margin-left: 20px;
    text-decoration: none;
  }

  .nav-links a:hover {
    background-color: #F8C391;
    color: #333;
    font-size: 16px;
    padding:20px;
    text-decoration: none;

    }
  </style>
  