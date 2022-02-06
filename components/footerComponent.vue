<template>
  <footer>
    <div class="top_header">
      <section>
        <span><i class="fa fa-map-marker"></i></span>
        <span>Pune, Maharashtra, India - 411048</span>
      </section>
      <section>
        <span><i class="fa fa-phone"></i></span>
        <span>+91 88888 88888</span>
      </section>
      <section>
        <span><i class="fa fa-envelope"></i></span>
        <span>sup.relaxury@mail.com</span>
      </section>
    </div>
    <span class="border-shape"></span>
    <div class="bottom_content">
      <section class="social">
        <a href="#"><i class="fa fa-facebook"></i></a>
        <a href="#"><i class="fa fa-instagram"></i></a>
        <a href="#"><i class="fa fa-twitter"></i></a>
        <a href="#"><i class="fa fa-telegram"></i></a>
      </section>
      <section>
        <a href="#">Contact Us</a>
      </section>
    </div>
    <div class="copyright">
      Copyright © 2022 Relauxry - All rights reserved (Created for HackViolet Hackathon)
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style scopped>
*,
*:after,
*:before {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
body {
  margin: 0;
  overflow-x: hidden !important;
  box-sizing: border-box;
  font-family: "Source Sans Pro", sans-serif;
}

a {
  text-decoration: none;
  outline: none !important;
  color: black;
}

.border-shape {
  background: #ffbe00 none repeat scroll 0 0;
  color: #fff;
  display: block;
  height: 3px;
  left: 0;
  margin: 20px auto;
  position: relative;
  right: 0;
  text-align: center;
  top: 0;
  width: 80px;
}

.border-shape::before {
  background: #ffbe00 none repeat scroll 0 0;
  bottom: 0;
  content: "";
  height: 1px;
  left: 80px;
  margin: 0 auto;
  position: absolute;
  text-align: center;
  top: 1px;
  width: 100px;
}

.border-shape::after {
  background: #ffbe00 none repeat scroll 0 0;
  bottom: 0;
  content: "";
  height: 1px;
  margin: 0 auto;
  position: absolute;
  right: 80px;
  text-align: center;
  top: 1px;
  width: 100px;
}

footer {
  margin-top: 5rem;
  width: 100%;
  background: rgba(238, 130, 238, 0.164);
  color: #fff;
}

.top_header {
  padding: 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.top_header section {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}

.top_header span {
  padding: 0 1rem;
}

.top_header .fa {
  color: #ffbe00;
  font-size: 35px;
}

footer .border-shape {
  width: 40%;
}

footer .border-shape::before {
  width: 100%;
  left: 120px;
}

footer .border-shape::after {
  width: 100%;
  right: 120px;
}

footer .bottom_content section {
  padding: 1.5rem 2rem;
  display: flex;
  align-items: center;
  justify-content: Center;
}

.bottom_content a {
  margin: 0 20px;
  color: rgba(0, 0, 0, 0.7);
  transition: 0.5s;
}

.bottom_content a:hover {
  color: rgba(255, 166, 0, 0.699);
}

.social .fa {
  font-size: 25px;
}

.copyright {
  padding: 0.8em 0;
  background-color: #1e1e1e;
  text-align: center;
  color: rgba(255, 255, 255, 0.7);
  font-size: 12px;
}

@media (max-width: 700px) {
  .top_header {
    padding: 1rem;
    display: block;
  }

  .top_header section {
    margin: 40px 0;
    align-items: left;
    justify-content: left;
  }
  footer .bottom_content section {
    padding: 1rem;
    display: block;
  }
  footer .bottom_content section a {
    padding: 1rem;
    font-size: 12px;
    margin: 0 5px;
    display: inline-block;
  }
}
</style>
