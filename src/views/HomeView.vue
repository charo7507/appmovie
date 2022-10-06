<template>
  <div class="home">
    <header class="header">
      <nav class="nav container">
        <a href="#" class="nav__logo">
          Movie<span>App</span>
        </a>
        <div class="nav__menu">
          <form action="" class="nav__form" @submit.prevent="findMovie">
            <input 
            type="search" 
            class="nav__input" 
            placeholder="Search..."
            v-model="moviename">
          </form>
        </div>
      </nav>
    </header>

          <main>
        <section class="section__home section">
          <div class="home__content container grid">
          <MovieCards 
          v-for="(movie, i) in allmovie" 
          :key="i"
          :movie="movie"
           />
          </div>
        </section>
      </main>
  </div>
</template>

<script setup>
import { ref } from '@vue/reactivity'
import MovieCards from '../components/MovieCards.vue'


const moviename = ref('')
const allmovie = ref([])


const findMovie = async () =>{
  allmovie.value = await fetch(`http://www.omdbapi.com/?s=${moviename.value}&apikey=ed2662d9`)
  .then(res => res.json())
  .then(data => data.Search)
  console.log(allmovie.value);

}



</script>

<style lang="scss">

.header{
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;
  transition: .6s;

  .nav{
    height: 3.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;

  .nav__logo{
    font-size: 2.5rem;
    color: #000;

    span{
      font-size: 3rem;
      color: crimson;
    }
  }

  .nav__input{
    min-width: 300px;
    width: 100%;
    height: 40px;
    padding: 10px 20px;
    border-radius: .5rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.493);
  }

  }

}

  .home__content{
    display: flex;
    justify-content: space-between;
    align-items: center;
    // place-items: center;
    gap: 1rem;
    flex-wrap: wrap;
  }



  @media screen and (max-width: 674px) {
    
.header{

  .nav{
 
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    align-items: center;

  .nav__logo{
    font-size: 2.5rem;
    color: #000;

    span{
      font-size: 3rem;
      color: crimson;
    }
  }

  .nav__input{
    min-width: 300px;
    width: 100%;
    height: 40px;
    padding: 10px 20px;
    border-radius: .5rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.493);
  }

  }

}
  }



</style>
