<template>
  <div class="name-input-group">
    <TheInput
      id="firstName"
      label="Ad"
      type="text"
      :modelValue="firstName"
      @update:modelValue="$emit('update:firstName', $event)"
    />
    <TheInput
      id="lastName"
      label="Soyad"
      type="text"
      :modelValue="lastName"
      @update:modelValue="$emit('update:lastName', $event)"
    />
  </div>
  <p v-if="error" class="error-message">
    En az 2 karakter olmalı ve sadece harf içermelidir.
  </p>
</template>

<script>
import TheInput from '@/components/atoms/TheInput.vue';

export default {
  name: 'NameInputGroup',
  components: {
    TheInput
  },
  props: {
    firstName: { type: String, default: '' },
    lastName: { type: String, default: '' },
    error: { type: Boolean, default: false } // Hata durumunu yönetmek için
  },
  emits: ['update:firstName', 'update:lastName']
};
</script>

<style scoped>
.name-input-group {
  display: flex;
  gap: 15px; /* İki alan arasına boşluk */
  margin-bottom: 5px;
}

/* TheInput.vue içindeki .input-container'ı hedefleyerek genişliği bölmek */
.name-input-group > :deep(.input-container) {
  flex: 1;
}

.error-message {
  color: #a00;
  font-size: 13px;
  text-align: left;
  margin-top: 0;
  margin-bottom: 15px;
  padding-left: 10px;
}
</style>