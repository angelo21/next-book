
<template>
  <div class="button">
    <button 
      class="btn button__random"
      @click="loadRandomPick">{{ random }}
    </button>
  </div>
</template>

<script>
  import { EventBus } from "../main.js";

  export default {
    data() {
      return {
        random: "Random Book",
        books: [
          {title: "The butterfly Garden"},
          {title: "Fantasticland"},
          {title: "The girl next door"},
          {title: "The last policeman"},
          {title: "The library at mount char"},
          {title: "Lolita"},
          {title: "Mr. penumbra"},
          {title: "Six wakes"},
          {title: "Sleeping giants"},
          {title: "Sphere"},
          {title: "The wasp factory"},
          {title: "Version control"},
          {title: "Off to be the wizard"},
          {title: "84k"},
          {title: "Guess Who"},
          {title: "The book of m"},
          {title: "The girl with the dragon tattoo"},
          {title: "House of cards"},
          {title: "The lies of locke lamora"},
          {title: "Paradox Bound"},
          {title: "Red dragon"},
          {title: "Semiosis"},
          {title: "Sleeping Giants"},
          {title: "Reincarnation Blues"},
          {title: "Sometimes I Lie"},
          {title: "Maze Master"},
          {title: "Baby Teeth"},
          {title: "Innocents Lost"},
          {title: "The Shining"},
          {title: "Misery"},
          {title: "Pet Semetary"},
          {title: "Night Film"},
          {title: "Snap"},
          {title: "The Bankers Wife"},
          {title: "Infected"},
          {title: "Brillance"},
          {title: "Touch"},
          {title: "Unhappenings"},
          {title: "Steelheart"},
          {title: "Unwind"},
          {title: "It"},
          {title: "Hyperion"},
          {title: "A noise downstairs"},
        ],
        newBook: "",
      }
    },
    methods: {
      loadRandomPick() {
        let ranNum = Math.floor(Math.random() * this.books.length) + 1;
        
        this.books.forEach((item,index) => {
          item.id = index + 1
          
          if (ranNum === item.id) {
            this.newBook = item.title;
          }
        })
        EventBus.$emit("random-pick", this.newBook)
      }
    }
  }
</script>


<style lang="scss">
  .button {
    display: flex;
    justify-content: center;
  }
</style>

