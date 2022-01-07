<template>
  <div class="text-center">
    <h1 class="text-2xl" @click="confetti">
      🎉
    </h1>
    {{ message }}
  </div>
</template>

<style>
@tailwind base;
@tailwind utilities;
@tailwind components;
</style>
<script lang="ts">
import Vue from 'vue'
import { createSEOMeta } from '~/constants/seo';
const dateTime : Date = new Date(1998,0,7,15,30);
const age : Number = Number(new Date().getFullYear()) - Number(dateTime.getFullYear());
export default Vue.extend({
  data: function () {
    return {
      message: {
        "message":"Happy Birthday to Me !",
        "additional":`🎉🎉🎉🎉🎉🎉🎉`,
        "age":age,
        "born_in":dateTime.getFullYear()
      }
    }
  },
  methods:{
    confetti: function(){
      (this as any).$confetti.start();
      setTimeout(()=>{
        (this as any).$confetti.stop();
      },20000);
    }
  },
})
</script>
