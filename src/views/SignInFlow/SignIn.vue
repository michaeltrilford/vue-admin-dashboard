<template>
  <div
    class="container"
    :class="{'light-background' : !isDarkMode, 'dark-background' :  isDarkMode }"
  >
    <RequestAccount/>
    <div class="login">
      <img src="@/assets/DCHQ.svg" v-show="isDarkMode">
      <img src="@/assets/DCHQ-dark.svg" v-show="!isDarkMode">
      <h4 :class="{'light-text' : isDarkMode, 'dark-text' : !isDarkMode}">Sign into Design+Code HQ</h4>
      <input
        :class="{'light-field' : isDarkMode, 'dark-field' : !isDarkMode}"
        type="email"
        placeholder="Email"
      >
      <input
        :class="{'light-field' : isDarkMode, 'dark-field' : !isDarkMode}"
        type="password"
        placeholder="Password"
      >
      <button :class="{'dark-button' : isDarkMode, 'light-button' : !isDarkMode}">Sign in</button>
      <router-link
        :class="{'light-link' : !isDarkMode, 'dark-link' :  isDarkMode }"
        to="/recover"
      >Forgot your password?</router-link>
      <button
        :class="{'dark-button' : isDarkMode, 'light-button' : !isDarkMode}"
        @click="toggleDarkMode"
      >Toggle</button>
    </div>
  </div>
</template>

<script>
import * as netlifyIdentityWidget from "netlify-identity-widget";

import RequestAccount from "@/components/RequestAccount";

export default {
  name: "SignIn",
  components: {
    RequestAccount
  },
  computed: {
    isDarkMode() {
      return this.$store.getters.isDarkMode;
    }
  },
  methods: {
    toggleDarkMode() {
      this.$store.commit("toggleDarkMode");
    }
  },
  mounted() {
    netlifyIdentityWidget.open();
  }
};
</script>

<style scoped lang="sass">

  .light-background
    background-color: $light-gray

  .dark-background
    background-color: $dark-blue 

  .light-text
    color: $white

  .dark-text
    color: $black

  .light-field
    background: rgba(255,255,255,0.2)
    border: 1px solid rgba(255,255,255,0.2)
    &::placeholder
      color: rgba(255,255,255,0.3)

  .dark-field
    background: rgba(198,208,235,0.2)
    border: 1px solid rgba(0,0,0,0.2)
    &::placeholder
      color: rgba(0,0,0,0.3)

  .light-link
    color: rgba(0, 0, 0, 0.3)

  .dark-link
    color: rgba(255, 255, 255, 0.3)

  .container
    display: flex
    justify-content: center
    align-items: center
    min-height: 100vh

  .login
    width: 400px

  h4
    margin: 0
    line-height: 34px
    font-size: 24px
    text-align: center
    color: #FFFFFF
  
  input
    background: rgba(255, 255, 255, 0.2)
    border: 1px solid rgba(255, 255, 255, 0.2)
    box-sizing: border-box;
    border-radius: 4px;
    height: 60px
    width: 100%
    font-size: 20px
    color: white
    padding-left: 20px
    margin-top: 20px
    &::placeholder
      color: rgba(255, 255, 255, 0.3)

  button
    border-radius: 4px
    height: 60px
    width: 100%
    font-size: 20px
    margin-top: 20px
    border: none
    margin-bottom: 40px

  .light-button
    background: #2470f5
    color: $white
    box-shadow: 0px 0px 20px rgba(#2470f5, 0.2)

  .dark-button
    background: #56CCF2
    color: $dark-blue
    box-shadow: 0px 0px 20px rgba($dark-blue, 0.2)


  a
    line-height: 25px
    text-align: center
    text-decoration: none

</style>