<template>
 
  <HomeNavbar/>
  <router-view/>
</template>

<script>
import HomeNavbar from "./components/HomeNavbar.vue";

  export default {
    name: "App",
    components: { HomeNavbar }
}
</script>
<style>

</style>
