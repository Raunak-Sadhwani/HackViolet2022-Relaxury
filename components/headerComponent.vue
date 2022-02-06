<template>
  <section id="headerC">
    <div class="header">
      <nav>
        <div class="nav-links">
          <img src="~/static/Relaxury.png" />
          <ul>
            <li><nuxt-link to="/app">HOME</nuxt-link></li>
            <li><nuxt-link to="/app/services">SERVICES</nuxt-link></li>
            <li><nuxt-link to="/app/events">EVENTS</nuxt-link></li>
            <li><nuxt-link to="/app/dropby">DROP BY</nuxt-link></li>
            <li><nuxt-link to="/about">ABOUT US</nuxt-link></li>
            <li><nuxt-link to="/register">REGISTER</nuxt-link></li>
          </ul>
        </div>
      </nav>
    </div>
  </section>
</template>

<script>
export default {
  methods: {
    serviceClicked() {
      this.$emit('service-clicked')
    },
    homeClicked() {
      this.$emit('home-clicked')
    },
  },
}
</script>

<style scopped>
ul{
  list-style: none;
  margin-top: auto;
  margin-bottom: auto;
  margin-right: 1rem;
  padding: auto;
}
.header nav {
  display: flex;
  justify-content: space-between;
  align-items: right;
  background-color: #ba7edd;

}
.nav-links {
  flex: 1;
  display: flex;
  justify-content: space-between;
  text-align: center;
}
.nav-links ul li {
  padding-top: 200px;
  list-style: none;
  display: inline-block;
  padding: 8px 15px;
  position: relative;
  cursor: pointer;
  margin-top: auto;
  margin-bottom: auto;
}
.nav-links ul li a {
  color: rgb(0, 0, 0);
  text-decoration: none;
  font-size: 15px;
  margin-top: auto;
  margin-bottom: auto;
}
.nav-links ul li::after {
  content: '';
  width: 0%;
  height: 2px;
  background: rgba(128, 128, 128, 0.521);
  display: block;
  margin: auto;
  transition: 0.7s;
}
.nav-links ul li:hover::after {
  width: 100%;
}
.text-box {
  width: 90%;
  color: white;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}
.nav-links img {
  width: 200px;
  height: 100px;
}
</style>
