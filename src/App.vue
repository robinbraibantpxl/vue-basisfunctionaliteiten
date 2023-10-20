<script>
export default {
  data() {
    return { 
      titel: "Vue basisfunctionaliteiten",
      intro: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      // De variabele voor de afbeelding. Opgelet de @ alias werkt hier niet omdat vue de waarde als een volwaardige string gaat benaderen
      baseImage: './src/assets/car.jpg'
    }
  }
}
</script>

<template>
  <div class="container">
    <h1>{{ titel }}</h1>
    <p>{{ intro }}</p>
    <picture>
      <!-- Met v-bind kan je de variabele binden aan het src attribuut -->
      <img class="main-image" v-bind:src="baseImage">
    </picture>
  </div>
</template>

<style>
/* Basis css toegevoegd om het er allemaal wat beter te laten uitzien */
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
