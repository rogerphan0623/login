<template>
  <div class="header">
    <div class="container">
      <nav class="navbar row navbar-expand-md">
        <div class="container">
          <nuxt-link to="/" class="navbar-brand">
            <img class="img-fluid" src="img/logo.png" />
          </nuxt-link>
          <button
            type="button"
            class="navbar-toggler"
            data-bs-toggle="collapse"
            data-bs-target="#navbarCollapse"
          >
            <span class="navbar-toggler-icon"></span>
          </button>     
          <div class="collapse navbar-collapse" id="navbarCollapse">
            <ul class="navbar-nav w-100 justify-content-end">
              <li class="nav-item active">
                <nuxt-link class="nav-link text-white" to="/">Login</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link text-white" to="/about">About</nuxt-link></li>
                <li class="nav-item">
                  <nuxt-link class="nav-link text-white" to="/contact">Contact</nuxt-link></li>
            </ul>
          </div>
        </div>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
    name:"Header"
}
</script>

<style>
.navbar-toggler-icon {
        background-image: url("data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 32 32' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='rgba(255,255,255, 1)' stroke-width='2' stroke-linecap='round' stroke-miterlimit='10' d='M4 8h24M4 16h24M4 24h24'/%3E%3C/svg%3E");
}

.header{
    background-color: #1d2842;
}
a.nuxt-link-exact-active {
  font-weight: bold;
}
</style>