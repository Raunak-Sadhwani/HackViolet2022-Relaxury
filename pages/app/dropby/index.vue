<template>
  <div class="main">
    <event-list v-for="event in shortedDropBy" :key="event.company" 
      :name="event.company"
      :details="event.details"
      :date="'Opens-'+event.time"
    />
    <locFilterComponent what="Drop By" 
    @locationChanged="locationChanged"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      dropby: [
        {
          company: 'chai wale',
          dropbytype: 'cafe',
          detail: ' chai peelo friends ',
          area: 'lohegaon',
          rating: 3.5,
          time: '12:00',
        },
        {
          company: 'kirana',
          dropbytype: 'shop',
          detail: ' stationary ',
          area: 'lohegaon',

        },
        {
          company: 'free massage wala',
          dropbytype: 'spa',
          detail: ' malamal massage ',
          area: 'lohegaon',
          rating: 5.5,
        },
      ],

      shortedDropBy: [],
    }
  },
  methods: {
    locationChanged(location) {
    //   this.shortedDropBy = this.dropby.filter((dropby) => dropby.area === location);

       this.shortedDropBy = this.dropby.filter(
        (dropby) => dropby.eventtype === location
      )
      this.filteredEvent = this.filteredEventByType
    },
    },

}
</script>

<style>
</style>