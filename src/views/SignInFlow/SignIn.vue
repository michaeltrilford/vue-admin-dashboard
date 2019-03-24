<template>
  <div class="container">
    <p class="request">
      Don't have a Design+HQ account?
      <router-link to="/request">Request an account</router-link>
    </p>
    <div class="login">
      <img src="@/assets/DCHQ-dark.svg" alt>
      <h4>Sign into Design+Code HQ</h4>
      <input type="email" placeholder="Email">
      <input type="password" placeholder="Password">
      <button>Sign in</button>
      <router-link to="/recover">Forgot your password?</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "SignIn"
};
</script>

<style scoped lang="sass">
  .container
    display: flex
    justify-content: center
    align-items: center
    min-height: 100vh

  .request
    margin: 0
    position: absolute
    top: 24px
    right: 24px
    color: rgba(255, 255, 255, 0.3)
    a
      color: white

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
    background: #56CCF2
    box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.2)
    border-radius: 4px
    height: 60px
    width: 100%
    font-size: 20px
    margin-top: 20px
    border: none
    margin-bottom: 40px

  a
    line-height: 25px
    text-align: center
    color: rgba(255, 255, 255, 0.3)
    text-decoration: none

</style>