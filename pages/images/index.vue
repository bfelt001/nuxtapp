<template>
    <main class="main">
      <div class="container">
        <div class="container-fluid">
          <div>
            <h1>Enjoy some movie related images!</h1>
          </div>
          <!-- display images in 2 rows -->
          <div class="row">
            <div class="col-sm-4" v-for="image in images1" :key="image.id">
              <!-- Updated src to use require() so dynamic links work -->
              <img :src="require('/'+image.url)" class="img-fluid" alt="Movie themed images">
            </div>
          </div>
  
          <div class="row">
            <div class="col-sm-4" v-for="image in images2" :key="image.id">
              <img :src="require('/'+image.url)" class="img-fluid" alt="Movie themed images">
            </div>
          </div>
        </div>
      </div>
    </main>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isNavbarOpen: false,
        images1: [
          { id: 1, url: 'camera1.jpg' },
          { id: 2, url: 'theater.jpg' },
          { id: 3, url: 'theater1.jpg' },
        ],
        images2: [
          { id: 4, url: 'film1.jpg' },
          { id: 5, url: 'theater2.jpg' },
          { id: 6, url: 'popcorn2.jpg' },
        ],
      };
    },
    head() {
      return {
        title: this.title,
        meta: [
          // hid is used as unique identifier. Do not use `vmid` for it as it will not work
          {
            hid: 'description',
            name: 'description',
            content: 'This is a website about movies and movie lovers. Users can enjoy seeing images related to movies here.'
          }
        ]
      }
    },
  };
  </script>

<style>
.container {
  max-width: 75%;
  margin: 0 auto;
  padding: 8rem 1rem 0 0;
}

img {
  box-shadow: 5px 4px 10px red;
  padding: .5rem;
}
</style>