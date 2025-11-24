<template>
    <headerSet></headerSet>
   <headerCom></headerCom>
   <dropdownMenu></dropdownMenu>
  <div class="login-page">
    <img v-bind:src="loginImage"></img>
    <LoginForm />
  </div>
  <footerPage></footerPage>
 
</template>

<script>
import LoginForm from '@/components/organisms/LoginForm1.vue'
import headerSet from '@/components/organisms/headerIcon.vue'
import headerCom from '@/components/organisms/header.vue'
import footerPage from '@/components/organisms/footer.vue'
import loginImage from '@/assets/images/loginimage.webp'
import dropdownMenu from '@/components/organisms/headerDropdown.vue'


export default {
  name: 'LoginPage',
  components: {
    'LoginForm' : LoginForm,
    'headerSet' : headerSet,
    'headerCom' : headerCom,
    'footerPage' : footerPage,
    'dropdownMenu': dropdownMenu  
  },

  data(){
    return{
      loginImage : loginImage
    }
  }
};

</script>

<style scoped>
.login-page {
  display:flex;
  justify-content: center;
  min-height: 100vh; /* Tüm ekranı kaplasın */
  background-color: #f9f9f9;
}

img{
  width:751.2px;
  height: 751.2px;
}


</style>