<template>
  <div>
    <Header />
    <SideBar />
    <nuxt />
    <Footer />
  </div>
</template>

<script>
  import Header from '@/components/Header.vue'
  import SideBar from '@/components/SideBar.vue'
  import Footer from '@/components/Footer.vue'

  export default {
    name: 'Home',
    components: {
      Header,
      SideBar,
      Footer,
    },
    Computed: {}
  }
</script>
