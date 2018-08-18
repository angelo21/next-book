
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
          {title: "84k"},
          {title: "The acolyte"},
          {title: "The Bankers Wife"},
          {title: "The Beach"},
          {title: "The blade itself"},
          {title: "The book of m"},
          {title: "The Book Thief"},
          {title: "The Breach"},
          {title: "The butterfly Garden"},
          {title: "The changeling"},
          {title: "The cipher"},
          {title: "the city and the city"},
          {title: "the company man"},
          {title: "The cricifix killer"},
          {title: "The croning"},
          {title: "the deep"},
          {title: "The expanse"},
          {title: "The eye of the minds"},
          {title: "The first fifteen lives"},
          {title: "The fisherman"},
          {title: "The girl next door"},
          {title: "The girl with the dragon tattoo"},
          {title: "the gone away world"},
          {title: "The gray man"},
          {title: "The green mile"},
          {title: "The hitchhikers guide"},
          {title: "The Hobbit"},
          {title: "The last policeman"},
          {title: "The library at mount char"},
          {title: "The lies of locke lamora"},
          {title: "The long walk"},
          {title: "The name of the wind"},
          {title: "The passage"},
          {title: "The quantum thief"},
          {title: "The Rise and fall of d.o.d.o"},
          {title: "The shadow of what was lost"},
          {title: "The shattered sea"},
          {title: "The Shining"},
          {title: "The sisters brothers"},
          {title: "The speed of sound"},
          {title: "The stand"},
          {title: "the terror"},
          {title: "The three body problem"},
          {title: "The wasp factory"},
          {title: "The windup girl"},
          {title: "the woman in the window"},
          {title: "the ruins"},
          
          {title: "A noise downstairs"},
          {title: "a simple plan"},
          {title: "Abandon"},
          {title: "Afraid Omnibus"},
          {title: "After on"},
          {title: "alice"},
          {title: "All our wrong todays"},
          {title: "Already dead"},
          {title: "Alterworld"},
          {title: "Amazonia"},
          {title: "Annihilation"},
          {title: "Armada"},
          {title: "Assasins Apprentice"},
          {title: "aurora"},

          {title: "Baby Teeth"},
          {title: "blackbird"},
          {title: "blood meridian"},
          {title: "Borne"},
          {title: "Brillance"},
          
          {title: "city of golden shadow"},
          {title: "city of stairs"},
          
          {title: "Death of Mrs. Westaway"},
          {title: "Deception Point"},
          
          {title: "Early Riser"},
          {title: "Eeny meeny"},
          {title: "enders game"},
          {title: "Everlost"},

          {title: "Fantasticland"},
          {title: "Firefall"},
          
          {title: "Gardens of the moon"},
          {title: "Ghost Story"},
          {title: "going home (OD)"},
          {title: "Guess Who"},
          
          {title: "hex"},
          {title: "House of cards"},
          {title: "How to stop time"},
          {title: "Hyperion"},
          
          {title: "Infected"},
          {title: "Innocents Lost"},
          {title: "It"},
          
          {title: "Let the right one in"},
          {title: "lies"},
          {title: "lightning"},
          {title: "little liars"},
          {title: "Living dead girl"},
          {title: "Lock in"},
          {title: "Lolita"},
          
          {title: "Maze Master"},
          {title: "Misery"},
          {title: "mistborne"},
          {title: "Mr. penumbra"},
          {title: "My best friends exorcism (OD)"},
          
          {title: "Necroscope"},
          {title: "Neuromancer"},
          {title: "Night Film"},
          {title: "nocturnal"},

          {title: "Obscura"},
          {title: "off season"},
          {title: "Off to be the wizard"},
          {title: "One of us"},
          {title: "origin"},

          {title: "Paradox Bound"},
          {title: "Pet Semetary"},
          {title: "Prince of thornes"},
          
          {title: "Red dragon"},
          {title: "Reincarnation Blues"},
          {title: "Rust and stardust"},
          
          {title: "Sandman Slim"},
          {title: "Scrublands"},
          {title: "Seed"},
          {title: "Semiosis"},
          {title: "Shift"},
          {title: "Six of crows"},
          {title: "Six wakes"},
          {title: "Sleeping giants"},
          {title: "Snap"},
          {title: "Snow crash"},
          {title: "Sometimes I Lie"},
          {title: "sparrow rock"},
          {title: "Speaks the nightbird"},
          {title: "Sphere"},
          {title: "Steelheart"},
          {title: "Still Life for Crows"},
          
          {title: "Touch"},
          {title: "Triptych"},
          
          {title: "Unhappenings"},
          {title: "Unwind"},
          
          {title: "Version control"},
          
          {title: "Warm Bodies (OD)"},
          {title: "When galaxies collide"},
          
          {title: "Year Zero"},
          {title: "You"},

          {title: "Zero World (OD)"},
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
      },
      showList() {
        this.disabled = true;
        EventBus.$emit("list", this.books)
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

