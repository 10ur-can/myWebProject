<template>
  <button :class="['btn', type]" @click="$emit('click')">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    type: { // 'primary' (KEŞFET) veya 'secondary' (navigasyon okları için)
      type: String,
      default: 'primary'
    }
  }
}
</script>

<style scoped>
.btn {
  border-radius: 50%;
  cursor: pointer;
  font-weight: bold;
  transition: background-color 0.3s;
}

.btn.primary {
  background-color: white;
  color: #c0392b; /* Kırmızı ton */
  font-size: 16px;
}

.btn.primary:hover {
  background-color: #f0f0f0;
}

.btn.secondary {
  background-color: rgba(0, 0, 0, 0.3);
  color: white;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  line-height: 1;
  padding: 0;
}
</style>