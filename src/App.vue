<script>
export default {
    data() {
        return {
            naam: 'Mylan van Vugt',
            leeftijd: 20,
            link: 'https://vuejs.org/',
        }
    },
    methods: {
        add() {
            document.getElementById("but").style.display = "block";
        },
        verwijder() {
            document.getElementById("but").style.display = "none";
        },
        addfive() {
            let leeftijd = 20;
            return leeftijd + 5;
        },
        getal() {
            let getal = Math.random();
            return getal
        },
        afb(tekst, event) {
            event = document.getElementsByTagName("img")[0].src = "assets/poker-winkel.png";
            tekst = document.getElementsByTagName("button")[0]. innerHTML = "afbeelding gewijzigd";
        }
    }
}
</script>

<template>
  <h2 @click="leeftijd++">{{ naam }}</h2>
    <br>
  <p>{{ leeftijd }}</p>
    <br>
  <p>{{ addfive() }}</p>
    <br>
  <p>willekeurig getal: {{ getal() }}</p>
    <br>
  <a href="{{ link }}">link</a>
    <br>
  <input type="text" name="naam" :value="naam">
    <br>
  <button @click="afb(tekst, event)">nieuwe afbeelding</button>
    <br>
  <img @click="add()" src="assets/Schermafbeelding%202023-06-10%20161041.png" alt="afbeelding">
    <br>
  <button id="but" @click="verwijder()">Verberg mij</button>
</template>

<style>
#but {
    display: none;
}
</style>
