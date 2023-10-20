<script>
export default {
  data() {
    return { 
      titel: "Vue basisfunctionaliteiten",
      intro: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      baseImage: './src/assets/car.jpg',
      fullName: "Robin Braibant",
      age: 39,
      url: 'https://vuejs.org',
      visibility: 'display: none',

      //nieuwe variabele
      message: ''
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
    showRandomNumber() {
      return Math.random();
    },
    showButton() {
      this.visibility = ""
    },
    hideButton() {
      this.visibility = "display: none"
    },
    changeImage(event, path) {
      event.target.textContent = 'Afbeelding gewijzigd'
      this.baseImage = path;
    },

    //Methode om de alert te tonen
    partOne(){
      alert("De submit werkt toch al")
    },
    showMessage(event) {
      this.message = event.target.value;
    }
  }
}
</script>

<template>
  <div class="container">
    <h1>{{ titel }}</h1>
    <p>{{ intro }}</p>

    <picture>
      <img class="main-image" v-bind:src="baseImage" v-on:click="showButton()">
    </picture>
    <button v-bind:style="visibility" v-on:click="hideButton()">Verberg mij</button>
    <button v-on:click="changeImage($event, 'src/assets/barcelona.jpg')">Wijzig afbeelding</button>

    <p>{{ changeText() }}</p>

    <h2 v-on:click="age++">{{ fullName }}</h2>
    <p>{{ age }}</p>
    <p>{{ age + 5 }}</p>
    <p>{{ showRandomNumber() }}</p>
    <a v-bind:href="url">Vue Website</a>
    <input type="text" v-bind:value="fullName">

    <!-- Formulier met event listener en een event modifier -->
    <form class="form" v-on:submit.prevent="partOne()">
      <div class="form-field">
        <label for="message">Boodschap</label>

        <!-- DEEL 2 event listener op de input om de Boodschap te tonen in de paragraaf eronder -->
        <!-- <input type="text" name="message" id="message" v-on:input="showMessage($event)"> -->

        <!-- DEEL 3 event listener om de Boodschap enkel te tonen wanneer er op de ENTER toets wordt geklikt -->
        <input type="text" name="message" id="message" v-on:keydown.enter="showMessage($event)">

        <p>{{ message }}</p>

      </div>
      <div class="form-submit">
        <button>Verzend</button>
      </div>
    </form>
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
.form {
  display: flex;
  flex-direction: column;
  margin: 5rem 0;
  padding: 2rem;
  border: solid 1px #000000
}
.form-field {
  display: flex;
  flex-direction: column;
  margin: 1rem 0;
}

.form-submit {
  width: 50%;
  margin: 1rem 0;
}
</style>
