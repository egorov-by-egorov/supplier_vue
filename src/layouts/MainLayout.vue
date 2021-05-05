<template>
  <div class="app-main-layout">
    <Header @click="isOpenSidebar = !isOpenSidebar"/>
    <Sidebar v-model="isOpenSidebar"/>

    <main class="app-content" :class="{full: !isOpenSidebar}">
      <div class="app-page">
        <router-view/>
      </div>
    </main>

    <div class="fixed-action-btn">
      <router-link class="btn-floating btn-large blue" to="/record">
        <i class="large material-icons">add</i>
      </router-link>
    </div>
  </div>
</template>

<script>
import Header from "../components/Header/Header";
import Sidebar from "../components/Sidebar/Sidebar";
export default {
  name: "MainLayout",
  data: () => ({
    isOpenSidebar: true
  }),
  components: {
    Header, Sidebar
  }
}
</script>

<style scoped>

</style>
