<template>
  <button class="sso-button" @click="$emit('click')">
    <img :src="iconSrc" :alt="providerName" class="sso-icon" />
  </button>
</template>

<script>
import googlelogo from '@/assets/images/googlelogo.png';

export default {
  name: 'SSOButton',
  props: {
    providerName: { type: String, required: true },
  },
  data(){
    return{
     iconSrc : googlelogo
     
    }
  },

  emits: ['click']
};
</script>

<style scoped>
.sso-button {
  width: 40px;
  height: 40px;
  background-color: #fff;
  border: 1px solid #ccc;
  border-radius: 50%;
  margin: 0 5px;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  transition: border-color 0.2s;
}

.sso-button:hover {
  border-color: #888;
}

.sso-icon {
  width: 20px;
  height: 20px;
}
</style>