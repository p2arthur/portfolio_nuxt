<!-- @format -->

<script setup lang="ts">
  interface modeIconsInterface {
    system: string;
    dark: string;
    light: string;
  }

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
    if (currentMode + 1 === modes.length) {
      nextMode = 0;
    } else {
      nextMode = currentMode + 1;
    }
    return modes[nextMode!];
  });

  const setColorMode = () => {
    colorMode.preference = nextMode.value;
  };
</script>

<template>
  <button @click="setColorMode">set to {{ nextModeIcons[nextMode] }}</button>
</template>

<style scoped lang="scss"></style>
