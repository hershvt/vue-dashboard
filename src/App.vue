<template>
  <div id="app">
    <div id="nav">

  <b-navbar  variant="white" type="light" class="ma-0 pa-0 navbar">
    <b-button v-b-toggle.sidebar-1 variant="light" class="mr-3 ml-3 icon"><b-icon icon="list-nested" aria-hidden="true"></b-icon></b-button>
    <b-navbar-brand href="#" >Dashboard demo</b-navbar-brand>

    <b-collapse id="nav-collapse" is-nav>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-navbar-nav class="ml-auto">

        <b-navbar-nav>
        <b-nav-item href="#" to="/" active>Home </b-nav-item> 

        <b-nav-item href="#" to="/about">About</b-nav-item>
        </b-navbar-nav> 
    </b-navbar-nav>
    </b-collapse>    
  </b-navbar>

    </div>
    <router-view/>


     <div>
    
    <b-sidebar id="sidebar-1" title="Pages" shadow>
     
        <b-link class="link-item pt-5" to="/">Home</b-link>
        <div class="link-section my-3"></div>
        <b-link to="/about" class=" link-item">About</b-link>
        <div class="link-section my-3"></div> 
        <b-link to="/list" class=" link-item">List</b-link>
        <div class="link-section my-3"></div> 
        <b-link to="/table" class=" link-item">Table</b-link>
        <div class="link-section my-3"></div>
    </b-sidebar>
  </div>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding-bottom: 20px;
  
}

#nav a {
  font-weight: 500;
  font-size: 25px;
  color: #000;
}

#nav a.router-link-exact-active {
  color: #2c3e50;
}

.navbar{
box-shadow: 0 .8rem 1rem rgba(0,0,0,.18)!important;
}
.icon{
  box-shadow: 0 .1rem 1rem rgba(0,0,0,.31)!important;
}

.link-item{
    font-family: Avenir, Helvetica, Arial, sans-serif;
    font-size: 25px;
    color: rgb(85, 85, 85);
    
}

.link-section{
border: #d8d8d8 1px solid ;
margin : 0px 15px;
}


</style>
