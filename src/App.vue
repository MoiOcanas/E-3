<template>
  <div>
    <h1>My Favorite Artists</h1>
    <ol>
      <span @click="bool ? as() : des()" class="changeSpan">
        <i class="fas fa-angle-down fa-3x"></i>
      </span>
      <item-list v-for="art in artists" :art="art" :key="art.name"></item-list>
    </ol>
  </div>
</template>

<script>
import ItemList from "./components/ItemList.vue";
import arraySort from "array-sort";
export default {
  name: "app",
  data() {
    return {
      bool: true,
      artists: [
        { id: 0, name: "Daft Punk" },
        { id: 1, name: "Justice" },
        { id: 2, name: "Parcels" },
        { id: 3, name: "Jungle" },
        { id: 4, name: "Sir Sly" },
        { id: 5, name: "Gorillaz" },
        { id: 6, name: "Soulwax" },
        { id: 7, name: "Metallica" },
        { id: 8, name: "Little Jesus" },
        { id: 9, name: "Run the Jewels" }
      ]
    };
  },
  methods: {
    as() {
      arraySort(this.artists, "name");
      this.bool = !this.bool;
    },
    des() {
      arraySort(this.artists, "name", { reverse: true });
      this.bool = !this.bool;
    }
  },
  computed: {},
  components: {
    ItemList
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Cabin");
$primary-color: black;
$secondary-color: #e9e9e9;
$third-color: #f9f9f9;

body {
  background: $third-color;

  h1 {
    text-align: center;
    font-family: "Cabin", sans-serif;
    font-size: 4em;
  }

  ol {
    background: $secondary-color;
    margin: 0 auto;
    border-radius: 2px;
    width: 800px;
    padding: 5px;
    list-style: none;

    display: grid;
    grid-template-rows: auto auto auto;
  }
}

.changeSpan {
  margin: 5px;
  text-align: center;
  width: 100px;
    
  &:hover {
    background: #f9f9f9;
    -webkit-transition: 0.3s;
    transition:  0.3s;
  }
}
</style>
