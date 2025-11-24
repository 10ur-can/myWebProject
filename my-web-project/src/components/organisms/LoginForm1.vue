<template>
  <form @submit.prevent="handleSubmit" class="login-form-organism">
    <h2 class="title">Giriş Yap</h2>
    <p class="subtitle">Hesabınız varsa lütfen giriş yapın.</p>

    <FormInput
      id="email"
      label="E-posta adresi"
      type="email"
      v-model="email"
      placeholder=""
    />

    <FormInput
      id="password"
      label="Şifre"
      type="password"
      v-model="password"
      placeholder=""
    />

    <TheButton type="submit" @click="handleSubmit">
      OTURUM AÇ
    </TheButton>

    <div class="links-container">
      <TheLink highlight @click="handleForgotPassword">
        ŞİFRENİZİ Mİ UNUTTUNUZ?
      </TheLink>

      <div class="signup-prompt">
        Hesabınız yok mu?
        <TheLink highlight @click="handleSignup">
          HESAP OLUŞTUR
        </TheLink>
      </div>
    </div>

    <div class="separator">YA DA</div>

    <div class="sso-container">
      <SSOButton provider-name="Google" v-bind:src="googlelogo" @click="loginWithGoogle" />
      <SSOButton provider-name="Apple" icon-src="/icons/apple-icon.svg" @click="loginWithApple" />
      </div>
  </form>
</template>

<script>
import FormInput from '@/components/molecules/FormInput.vue';
import TheButton from '@/components/atoms/LoginButton.vue'
import TheLink from '@/components/atoms/TheLink.vue';
import SSOButton from '@/components/molecules/SSOButton.vue';

export default {
  name: 'LoginForm',
  components: {
    FormInput,
    TheButton,
    TheLink,
    SSOButton
  },
  data() {
    return {
      email: '',
      password: ''
    };
  },
  methods: {
    handleSubmit() {
      // Form gönderildiğinde yapılacak işlemler (örn. API çağrısı)
      console.log('Giriş Denemesi:', this.email, this.password);
      // Başarılı/başarısız durumlarını yönetin
    },
    handleForgotPassword() {
      console.log('Şifremi unuttum tıklandı');
    },
    handleSignup() {
      console.log('Hesap oluştur tıklandı');
    },
    loginWithGoogle() {
      console.log('Google ile giriş tıklandı');
    },
    loginWithApple() {
      console.log('Apple ile giriş tıklandı');
    }
  }
};
</script>

<style scoped>
.login-form-organism {
  width: 100%;
  max-width: 512px; /* Formun boyutunu sınırlayın */
  margin: 0 auto;
  padding: 20px;
  text-align: center;
}

.title {
  font-size: 28px;
  margin-bottom: 5px;
}

.subtitle {
  font-size: 16px;
  margin-bottom: 30px;
  color: #666;
}

.links-container {
  margin-top: 25px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.signup-prompt {
  margin-top: 10px;
  font-size: 14px;
}

.separator {
  margin: 30px 0 20px 0;
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 14px;
  color: #777;
}

.separator::before,
.separator::after {
  content: '';
  flex: 1;
  border-bottom: 1px solid #ddd;
}

.separator:not(:empty)::before {
  margin-right: 0.25em;
}

.separator:not(:empty)::after {
  margin-left: 0.25em;
}

.sso-container {
  display: flex;
  justify-content: center;
  gap: 10px;
}
</style>