<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <vue-recaptcha
      @verify="onVerify"
      sitekey="6Lfe33gUAAAAAMCuDwRfhSUV4sGkqGDaGrKqjkmZ">
      <button type="submit" v-on:click="whenSubmit">Submit</button>
    </vue-recaptcha>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import VueRecaptcha from 'vue-recaptcha';

export default {
  name: 'home',
  components: {
    HelloWorld,
    VueRecaptcha,
  },
  methods: {
    onVerify(key) {
      console.log('verifed');
      console.log(key);
      grecaptcha.execute()
    },
    whenSubmit() {
      console.log('something');
    }
  }
}
</script>
