<script setup lang="ts">
import {NThemeEditor, NConfigProvider} from 'naive-ui'

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const NThemeVisible = ref(false)
onMounted(() => {
  NThemeVisible.value = true
})
</script>

<template>
  <NThemeEditor v-if="NThemeVisible">
    <NConfigProvider>
      <NMessageProvider>
        <AppHeader />
        <div class="pages-slot pt-48px">
          <slot />
        </div>
      </NMessageProvider>
    </NConfigProvider>
  </NThemeEditor>
</template>

<style>
body {
  overflow-x: hidden;
}
</style>