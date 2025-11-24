<template>
  <a
    :href="to"
    @click.prevent="$emit('click')"
    class="text-link"
    :class="{ 'highlight': highlight }"
  >
    <slot></slot>
  </a>
</template>

<script>
export default {
  name: 'TheLink',
  props: {
    to: { type: String, default: '#' },
    highlight: { type: Boolean, default: false } // Kırmızı renklendirme için
  },
  emits: ['click']
};
</script>

<style scoped>
.text-link {
  font-size: 12px;
  text-decoration: none;
  color: #777; /* Varsayılan koyu gri */
}

.highlight {
  color: #a00; /* Kırmızı renk */
}

.text-link:hover {
  text-decoration: underline;
}
</style>