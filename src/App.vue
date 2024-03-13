<script setup>
import RodaPe from '@/components/RodaPe.vue';
import RodaPeMobile from '@/components/RodaPeMobile.vue';
import { useScreen } from '@/composables/screen';
import { useMonitor } from '@/composables/monitor';

const {isMobile} = useScreen()

const { menu } = useMonitor();
</script>

<template>
  <div>
    <component :is="menu" />
    <main>
      <router-view />
    </main>
    <footer>

      <RodaPe v-if="!isMobile"/>

  <RodaPeMobile v-else/>
    </footer>
  </div>
</template>