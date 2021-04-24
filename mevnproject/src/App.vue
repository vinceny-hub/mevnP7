<template>
<div class="container">
<nav class="navbar navbar-expand-md navbar-dark bg-dark">
  <a class="navbar-brand" href="#">Groupomania</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarText" aria-controls="navbarText" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarText">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
       <router-link to="/" class="nav-link">Home<span class="sr-only">(current)</span></router-link>
      </li>
      <li class="nav-item">
         <router-link to="/create" class="nav-link" >Create Post</router-link>
      </li>
      <li class="nav-item">
        <router-link to="/posts" class="nav-link">Posts</router-link>
      </li>
    </ul>
    <form class="form-inline">
    <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
    <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
  </form>
  </div>
</nav>
<br />
  <transition name=fade>
   <router-view></router-view>
  </transition> 

            <footer id="sticky-footer" class="py-4 bg-dark text-white-50">
    <div class="container text-center">
      <small>Copyright &copy; Your Website</small>
    </div>
  </footer>

</div>
  <!-- Navbar content -->

 <!-- <div >
  <nav class="navbar navbar-dark bg-dark">
   <ul >
    <li >
     <router-link to="/" class="nav-link">Home<span class="sr-only">(current)</span></router-link>
    </li>
    <li >
     <router-link to="/create" >Create Post</router-link>
    </li>
    <li >
     <router-link to="/posts" >Posts</router-link>
    </li>
   </ul>
  </nav><br />
  <transition name=fade>
   <router-view></router-view>
  </transition>
 </div> -->

</template>

<script>


export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}


</style>
