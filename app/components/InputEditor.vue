<script setup lang="ts">
const { lang = 'json' } = defineProps<{
  lang?: string
}>()

const model = defineModel<string>({
  default: '',
})
</script>

<template>
  <div class="relative min-h-[600px]">
    <EditorToolbar
      :content="model"
      class="absolute top-0 left-0 z-10"
      @clear="model = ''"
    />
    <ClientOnly>
      <LazyBaseEditor
        v-model="model"
        :lang
      />
    </ClientOnly>
  </div>
</template>
