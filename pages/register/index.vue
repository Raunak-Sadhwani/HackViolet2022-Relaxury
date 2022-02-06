<template>
  <section class="main">
    <serviceRegisterForm v-if="onServiceRegister" />
    <dropByRegisterForm v-else-if="onDropByRegister" />
    <eventRegisterForm v-else-if="onEventRegister" />
    <div v-else>
      <section class="reg">
        <div class="mid" id="cards">
          <div class="row">
            <div class="col">
              <h3>Services</h3>
              <br />
              <img
                src="https://img.icons8.com/ios-filled/100/000000/man-on-phone.png"
              />
              <p>
                <br /><br />
                Services like technician, laundry, cook, or any other home
                services in your locality <br /><br /><br />
              </p>
              <button class="butn" @click="serviceRegister">
                Register a Service
              </button>
            </div>
            <div class="col">
              <h3>Drop By</h3>
              <br />
              <img
                src="https://img.icons8.com/ios-glyphs/90/000000/shop-location.png"
              />
              <p>
                <br /><br />
                Information about location in your locality like cafes, stores,
                stalls, spa. <br /><br /><br />
              </p>
              <button class="butn" @click="dropByRegister">
                Register a Drop By
              </button>
            </div>
            <div class="col">
              <h3>Events</h3>
              <br />
              <img
                src="https://img.icons8.com/ios-filled/100/000000/conference-foreground-selected.png"
              />
              <p>
                <br /><br />
                Public events in your locality ranging from a cricket match for
                the evening to parties. <br /><br /><br />
              </p>
              <button class="butn" @click="eventRegister">
                Register an Event
              </button>
            </div>
          </div>
        </div>
      </section>
    </div>
  </section>
</template>

<script>
import serviceRegisterForm from '~/components/serviceRegisterForm.vue'
import dropByRegisterForm from '~/components/dropByRegisterForm.vue'
import eventRegisterForm from '~/components/eventRegisterForm.vue'
export default {
  components: {
    serviceRegisterForm,
    dropByRegisterForm,
    eventRegisterForm,
  },
  data() {
    return {
      onServiceRegister: false,
      onDropByRegister: false,
      onEventRegister: false,
    }
  },
  methods: {
    serviceRegister() {
      this.onServiceRegister = true
      this.onDropByRegister = false
      this.onEventRegister = false
    },
    dropByRegister() {
      this.onServiceRegister = false
      this.onDropByRegister = true
      this.onEventRegister = false
    },
    eventRegister() {
      this.onServiceRegister = false
      this.onDropByRegister = false
      this.onEventRegister = true
    },
  },
}
</script>

<style scoped>
.mid {
  width: 80%;
  margin: auto;
  text-align: center;
}
.mid h1 {
  font-size: 36px;
  font-weight: 600;
}
.mid p {
  font-weight: 300;
  font-size: 14px;
  line-height: 22px;
  padding: 10px;
}

.row {
  margin-top: 10%;
  display: flex;
  justify-content: space-between;
}
.col {
  flex-basis: 31%;
  background: rgba(238, 130, 238, 0.164);
  border-radius: 10px;
  margin-bottom: 5%;
  padding: 20px 12px;
  box-sizing: border-box;
  transition: 0.5s;
  height: max-content;
  width: 50rem;
}
.row h3 {
  font-weight: 600;
  margin: 10px 0;
  text-align: center;
}
.col:hover {
  box-shadow: 0 0 20px 0 rgba(0, 0, 0, 0.2);
}
.butn {
  display: inline-block;
  text-decoration: none;
  border: none;
  padding: 12px 34px;
  font-size: 13px;
  background: transparent;
  position: relative;
  cursor: pointer;
  border-radius: 20px;
  width: 180px;
  background: rgba(238, 130, 238, 0.315);

}
.butn:hover {
  background: violet;
  transition: 1s;
}
img {
  width: 100px;
  height: 100px;
}
</style>
