<template>
  <section class="listC">
    <div class="Lbox">
      <div class="leftInline">
        <img src="~/static/cook2.png" />
      </div>
      <div class="rightInline">
        <h1>{{ name }}</h1>
        <div class="det">
          <p>{{ detail }}<br /></p>
        </div>
        <div class="star">
          <strong>Rating: {{rating}} /5</strong>
        </div>
      </div>
      <div class="price">
        <h1>₹{{ price }}</h1>
        <p>per Month</p>
      </div>
      <div class="arrow" @click="clicked(name)" >
        <img 
          src="https://img.icons8.com/ios-filled/50/000000/circled-chevron-right.png" 
        />
      </div>
    </div>
  </section>
</template>

<script>
export default {
    props: ['name','detail','price','rating'],
  data() {
    return {
      // cook: {
      //   name: "",
      //   detail: "",
      //   price: "",
      //   rate: "",
      // },
    };
  },
  methods: {
    clicked(name) {
      this.$emit("clicked",name);
    },
  },
};
</script>

<style scopped>
.Lbox {
  display: block;
  border-radius: 20px;


  background-color: rgba(238, 130, 238, 0.353);
  float: right;
  width: 899px;
  height: 166px;
  margin: 3rem;
  margin-right: 4rem;
  margin-bottom: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 2rem;
  padding-top: 1rem;
}
.leftInline {
  display: inline-block;
}
.leftInline img {
  margin-top: 25px;
  width: 151px;
  height: 120px;
  border-radius: 20px;
}
.rightInline {
  display: inline-block;
  width: 300px;
  height: 100px;
}
.det {
  line-height: 2.5;
}
.rightInline h1 {
  font-size: x-large;
}
.price h1 {
  margin-top: 15px;
  font-size: x-large;
}
.det {
  height: 50px;
}
.star i {
  font-size: 24px;
}
.arrow {
  cursor: pointer;

}
</style>
