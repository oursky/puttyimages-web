<template>
  <v-app>
    <the-header />
    <metamask-dialog />
    <nuxt/>
  </v-app>
</template>

<script>
import MetamaskDialog from '@/components/MetamaskDialog';
import TheHeader from '@/components/TheHeader';

export default {
  components: {
    MetamaskDialog,
    TheHeader,
  },
};
</script>
