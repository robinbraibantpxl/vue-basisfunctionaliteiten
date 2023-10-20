<script>
export default {
  data() {
    return { 
      titel: "Vue basisfunctionaliteiten",
      intro: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      baseImage: './src/assets/car.jpg',
      // Variabelen opdracht 6
      fullName: "Robin Braibant",
      age: 39,
      url: 'https://vuejs.org'
    }
  },
  methods: {
    changeText() {
      let randomNumber = Math.random();
      if (randomNumber < 0.5) {
        return "Wij verkopen de beste producten die je op de markt kan vinden"
      } else {
        return 'Wie zoekt die vindt'
      }
    },
    // Methode opdracht 6
    showRandomNumber() {
      return Math.random();
    }
  }
}
</script>

<template>
  <div class="container">
    <h1>{{ titel }}</h1>
    <p>{{ intro }}</p>
    <picture>
      <img class="main-image" v-bind:src="baseImage">
    </picture>
    <p>{{ changeText() }}</p>

    <!-- Opdracht 6 -->
    <h2>{{ fullName }}</h2>
    <p>{{ age }}</p>
    <p>{{ age + 5 }}</p>
    <p>{{ showRandomNumber() }}</p>
    <a v-bind:href="url">Vue Website</a>
    <input type="text" v-bind:value="fullName">
  </div>
</template>

<style>
.container {
  width: 75%;
  margin: auto;
  padding-bottom: 5rem;
}
picture {
  width: 100%;
  display: flex;
  justify-content: center;
}
.main-image {
  width: 50%;
}
</style>
