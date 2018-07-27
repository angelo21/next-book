
<template>
  <div class="input">
    <input 
      type="text" 
      class="input__form"
      v-model="input">
  </div>
</template>

<script>
  import { EventBus } from "../main.js";
  
  export default {
    data() {
      return {
        input: "Random Book Pick",
        showInputField: false
      }
    },
    methods: {
      randomPick($event) {
        let counter = 3;
        this.input = "Finding your new book..."
        let countdown = setInterval(() => {
          this.input = counter--;
          if (counter === -1) {
            this.input = $event;
            clearInterval(countdown);
          }
        },1000)
      }
    },
    created() {
      EventBus.$on("random-pick", this.randomPick)
    }
  }
</script>


<style lang="scss">
  .input {
    margin-bottom: 2rem;

    &__form {
      background-color: rgba(0,0,0,.5);
      border: 1px solid transparent;
      border-radius: 4rem;
      color: white;
      font-size: 1.7rem;
      font-weight: 100;
      outline: none;
      padding: 1.7rem;
      text-align: center;
      text-transform: capitalize;
      width: 30rem;
    }

    @media screen and (max-width: 400px) {
      .input__form {
        width: 90%;
        margin-left: 5%;
        height: 7rem;
        font-size: 1.8rem;
      }
    }
  }
</style>


