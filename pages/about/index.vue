<template>
  <section class="main">
    <div class="about-section">
      <h1>About Us Page</h1>
      <p>Some text about who we are and what we do.</p>
    </div>

    <h2 style="text-align: center">Our Team</h2>

    <div class="row">
      <div class="column">
        <div class="card">
          <img src="we4.png" alt="John" style="width: 100%" />
          <div class="container">
            <br />
            <br />
            <h2>Realxury</h2>
            <p class="title">Founders</p>
            <p>
              Meet the team behind Relaxury <br />
              From left to right: Raunak Sadhwani, Mohammed Faizan, Taha Kotwal
              and Rajesh Kumawat.
            </p>
            <br />
            <br />
            <ul>
              <li>Raunak Sadhwani: UX and Design Head</li>
              <li>Rajesh Kumawat: Back end Developer</li>
              <li>Taha Kotwal: Sales Head</li>
              <li>Mohammed Faizan: HR and Marketing head</li>
            </ul>
            <br /><br />
            <p>Email: sup.relaxury@mail.com</p>
            <br />
            <br />
            <p><button class="button">Contact</button></p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {}
</script>

<style scoped>
.main {
  margin: 0;
}
html {
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: inherit;
}
.row {
  display: flex;
  margin: auto;
}
.column {
  width: 60.3%;
  margin: auto;

  margin-bottom: 3rem;

  padding: 0 8px;
}

.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  margin: 8px;
}

.about-section {
  padding: 50px;
  text-align: center;
  color: white;
}

.container {
  padding: 0 16px;
  text-align: center;
  height: max-content;
}

.container::after,
.row::after {
  content: '';
  clear: both;
  display: table;
}

.title {
  color: grey;
}

.button {
  border: none;
  outline: 0;
  display: inline-block;
  padding: 8px;
  color: white;
  background-color: #000;
  text-align: center;
  cursor: pointer;
  width: 100%;
}

.button:hover {
  background-color: #555;
}

img {
  width: 10%;
}

@media screen and (max-width: 650px) {
  .column {
    width: 100%;
    display: block;
  }
}
</style>
