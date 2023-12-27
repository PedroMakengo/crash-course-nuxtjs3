<script lang="ts">
export default {
  props: {
    as: {
      type: String,
      required: false,
    },
  },
  setup(props) {
    return { props }
  },
}
</script>

<template>
  <Component
    :is="props.as || 'section'"
    class="px-4 py-10 md:py-14 md:px-6 lg:py-16"
  >
    <div class="max-w-6xl w-full mx-auto">
      <slot />
    </div>
  </Component>
</template>
