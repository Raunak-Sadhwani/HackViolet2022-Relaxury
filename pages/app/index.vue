<template>
  <section class="main">
    <div
      style="background: linear-gradient(#ba7edd 9%, #ffffff 40%)"
      v-if="onHomePage"
    >
      <home>
      </home>
    </div>
    
  </section>
</template>

<script>
import FilterComponent from '~/components/serviceFilterComponent.vue'
import HeaderComponent from '~/components/headerComponent.vue'
import Home from '~/components/home.vue'
import serviceListComponent from '~/components/ServiceListComponent.vue'
import LocFilterComponent from '~/components/locFilterComponent.vue'
import registerForm from '~/components/serviceRegisterForm.vue'

export default {

  components: {
    registerForm,
    Home,
    HeaderComponent,
    serviceListComponent,
    LocFilterComponent,
    FilterComponent,
  },

  name: 'App',
  data() {
    return {
      onHomePage: true,
      
    }
  },
  methods: {
    serviceClicked() {
      this.onHomePage = !this.onHomePage
      this.onServicePage = !this.onServicePage
      this.$Router.push('/service')
    },
    homeClicked() {
      this.onHomePage = false
      this.onServicePage = false
      this.$Router.push('/')
    },
    clicked(name) {
      this.onDetailsPage = true
      this.onServicePage = false
      this.onHomePage = false
      // console.log(name);
      this.detailsOf = this.cooks.find((cook) => cook.name === name)
      // console.log(this.detailsOf);
    },
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  font-family: 'Poppins', sans-serif;
  color: black;
}
</style>
