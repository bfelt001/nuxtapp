<template>
    <nav class="navbar fixed-top navbar-expand-lg navbar-dark bg-dark">
      <router-link to="/" class="navbar-brand">My Movie Website</router-link>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <NuxtLink to="/" class="nav-link">Home</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink to="/images" class="nav-link">Images</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink to="/top3" class="nav-link">Top 3 Movies</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink to="/contact" class="nav-link">Contact</NuxtLink>
          </li>
        </ul>
      </div>
    </nav>
  </template>
  
  <style>
  .navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #f8f9fa;
  border-bottom: 1px solid #dee2e6;
  padding: 10px;
  z-index: 999;
 
}
  
  .navbar-brand {
    font-size: 1.5rem;
  }
  
  .navbar-nav {
    font-size: 1.2rem;
  }
  
  .navbar-nav .nav-item {
    margin-right: 1rem;
  }
  
  .nav-link {
    color: #fff;
    transition: all 0.2s ease-in-out;
  }
  
  .nav-link:hover {
    color: #17a2b8;
    text-decoration: none;
  }
  
  @media (max-width: 875px) {
    .navbar-nav {
      margin-top: 1rem;
    }
  
    .navbar-nav .nav-item {
      margin-right: 0;
      margin-bottom: 0.5rem;
    }
  }
  </style>
  
  <script>
  export default {
    name: 'Navbar'
  }
  </script>
  