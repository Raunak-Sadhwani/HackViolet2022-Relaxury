<template>
  <div class="main">
    <div v-if="displayList">
      <service-list-component
        v-for="service in filteredService"
        :key="service.company"
        :name="service.company"
        :detail="service.detail"
        :price="service.price"
        :rating="service.rating"
      />
    </div>
    <h1 v-else>*Select Required Location</h1>
    <locFilterComponent what="Services" @areaChanged="areaChanged" />
    <filter-component
      @servicetypechanged="servicetypechanged"
      @pricechanged="pricechanged"
    />
  </div>
</template>

<script>
import filterComponent from '~/components/serviceFilterComponent.vue'
import locFilterComponent from '~/components/locFilterComponent.vue'
import ServiceListComponent from '~/components/ServiceListComponent.vue'

export default {
  components: {
    filterComponent,
    locFilterComponent,
    ServiceListComponent,
  },

  data() {
    return {
      displayList: false,

      service: [
        {
          servicename: 'laundry',
          company: 'dhoneawala',
          detail: 'laundry service with love',
          area: 'lohegaon',
          price: 7900,
          rating: 4.0,
        },
        {
          servicename: 'homeservice',
          detail: 'home cleaning services',
          company: '5 Star services',
          area: 'lohegaon',
          price: 14000,
          rating: 5.0,
        },
        {
          servicename: 'cook',
          company: 'Sanjeev Kapoor',
          detail: 'Everyday special meals',
          area: 'lohegaon',
          price: 7000,
          rating: 4.5,
        },
        {
          servicename: 'spa',
          company: ' Vintage Massage',
          detail: 'Masseure, Facial, Body, etc',
          area: 'lohegaon',
          price: 11000,
          rating: 4.7,
        },
        {
          servicename: 'homeservice',
          company: 'Classic Home Services',
          detail: 'Clean, maintain, repair',
          area: 'lohegaon',
          price: 7800,
          rating: 4.2,
        },
         {
          servicename: 'spa',
          company: 'Sauna spa',
          detail: 'Fully Steam, Massage, etc',
          area: 'lohegaon',
          price: 11000,
          rating: 5.0,
        },
        {
          servicename: 'laundry',
          company: 'Polite Laundry',
          detail: 'laundry service with extra cleaning',
          area: 'lohegaon',
          price: 8900,
          rating: 4.0,
        },
        {
          servicename: 'cook',
          company: 'Robert Browney',
          detail: 'Speciality in Italian Cuisine',
          area: 'lohegaon',
          price: 7000,
          rating: 4.5,
        },
      ],
      
      
      filteredService: [],
      filteredServiceByarea: [],
      filteredServiceByType: [],
      filteredServiceByPrice: [],
    }
  },
  methods: {
    areaChanged(e) {
      this.filteredServiceByarea = this.service.filter(
        (service) => service.area === e
      )
      this.filteredService = this.filteredServiceByarea
      this.displayList = true
    },
    servicetypechanged(e) {
      console.log(e)
      this.filteredServiceByType = this.filteredServiceByarea.filter(
        (filteredServiceByarea) => filteredServiceByarea.servicename === e
      )
      this.filteredService = this.filteredServiceByType
    },
    pricechanged(e) {
      this.filteredServiceByPrice = this.filteredServiceByType.filter(
        (filteredServiceByType) => filteredServiceByType.price <= e
      )
      this.filteredService = this.filteredServiceByPrice
    },
  },
}
</script>

<style scoped>

  h1{
    text-align: center;
    font-size: 20px;
    font-weight: bold;
  }

</style>
