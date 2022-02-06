<template>
  <section id="location">
    <div class="row1">
      <select name="type" @change="typechanged($event)">
        <option value="">{{ what }}</option>
        <option value="services">Services</option>
        <option value="dropby">Drop By</option>
        <option value="events">Events</option>
      </select>
      <select name="location" @change="locationChanged($event)">
        >
        <option value="">Select Location</option>
        <option value="pune">Pune</option>
        <option value="mumbai">Mumbai</option>
        <option value="banglore">Bangalore</option>
        <option value="chennai">Chennai</option>
      </select>
      <select name="area" @change="areaChanged($event)">
        <option v-for="area in areas" :key="area.id" :value="area.name">
          {{ area.name }}
        </option>
      </select>
    </div>
  </section>
</template>

<script>
export default {
  props: ['what'],
  methods: {
    typechanged(e) {
      this.$router.push({
        path: '/app/' + e.target.value,
      })
    },
  },
  data() {
    return {
      areas: [],
      puneArea: [
        {
          id: '1',
          name: 'viman nagar',
        },
        {
          id: '2',
          name: 'lohegaon',
        },
        {
          id: '3',
          name: 'swarget',
        },
        {
          id: '4',
          name: 'budhwar peth',
        },
      ],
      mumbaiArea: [
        {
          id: '1',
          name: 'dadar',
        },
        {
          id: '2',
          name: 'warli',
        },
        {
          id: '3',
          name: 'station',
        },
        {
          id: '4',
          name: 'andheri',
        },
      ],
      bangloreArea: [
        {
          id: '1',
          name: 'jayanagar',
        },
        {
          id: '2',
          name: 'rajajinagar',
        },
        {
          id: '3',
          name: 'airport',
        },
        {
          id: '4',
          name: 'bus-stand',
        },
      ],
      chennaiArea: [
        {
          id: '1',
          name: 'mylapore',
        },
        {
          id: '2',
          name: 'chromepet',
        },
        {
          id: '3',
          name: 'chetpet',
        },
        {
          id: '4',
          name: 'teynampet',
        },
      ],
    }
  },
  methods: {
    locationChanged(e) {
      if (e.target.value === 'pune') {
        this.areas = this.puneArea
      } else if (e.target.value === 'mumbai') {
        this.areas = this.mumbaiArea
      } else if (e.target.value === 'banglore') {
        this.areas = this.bangloreArea
      } else if (e.target.value === 'chennai') {
        this.areas = this.chennaiArea
      }
    },
    areaChanged(e) {
      console.log(e.target.value)
      this.$emit('areaChanged', e.target.value)
    },
  },
}
</script>

<style scopped>
select {
  text-align: center;
  border: none;
  background-color: rgba(43, 43, 43, 0.945);
color: violet;

  margin-left: auto;
  margin-right: auto;
  margin-top: 2rem;
  margin-bottom: 2rem;
  width: 18rem;
  height: 2.5rem;
  font-weight: 600;
  font-size: 1.5rem;
  border-radius: 1.5rem;
  background-position: right 1rem;
}
select i {
  margin-right: 5rem;

}

.row1 {
  display: flex;
  flex-direction: column;
  border-radius: 20px;

  background-color: rgba(238, 130, 238, 0.353);

  width: 339px;
  height: 313px;
  margin-left: 3rem;
  margin-right: 4rem;
  margin-top: 2rem;
  margin-bottom: 0;
  margin: 4 0rem;
  justify-content: space-around;
  align-items: center;
}
.col1 {
  display: flex;
  justify-content: space-between;
  align-items: center;
  align-content: center;
  text-align: center;
  
  margin: auto;
  width: 291px;
  height: max-content;
  padding: 10px;
  padding-left: 20px;
  border-radius: 20px;
}
.col1 img {
  width: 25px;
  height: 25px;
  cursor: pointer;
}
option {
color: rgba(238, 130, 238, 0.705);

  text-align: center;
}
</style>
