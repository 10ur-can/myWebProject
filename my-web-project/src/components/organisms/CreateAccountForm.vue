<template>
  <form @submit.prevent="handleSubmit" class="create-account-organism">
    <h2 class="title">Hesap oluştur</h2>
    <p class="subtitle">Devam etmek için bilgilerinizi girin. Zaten bir hesabınız varsa, lütfen giriş yapın.</p>

    <NameInputGroup
      v-model:firstName="form.firstName"
      v-model:lastName="form.lastName"
      :error="nameError"
    />
    
    <FormInput
      id="email"
      label="E-posta adresi"
      type="email"
      v-model="form.email"
    />

    <FormInput
      id="phone"
      label="Telefon Numarası"
      type="tel"
      v-model="form.phone"
    />

    <FormInput
      id="password"
      label="Şifre"
      type="password"
      v-model="form.password"
    />

    <FormInput
      id="dob"
      label="Doğum Tarihi gg.aa.yyyy"
      type="date"
      v-model="form.dob"
    >
      <template #icon>
          <span class="date-icon">🗓️</span>
      </template>
    </FormInput>

    <CheckboxGroup 
      v-model:emailConsent="form.emailConsent"
      v-model:smsConsent="form.smsConsent"
    />

    <TheButton type="submit">
      HESAP OLUŞTUR
    </TheButton>

    <div class="separator">YA DA</div>

    <div class="sso-container">
      <SSOButton provider-name="Google" icon-src="/icons/google-icon.svg" @click="loginWithGoogle" />
      <SSOButton provider-name="Apple" icon-src="/icons/apple-icon.svg" @click="loginWithApple" />
    </div>
    
    <div class="login-prompt">
      Zaten hesabınız var mı?
      <TheLink highlight @click="handleLogin">
        GİRİŞ YAP
      </TheLink>
    </div>
  </form>
</template>

<script>
// Atomlar ve Moleküllerin doğru yollarını kullandığınızdan emin olun
import FormInput from '@/components/molecules/FormInput.vue'; 
import NameInputGroup from '@/components/molecules/NameInputGroup.vue'; 
import CheckboxGroup from '@/components/molecules/CheckboxGroup.vue';
import TheButton from '@/components/atoms/TheButton.vue';
import TheLink from '@/components/atoms/TheLink.vue';
import SSOButton from '@/components/molecules/SSOButton.vue';

export default {
  name: 'CreateAccountForm',
  components: {
    FormInput,
    NameInputGroup,
    CheckboxGroup,
    TheButton,
    TheLink,
    SSOButton
  },
  data() {
    return {
      form: {
        firstName: '',
        lastName: '',
        email: '',
        phone: '',
        password: '',
        dob: '',
        emailConsent: false,
        smsConsent: false
      },
      nameError: false // Örnek hata yönetimi
    };
  },
  methods: {
    handleSubmit() {
      // Basit validasyon kontrolü
      this.nameError = this.form.firstName.length < 2 || !/^[a-zA-ZğüşöçİĞÜŞÖÇ]+$/.test(this.form.firstName);
      
      if (this.nameError) {
          console.error('Lütfen Ad alanını kontrol edin.');
          return;
      }

      console.log('Hesap Oluşturma Verileri:', this.form);
      // Başarılı bir kayıttan sonra ana bileşene haber ver
      this.$emit('signupSuccess');
    },
    handleLogin() {
      // Login sayfasına geçişi tetikle (App.vue'da yakalanacak)
      this.$emit('goToLogin');
    },
    loginWithGoogle() { /* ... */ },
    loginWithApple() { /* ... */ }
  }
};
</script>

<style scoped>
.create-account-organism {
  width: 100%;
  max-width: 450px; 
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

/* Bu stiller LoginForm'daki ile aynı olabilir */
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
  margin-bottom: 20px;
}

.login-prompt {
    font-size: 14px;
}

.date-icon {
    position: absolute;
    right: 15px;
    top: 50%;
    transform: translateY(-50%);
    pointer-events: none; /* İkona tıklanmayı engellemek için */
}
</style>