<script lang="ts">
import { useSettings } from '../composables/useSettings'

export default {
  setup() {
    const settings = useSettings()

    return { settings }
  },
}
</script>

<template>
  <Bounded as="footer" class="!py-4 md:!py-6 lg:!py-8 bg-white">
    <div class="flex gap-4 items-center justify-between flex-col sm:flex-row">
      <Logo />
      <p class="text-xs">
        ©{{ new Date().getFullYear() }} {{ settings?.data.site_title }}
      </p>
      <nav>
        <ul class="flex">
          <li v-for="(item, index) in settings?.data.navigation" :key="index">
            <PrismicLink :field="item.link" class="p-4">
              {{ item.label }}
            </PrismicLink>
          </li>
        </ul>
      </nav>
    </div>
  </Bounded>
</template>
