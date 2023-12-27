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
  <Bounded as="header" class="!py-4 md:!py-6 lg:!py-8">
    <div class="flex gap-4 items-center justify-between flex-col sm:flex-row">
      <Logo />
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
