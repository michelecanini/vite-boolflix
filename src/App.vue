<script>

import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue';
import AppCard from './components/AppCard.vue';

export default {
    components: {
        AppHeader,
        AppMain,
        AppCard
    }
}

</script>

<template lang="">

  <div>
    <AppHeader />
    <AppMain />
    <AppCard />
  </div>

</template>

<style lang="scss">

    @import './styles/generals.scss';
    @import '../node_modules/bootstrap/scss/bootstrap';

</style>
