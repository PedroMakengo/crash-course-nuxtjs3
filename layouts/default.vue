<script lang="ts">
import { useSettings } from '../composables/useSettings'

export default {
  setup() {
    // Variables
    const settings = useSettings()
    const { asImageSrc } = usePrismic()

    // Functions
    useSeoMeta({
      title: settings.value?.data.site_title,
      description: settings.value?.data.meta_description,
      ogImage: asImageSrc(settings.value?.data.og_image),
    })
    return { settings }
  },
}
</script>

<template>
  <div>
    <Header />
    <slot />
    <Footer />
    <div
      class="fixed inset-0 bg-gradient-to-tr from-emerald-50 to-cyan-50 z-[-1] opacity-50"
    />
  </div>
</template>
