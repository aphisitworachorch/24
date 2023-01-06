<template>
  <div class="text-center hero min-h-screen">
    <div class="hero-content">
      <div class="container">
        <div class="flex flex-col md:flex-row m-3">
          <img src="../assets/25V2.svg" class="max-w-screen items-center light:invert lg:w-72" @click="confetti"/>
          <div class="mockup-code text-left p-3">
            <pre data-prefix="1"><code>let mybirthday: BirthdayDto = {};</code></pre>
            <pre data-prefix="2"><code>mybirthday = {</code></pre>
            <pre data-prefix="3" class="text-success"><code>  "message": "{{ message['message'] }}",</code></pre>
            <pre data-prefix="4" class="text-success"><code>  "additional": "{{ message['additional'] }}"</code></pre>
            <pre data-prefix="5" class="text-success"><code>  "age": {{ message['age'] }}</code></pre>
            <pre data-prefix="6" class="text-success"><code>  "born_in": "{{ message['born_in'] }}"</code></pre>
            <pre data-prefix="7"><code>};</code></pre>
            <pre data-prefix="8"><code>console.log(mybirthday);</code></pre>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>

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
        "born_in": dateTime.getFullYear()
      }
    }
  },
  methods:{
    confetti: function(){
      (this as any).$confetti.start({
        particles: [
          {
            type: 'heart',
          },
          {
            type: 'circle'
          }
        ],
        defaultDropRate: 30,
        defaultSize: 20,
        defaultColors: [
          '#ffdf00',
          '#d4af37',
          '#996515'
        ],
      });
      setTimeout(()=>{
        (this as any).$confetti.stop();
      },20000);
    }
  },
  mounted() {
    console.log({
      "message": this.message.message,
      "additional": this.message.additional,
      "age": this.message.age,
      "born_in": this.message.born_in
    })
  }
})
</script>
