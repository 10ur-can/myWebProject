<template>
  <button
    :type="type"
    :disabled="disabled"
    @click="$emit('click')"
    :class="['base-button', { 'clicked-style': isClicked }]"
    @mousedown="isClicked = true"
    @mouseup="isClicked = false"
    @mouseleave="isClicked = false"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'TheButton',
  props: {
    type: { type: String, default: 'button' },
    disabled: { type: Boolean, default: false }
  },
  emits: ['click'],
  data() {
    return {
      // Butona basılıp basılmadığını takip eden durum
      isClicked: false
    };
  }
};
</script>

<style scoped>
.base-button {
  width:512px;
  padding:10px;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
  border: none;
  transition: background-color 0.1s ease;
  background-color: #a8a8a8;
  color: #fff;
}

</style>