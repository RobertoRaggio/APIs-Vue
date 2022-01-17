<template>
    <div id="app">
    <ul>
      <li v-for="(personaje, i) in personajes" :key="i">
        <img :src="getPersonajes(personaje)"/>
        <p>{{ personaje.name }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      personajes: [
        { id: 1, name: "Rick Sanchez" },
        { id: 2, name: "Morty Smith" },
        { id: 3, name: "Summer Smith" },
        { id: 4, name: "Beth Smith" },
      ],
    };
  },
  methods: {
  getPersonajes(personaje) {
      return `https://rickandmortyapi.com/api/character/avatar/${personaje.id}.jpeg`;
      },
    },
  };
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  background: url("https://rickandmortypod.com/wp-content/uploads/2018/11/cropped-RM_page-header_background1-3.png")
    no-repeat center center fixed;
  background-size: cover;
}

ul li {
  display: flex;
  flex-direction: row;
  vertical-align: middle;
}
img {
  height: 200px;
  border-radius: 50%;
  padding-top:10px;
}
ul li p {
  color: green;
  font-size: 20px;
  font-weight: 900;
  text-align: center;
}
</style>
