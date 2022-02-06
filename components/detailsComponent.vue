<template>
  <section class="detailPage">
    <div class="mainCon">
      <div class="leftCon">
        <div class="photo">
          <img :src="details.image" />
        </div>
        <div class="txt">
          <h2>{{name}}</h2>
          <p>Excellent cook<br />in indian cuisine</p>
        </div>
        <div class="detPrice">
          <h2>{{price}}</h2>
          <button class="cookBtn">HIRE ME</button>
        </div>
      </div>
      <div class="rightCon">
        <div class="cookAbout">
          <h1>About Me</h1>
          <br />
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur
            scelerisque semper rhoncus. Aenean sit amet tempus nibh.
            Pellentesque pretium sed felis ac cursus. Praesent consequat
            pellentesque nulla, et varius leo rhoncus vitae. Integer bibendum
            felis et gravida euismod. <br />
            <br />
            Nam elementum augue et ex porttitor, sit amet molestie massa
            dapibus. Nunc magna diam, efficitur et ultricies a, hendrerit sit
            amet ligula. Vivamus ac urna ut nisl ornare tempor sit amet et enim.
            Nulla quis nunc a sapien condimentum bibendum. Nam porta ante
            blandit ante pharetra, a fermentum tellus dignissim.
          </p>
        </div>
        <div class="cookBio">
          <h1>Bio</h1>
          <br />
          <div class="flexBio">
            <div class="icon">
              <div><i class="fa fa-calendar"></i> Age</div>
              <br />
              <div><i class="fa fa-envelope"></i> Email</div>
              <br />
              <div><i class="fa fa-skype"></i> Skype</div>
              <br />
              <div><i class="fa fa-phone"></i> Phone</div>
              <br />
              <div><i class="fa fa-map-marker"></i> Address</div>
              <br />
            </div>

            <div class="iconValues">
              <div>28</div>
              <br />
              <div>sanjeev@company.com</div>
              <br />
              <div>sanjeev@skype.com</div>
              <br />
              <div>+91 12345 67890</div>
              <br />
              <div>F 420, Paradise Apartment, Pune</div>
              <br />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
props:['name', 'details','price','rate'],
    data () {
        return {
            
        }
    }
};
</script>

<style scopped>
.mainCon {
  height: 80vh;
  width: 90vw;
  background-color: rgba(0, 255, 255, 0.349);
  margin: auto;
  margin-top: 4.7rem;
  box-shadow: 0 0 20px 0 rgba(0, 0, 0, 0.3);
  display: flex;
}
.leftCon {
  display: inline-flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  width: 20vw;
  height: 80vh;

  background-color: white;
}
.txt {
  text-align: center;
}
.photo img {
  box-shadow: 0 0 20px 0 rgba(0, 0, 0, 0.7);

  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 5px;
  width: 175px;
  height: 175px;
}
.detPrice {
    text-align: center;
}
.cookBtn {
  background: rgb(0, 217, 255);
  padding: 20px 40px;
  border: none;
  border-radius: 10px;
  color: white;
  font-size: large;
  cursor: pointer;
  margin-top: 1rem
}
.cookBtn:hover {
  background: rgb(0, 204, 240);
}
.rightCon {
  display: inline-flex;
  width: 70vw;
}
.rightCon h1 {
  font-weight: 400;
  font-size: x-large;
}
.cookAbout {
  display: inline-block;
  padding: 5rem;
  width: 42vw;
}
.cookBio {
  padding-top: 6rem;
  display: inline-block;
  width: 20vw;
}
.flexBio {
  width: 25vw;
  display: flex;
  justify-content: space-between;
}
</style>
