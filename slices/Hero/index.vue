<script setup lang="ts">
import { type Content } from '@prismicio/client'

// The array passed to `getSliceComponentProps` is purely optional.
// Consider it as a visual hint for you when templating your slice.
defineProps(
  getSliceComponentProps<Content.HeroSlice>([
    'slice',
    'index',
    'slices',
    'context',
  ])
)
</script>

<template>
  <Bounded
    :data-slice-type="slice.slice_type"
    :data-slice-variation="slice.variation"
  >
    <div class="grid grid-cols-1 place-items-center">
      <div class="flex flex-col items-center text-center">
        <PrismicRichText
          :field="slice.primary.heading"
          class="heading heading--xl"
        />
        <PrismicRichText :field="slice.primary.body" class="description" />

        <PrismicLink :field="slice.primary.button_link" class="button">
          {{ slice.primary.button_text }}
        </PrismicLink>
      </div>
      <PrismicImage :field="slice.primary.image" class="image" />
    </div>
  </Bounded>
</template>
