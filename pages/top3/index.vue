<template>
  <div class="container">
    <div>
      <h1>Can you guess the IMDB users' top 3 movies?</h1>
    </div>

    <div>
      <div class="container-fluid">
        <!-- 3 accordion features will be generated-->
        <div class="accordion" id="accordion1">
          <!-- accordion generation-->
          <div v-for="(movie, index) in movies" :key="index" class="accordion-item">
            <h2 class="accordion-header" :id="'headingOne'+index">
              <button
                class="accordion-button"
                type="button"
                data-toggle="collapse"
                :data-target="'#collapseOne'+index"
                :aria-controls="'collapseOne'+index"
              >
              Click to expand/collapse
              </button>
            </h2>
            <div
              :id="'collapseOne'+index"
              class="accordion-collapse collapse"
              :aria-labelledby="'headingOne'+index"
              data-parent="#accordion1"
            >
              <div class="accordion-body">
                <div>
                  <h2>{{ movie.title }}</h2>
                  <img class="img-thumbnail" :src="movie.imgUrl" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  
  data() {
    return {
      movies: [
        {
          title: "The Shawshank Redemption",
          imgUrl: "https://img.omdbapi.com/?i=tt0111161&h=600&apikey=b77d742c"
        },
        {
          title: "The Godfather",
          imgUrl: "https://img.omdbapi.com/?i=tt0068646&h=600&apikey=b77d742c"
        },
        {
          title: "The Dark Knight",
          imgUrl: "https://img.omdbapi.com/?i=tt0468569&h=600&apikey=b77d742c"
        }
      ]
    };
  }
};
</script>

<style>
.container {
  max-width: 600px;
  margin: 0 auto;
  padding: 8rem 1rem 0 0;
}

.img-thumbnail {
  box-shadow: 0 0 .1rem 0 rgba(0, 0, 0, 0.38);  
}
</style>