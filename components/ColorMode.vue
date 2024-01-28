<!-- @format -->

<script setup lang="ts">
  interface modeIconsInterface {
    [key: string]: string;
    system: string;
    dark: string;
    light: string;
  }

  const showNextModeLabel = ref(false);

  const colorMode = useColorMode();

  const modes = ['system', 'light', 'dark'];

  const nextModeIcons: modeIconsInterface = {
    system: '🌓',
    dark: '🌑',
    light: '🌕',
  };

  const nextMode = computed(() => {
    const currentMode = modes.indexOf(colorMode.preference);
    let nextMode = null;
    currentMode + 1 === modes.length
      ? (nextMode = 0)
      : (nextMode = currentMode + 1);

    return modes[nextMode!];
  });

  const nextModeIcon = computed(() => {
    return nextModeIcons[nextMode.value];
  });

  const setColorMode = () => {
    colorMode.preference = nextMode.value;
  };
</script>

<template>
  <div class="flex relative w-32 justify-end">
    <div
      class="text-gray-500 text-xs"
      v-if="showNextModeLabel">
      Change to {{ nextMode }}
    </div>
    <button
      @mouseenter="showNextModeLabel = true"
      @mouseleave="showNextModeLabel = false"
      class="hover:bg-gray-100 dark:hover:bg-gray-400 px-2 py-1 text-gray-500"
      @click="setColorMode">
      {{ nextModeIcon }}
    </button>
  </div>
</template>

<style scoped lang="scss"></style>
