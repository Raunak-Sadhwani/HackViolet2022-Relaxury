<template>
  <section class="homePage">
    <div class="home">
      <div class="text-box">
        <h1>Need Anything Let Us Know</h1>
        <p>Scroll Down to know<br />more</p>
        <span>
          <a href="#cards"><i class="fa fa-angle-double-down fa-2x floating"/></a>
        </span>
      </div>
    </div>

    <div class="mid" id="cards">
      <h1>Our motto is to help people anyway we can</h1>
      <p>
        We offer various types of help, we also help lonely people to socialize
        and making friends<br />
        We also offer - services, Drop By, Events.
      </p>
      <div class="row">
        <div class="col">
          <h3> Services</h3>
          <br />
          <img
            src="https://img.icons8.com/ios-filled/100/000000/man-on-phone.png"
          />
          <p>
            <br /><br />
            Services like technician, laundry, cook, or any other home services
            in your locality <br /><br /><br />
          </p>
          <button class="butn" @click="serviceClicked">
            <a href="#headerC">Know More</a></button>
        </div>
        <div class="col">
          <h3>Drop By</h3>
          <br />
          <img
            src="https://img.icons8.com/ios-glyphs/90/000000/shop-location.png"
            height="100"
            width="100"
          />
          <p>
            <br /><br />
            Information about location in your locality like cafes, stores,
            stalls, spa. <br /><br /><br />
          </p>
          <button class="butn">Know More</button>
        </div>
        <div class="col">
          <h3>Events</h3>
          <br />
          <img
            src="https://img.icons8.com/ios-filled/100/000000/conference-foreground-selected.png"
          />
          <p>
            <br /><br />
            Public events in your locality ranging from a cricket match for the
            evening to parties. <br /><br /><br />
          </p>
          <button class="butn">Know More</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  methods: {
    serviceClicked() {
      this.$router.push('/app/services')
    },
  },
};
</script>

<style scoped>
.home {
  min-height: 80vh;
  width: 100%;
  background-position: center;
  background-size: cover;
  position: relative;
}
.text-box h1 {
  margin-top: 35px;
  font-size: 58px;
}
.text-box p {
  margin: 10px 0 20px;
  font-size: 14px;
}
.text-box span i {
  cursor: pointer;
}
.floating {
  animation-name: floating;
  animation-duration: 3s;
  animation-iteration-count: infinite;
  animation-timing-function: ease-in-out;
}

@keyframes floating {
  0% {
    transform: translate(0, 0px);
  }
  100% {
    transform: translate(0, 20px);
    color: rgba(0, 0, 0, 0.205);
  }
}

.mid {
  width: 80%;
  margin: auto;
  text-align: center;
  padding-top: 100px;
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
  margin-top: 5%;
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
</style>
