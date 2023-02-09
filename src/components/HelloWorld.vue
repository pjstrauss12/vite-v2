<template>
  <h1>{{ msg }}</h1>

  <div class="fullcard">
    <h1>Steel Vengeance</h1>
    <img src="https://www.gannett-cdn.com/-mm-/c866a26832d9a00c13d83ca470f7860c9325bbed/c=0-18-2099-1204/local/-/media/2017/08/16/DetroitFreeP/DetroitFreePress/636384989754521386-SteelVengence-07.JPG">
    <p>Opening in 2018 at Cedar Point in Sandusky, Ohio, Steel Vengeance has quickly became a fan favorite.  Rocky Mountain Construction, a company that retracks old wooden roller coasters, came in to revamp Mean Streak and made it a hybrid roller coaster.  This means it has a wood structure, but the trains run along a steel track.  This allows for a better experience overall and increases the lifespan of older wooden roller coasters.  The ride is 205 feet tall with a 200 foot drop at 90 degrees and it flips you upside down four times.  The top speed of Steel Vengeance is 74 miles per hour and the total ride time is 2 minutes and 30 seconds.  Learn more about the ride by clicking below.</p>
    <button class="details" v-on:click="showhide">Details</button>
  </div>
  <button class="add" v-on:click="duplicator">Make a duplicate</button>

  <button class="toggle" v-on:click="backColorChange">Background Color</button>

  <button class="word" v-on:click="words">Words</button>

  <button class="del" v-on:click="deleter">Remove Last</button>


  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank">
      Vite Documentation
    </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a>
  </p>

  <button type="button" @click="state.count++">count is: {{ state.count }}</button>
  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<script setup>
import { defineProps, reactive } from 'vue'

defineProps({
  msg: String
})

const state = reactive({ count: 0 })
</script>

<script>

export default {
  methods: {
    hoverButton(){
      document.querySelectorAll(".add").forEach((thingy) => {
        if(thingy.classList.contains("hoverclass")){
          thingy.classList.remove("hoverclass");
        } else{
          thingy.classList.add("hoverclass");
        }
      });
    },
     duplicator(){
      let d = document.querySelector('div');
      let cloneNode = d.cloneNode(true);
      document.body.appendChild(cloneNode);
      console.log(cloneNode);
    },

     backColorChange(){
      var colors = document.querySelector(".fullcard");
      if (colors.style.backgroundColor === "black"){
        colors.style.backgroundColor = "blue";
      }else{
        colors.style.backgroundColor = "black";
      }
    },

     deleter(){
      let d = document.querySelectorAll('div');
      var last = d[d.length- 1];
      if (d.length != 1){
      last.remove();
      }
    },

     showhide(){
      var para = document.querySelector("p");
      if (para.style.display === "none"){
        para.style.display = "inline-block";
      }else{
        para.style.display = "none";
      }
    },

    words(){
      document.querySelector('h1').textContent = "something else";
      document.querySelector('p').textContent = "something else";
    }

  }
}
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
