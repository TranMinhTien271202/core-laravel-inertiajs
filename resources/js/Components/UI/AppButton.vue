<script setup>
const props = defineProps({
  label: {
    type: String,
    required: false,
  },
  color: {
    type: String,
    default: 'primary'
  },
  large: {
    type: Boolean,
    default: false
  },
  small: {
    type: Boolean,
    default: false
  },
  rounded: {
    type: Boolean,
    required: false
  },
  outlined: {
    type: Boolean,
    required: false
  }
});
</script>

<template>
  <button
    :class="['btn',
      `btn-${color}`,
      {'btn-rounded': rounded},
      {'btn-large': large},
      {'btn-small': small},
      outlined ? `color-${color} btn-outlined` : ''
      ]">
    {{ label }}
    <slot/>
  </button>
</template>
