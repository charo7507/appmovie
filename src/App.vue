<template>
  <router-view/>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body{
   margin: 3.5rem 0 0 0 ;
   font-family: 'Poppins', sans-serif;
}

a{
  text-decoration: none;
}

input{
  border: none;
  outline: none;
}

// main{
//   overflow: hidden;
// }

.container{
  max-width: 1200px;
  margin-left: 1.5rem;
  margin-right: 1.5rem;
}

.grid{
  display: grid;
}

  .section{
    padding: 3rem 0 2rem 2rem;
  }


@media screen and (max-width: 320px) {
  .container{
  margin-left: 1rem;
  margin-right: 1rem;
}
}

@media screen and (min-width: 767px){
  body{
    margin: 0;
  }

  .section{
    padding: 7rem 0 2rem;
  }

  .nav{
    height: calc(3.5rem + 1.5rem);
  }
  }

  @media screen and (min-width: 992px){
  .container{
    margin-left: auto;
    margin-right: auto;
  }
  }
</style>
