<template>
  <HelloWorld msg="Hello Vue 3 + Vite" />
</template>

<script setup>
import HelloWorld from './components/HelloWorld.vue'

</script>

<style>
.fullcard {
  border: 5px solid;
  text-align: center;
  color: white;
  margin: 12px;

  background-color: black;
  padding: 16px;
}
p{
  display: none;
}
img {
  max-width: 75%;
  max-height: 75%;
  margin: auto;
  display: block;
  padding: 16px, 16px;
}
button{
  padding: 8px 8px;
  color: blue;
  background-color: orange;
  text-transform: uppercase;
  display: none;
  margin: 8px;
}
.details{
  padding: 8px 8px;
  color: blue;
  background-color: orange;
  text-transform: uppercase;
  display: none;
  margin: 8px;
}
.add {
  padding: 8px 8px;
  color: white;
  background-color: red;
  text-transform: uppercase;
  margin: 8px;
}

.add:hover {
  background-color: green;
  color: yellow;
}

.hoverclass{
  background-color: green;
  color: yellow;
}

.add:focus{
  background-color: green;
  color: yellow;
}

.toggle{
  background-color: blue;
  color: orange;
}

@media screen and (min-width: 500px) and (max-width: 800px){
  button{
    display: inline-block;
  }
  .details{
    display: inline-block;
  }
}
@media (max-width: 500px) {
  div{
    font-size: 10px;
  }
}

input:checked + label + .description { display:none; }



</style>
