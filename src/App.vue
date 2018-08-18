
<template>
  <div class="container">
    <app-search></app-search>
    <app-book-exists></app-book-exists>
    <app-button></app-button>
  </div>
</template>

<script>
  import AppSearch from "./components/SearchBar.vue";
  import AppButton from "./components/Buttons.vue";
  import AppBookExists from "./components/BookExitsts.vue";

  export default {
    data() {
      return {
        
      }
    },
    components: {
      AppSearch,
      AppButton,
      AppBookExists,
    }
  }
</script>


<style lang="scss">
//GLOBAL STYLES
  * {
    box-sizing: inherit;
  }

  html {
    box-sizing: border-box;
    font-family: sans-serif;
    font-size: 62.5%;
  }

  body {
    font-size: 1.6rem;
    background: linear-gradient(to right, #23074d,#cc5333)
  }

  .container {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%)
  }

  .btn {
    background-color: transparent;
    border: .1rem solid lightblue;
    border-radius: 1rem;
    color: white;
    cursor: pointer;
    font-size: 1.4rem;
    font-weight: 100;
    outline: none;
    padding: 1rem;
    text-transform: uppercase;
    transition: all .6s;
    
    &:hover {
      border: .1rem solid #59b9e5;
    }

    &:active {
      transform: translate(.1rem, .1rem);
    }
  }

  @media screen and (max-width: 400px) {
    .container {
      width: 100vw;
    }
    .btn {
      padding: 2rem;
      font-size: 1.7rem;
    }
  }
</style>
