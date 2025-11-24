<template>
    <headerSet></headerSet>
    <headerCom></headerCom>
  <div class="signup-page-container">
    <img v-bind:src="loginImage"></img>
    <CreateAccountForm @goToLogin="$emit('goToLogin')" @signupSuccess="$emit('signupSuccess')" />
  </div>
  <footerPage></footerPage>
</template>

<script>
import CreateAccountForm from '@/components/organisms/CreateAccountForm.vue';
import headerSet from '@/components/organisms/headerIcon.vue'
import headerCom from '@/components/organisms/header.vue'
import footerPage from '@/components/organisms/footer.vue'
import loginImage from '@/assets/images/loginimage.webp'

export default {
  name: 'SignupPage',
  components: {
    CreateAccountForm,
    headerSet,
    headerCom,
    footerPage,
  },

  data(){
    return{
      loginImage : loginImage
    }
  },

  emits: ['goToLogin', 'signupSuccess']
};
</script>

<style scoped>
.signup-page-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f7f7f7;
  padding:0px;
  margin: 0px;
}

img{
  position: relative;
  top:-5px;
  left:0px;
  width:851.2px;
  height:935.2px;
  padding:0px;
}
</style>