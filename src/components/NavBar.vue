<template>
    <div class="topnav">
        <a href="#home">SANOTE</a>
        <a href="#news">GitHub</a>
        <a href="#contact">Регистрация</a>
        <a href="#about">Вход</a>
    </div>
</template>

<script>
export default {
    name: "NavBar",    
}
</script>


<style>
/* Add a black background color to the top navigation */
.topnav {
  background-color: #686354;
  overflow: hidden;
}

/* Style the links inside the navigation bar */
.topnav a {
  float: left;
  color: #f2f2f2;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}

/* Change the color of links on hover */
.topnav a:hover {
  background-color: #50c19a;
  color: black;
}

/* Add a color to the active/current link */
.topnav a.active {
  background-color: #50c19a;
  color: white;
}
</style>
