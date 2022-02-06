<template>
  <div class="main">
    <event-list v-for="event in filteredEvent" :key="event.eventname" 
      :name="event.eventname"
      :details="event.detail"
      :date="event.date"
    />
    <locFilterComponent what="Event" 
    @areaChanged="areaChanged" />
    <event-filter-component 
    @eventtypechanged="eventtypechanged"/>
  </div>
</template>

<script>
import eventList from '~/components/eventList.vue'
export default {
  components: {
    eventList,
  },
  data() {
    return {
      displayList: false,
      events: [
        {
          eventname: 'T20',
          eventtype: 'sport',
          detail: 'Cricket',
          area: 'lohegaon',
          date: '31/08/2022',
        },
        {
          eventname: 'Daaru Party',
          eventtype: 'party',
          detail: 'Free wine',
          area: 'lohegaon',
          date: '24/05/2022',
        },
        {
          eventname: 'Road Trip',
          eventtype: 'trip',
          detail: 'trip with 10 people enjoying the snacks',
          area: 'lohegaon',
          date: '02/06/2022',
        },
        {
          eventname: 'Clothes Exhibition',
          eventtype: 'exhibition',
          detail: 'Purchase quality clothes at minimum price',
          area: 'lohegaon',
          date: '11/03/2022',
        },
        {
          eventname: '18+ club ',
          eventtype: 'party',
          detail: 'xx iykyk',
          area: 'lohegaon',
          price: '15/04/2022',
        },
        {
          eventname: 'World Cup',
          eventtype: 'sport',
          detail: 'football',
          area: 'lohegaon',
          date: '26/07/2022',
        },
        {
          eventname: 'Valentine Exhibition',
          eventtype: 'exhibition',
          detail: 'Chance to meet your valentine',
          area: 'lohegaon',
          date: '04/08/2022',
        },
        {
          eventname: 'Flight Trip',
          eventtype: 'trip',
          detail: 'Lufthansa',
          area: 'lohegaon',
          date: '14/02/2022',
        },
      ],

      filteredEvent: [],
      filteredEventByarea: [],
      filteredEventByType: [],
    }
  },
  methods: {
    areaChanged(e) {
      this.filteredEventByarea = this.events.filter(
        (events) => events.area === e
      )
      this.filteredEvent = this.filteredEventByarea
      this.displayList = true
    },
    eventtypechanged(e) {
      console.log(e)
      this.filteredEventByType = this.filteredEventByarea.filter(
        (filteredEventByarea) => filteredEventByarea.eventtype === e
      )
      this.filteredEvent = this.filteredEventByType
    },
  },
}
</script>

<style scopped></style>
