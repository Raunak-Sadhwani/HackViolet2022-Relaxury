<template>
  <section class="filter">
    <div class="row2">
      <select name="servicetype" @change="servicetypechanged">
        <option value="">Select a service</option>
        <option value="cook">Cook</option>
        <option value="homeservice">House help</option>
        <option value="laundry">Laundry</option>
        <option value="spa">Spa</option>
      </select>

      <div class="slidecontainer">
        <p>Rating</p>
        <br />
        <input type="range" min="1" max="5" value="5" class="slider" />
        <div class="text-p">
          <p>0</p>
          <p>5</p>
        </div>
      </div>

      <div class="slidecontainer">
        <p>Price (less then {{price}})</p>
        <br />
        <input
          type="range"
          min="2500"
          max="25000"
          class="slider"
          v-model="price"
          @change="pricechanged"
        />
        <div class="text-p">
          <p>2500</p>
          <p>25000</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data(){
    return {
      price: 25000,
    }
  },
  methods: {
    servicetypechanged(e) {
      this.$emit('servicetypechanged', e.target.value)
    },
    pricechanged(e) {
      this.$emit('pricechanged', e.target.value)
    },
  },
}
</script>

<style scopped>
.row2 {
  display: flex;
  flex-direction: column;
  border-radius: 20px;
  background-color: rgba(238, 130, 238, 0.353);
  width: 339px;
  height: 507px;
  margin-left: 3rem;
  margin-right: 4rem;
  margin-top: 2rem;
  margin-bottom: 0;
  margin: 4 0rem;
}
.col2 {
  display: flex;
  justify-content: space-between;
  align-items: center;
  align-content: center;
  text-align: center;
  background-color: violet;
  margin: 1.5rem;
  margin-top: 3rem;
  width: 291px;
  height: max-content;
  padding: 10px;
  padding-left: 20px;
  border-radius: 20px;
}
.col2 img {
  width: 25px;
  height: 25px;
}
.slidecontainer {
  margin: 3rem;
  margin-top: 1.5rem;
  width: 291px;
  margin-left: 1.5rem;
  margin-bottom: 1rem;
}

.slider {
  -webkit-appearance: none;
  width: 291px;
  border-radius: 20px;
  height: 15px;
  outline: none;
  opacity: 0.7;
  -webkit-transition: 0.2s;
  transition: opacity 0.2s;
  background-color: violet;

}
.slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  background: white;
  border-radius: 50%;
  cursor: pointer;
}
.slider::-moz-range-thumb {
  width: 25px;
  height: 25px;
  background: #04aa6d;
  cursor: pointer;
}
.slider:hover {
  opacity: 1;
}

.text-p {
  display: flex;
  justify-content: space-between;
  width: 291px;
}

.dropbtn {
  background-color: rgba(2, 247, 255, 0.781);
  cursor: pointer;
  font-size: 16px;
  border: none;
  border-radius: 50%;
  padding: 0px;
}

/* The container <div> - needed to position the dropdown content */
.dropdown {
  padding-top: 5px;
  display: inline-block;
}

/* Dropdown Content (Hidden by Default) */
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f1f1f1;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;
}

/* Links inside the dropdown */
.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

/* Change color of dropdown links on hover */
.dropdown-content a:hover {
  background-color: #ddd;
}

/* Show the dropdown menu on hover */
.dropdown:hover .dropdown-content {
  display: block;
}

/* Change the background color of the dropdown button when the dropdown content is shown */
</style>
