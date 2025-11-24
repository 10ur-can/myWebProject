<template>
  <TheInput
    :id="id"
    :label="label"
    :type="inputType"
    :placeholder="placeholder"
    :modelValue="modelValue"
    @update:modelValue="$emit('update:modelValue', $event)"
  >
    <template v-if="isPassword" #icon>
      <span class="password-toggle" @click="togglePasswordVisibility">
        {{ isVisible ? '' : '' }}
      </span>
    </template>
  </TheInput>
</template>

<script>
import TheInput from '@/components/atoms/TheInput.vue';

export default {
  name: 'FormInput',
  components: {
    TheInput
  },
  props: {
    id: { type: String, required: true },
    label: { type: String, default: '' },
    type: { type: String, default: 'text' },
    placeholder: { type: String, default: '' },
    modelValue: { type: [String, Number], default: '' }
  },
  emits: ['update:modelValue'],
  data() {
    return {
      isVisible: false,
      inputType: this.type
    };
  },
  computed: {
    isPassword() {
      return this.type === 'password';
    }
  },
  methods: {
    togglePasswordVisibility() {
      this.isVisible = !this.isVisible;
      this.inputType = this.isVisible ? 'text' : 'password';
    }
  },
  watch: {
    // Prop değiştiğinde local inputType'ı güncel tutar
    type(newType) {
      this.inputType = newType;
    }
  }
};
</script>

<style scoped>
.password-toggle {
  position: absolute;
  right: 15px;
  top: 50%; /* Dikey ortalamak için */
  transform: translateY(-50%);
  cursor: pointer;
  font-size: 18px;
  z-index: 2;
  /* Göz ikonunun yerleşimi için molekül içindeki .text-input'ın yüksekliğini hesaba katın */
}
</style>