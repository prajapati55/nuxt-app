<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      aria-controls="navbarTogglerDemo01"
      aria-label="Toggle navigation"
      @click.prevent="navbarClick()"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="navbar-collapse" :class="{'collapse': !divCollapse}" >
      <a class="navbar-brand" href="#"> Logo Here </a>
      <ul class="navbar-nav mr-auto mt-2 mt-lg-0" @click.prevent="navLinkClick()">
        <li class="nav-item active" >
            <nuxt-link to="/" class="nav-link"> Home <span class="sr-only">(current)</span></nuxt-link>
        </li>
        <li class="nav-item">
            <nuxt-link to="/blogs" class="nav-link"> Blogs </nuxt-link>
        </li>
        <li class="nav-item">
            <nuxt-link to="/blogs" class="nav-link"> Tutorials </nuxt-link>
        </li> 
        <li class="nav-item">
          <nuxt-link to="/about" class="nav-link"> About </nuxt-link>
        </li>               
      </ul>
      <ul class="nav navbar-nav my-2 my-lg-0">
        <li class="nav-item">
          <a href="javascript:void(0)" class="btn btn-outline-success" @click="showLoginModal"> Login</a>
        </li>
      </ul>      
    </div>
  </nav>
</template>

<script>
export default {
  name: "navbar",
  data(){
    return {
      divCollapse:false
    }
  },  
  methods: {
    navbarClick(){
      this.divCollapse = !this.divCollapse;
    },
    navLinkClick(){
        this.divCollapse = false;
    },
    showLoginModal(){
      this.$emit('showmodal');
    }
  }
};
</script>

<style>
</style>
