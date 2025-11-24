<template>
  <div class="checkbox-group">
    <p class="kvkk-text">
      ⓘ 6698 sayılı Kişisel Verilerin Korunması Kanunu kapsamında Üye Aydınlatma Metni'mize
      <TheLink to="#" highlight>buradan</TheLink> ulaşabilirsiniz.
    </p>
    
    <div class="checkbox-item">
      <input type="checkbox" id="email-consent" :checked="emailConsent" @change="$emit('update:emailConsent', $event.target.checked)">
      <label for="email-consent">
        Moda haberleri, yeni trendler, tanıtım ve kampanyalar hakkında **E-posta** aracılığıyla bilgilendirilmek istiyorum.
        Elektronik Ticari İleti Aydınlatma Metni'mize <TheLink to="#" highlight>buradan</TheLink> ulaşabilirsiniz.
        Tarafımla iletişim kurulmasına izin veriyorum.
      </label>
    </div>

    <div class="checkbox-item">
      <input type="checkbox" id="sms-consent" :checked="smsConsent" @change="$emit('update:smsConsent', $event.target.checked)">
      <label for="sms-consent">
        Moda haberleri, yeni trendler, tanıtım ve kampanyalar hakkında **SMS** aracılığıyla bilgilendirilmek istiyorum.
        Elektronik Ticari İleti Aydınlatma Metni'mize <TheLink to="#" highlight>buradan</TheLink> ulaşabilirsiniz.
        Tarafımla iletişim kurulmasına izin veriyorum.
      </label>
    </div>
  </div>
</template>

<script>
import TheLink from '@/components/atoms/TheLink.vue';

export default {
  name: 'CheckboxGroup',
  components: {
    TheLink
  },
  props: {
    emailConsent: { type: Boolean, default: false },
    smsConsent: { type: Boolean, default: false }
  },
  emits: ['update:emailConsent', 'update:smsConsent']
};
</script>

<style scoped>
.checkbox-group {
  margin: 25px 0;
  text-align: left;
}

.kvkk-text {
  font-size: 13px;
  color: #666;
  margin-bottom: 20px;
}

.checkbox-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 15px;
}

.checkbox-item input[type="checkbox"] {
  margin-top: 5px;
  flex-shrink: 0;
}

.checkbox-item label {
  font-size: 13px;
  color: #333;
  margin-left: 10px;
}
/* Linklerin içindeki bold metinler için */
.checkbox-item label :deep(b) { 
  font-weight: bold;
}
</style>