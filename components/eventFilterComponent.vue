<template>
  <section class="filter">
    <div class="row2">
      <select name="servicetype" @change="eventtypechanged">
        <option value="">Select Event Type</option>
        <option value="party">Party</option>
        <option value="trip">Trip</option>
        <option value="sport">Sport</option>
        <option value="exhibition">Exibition</option>
      </select>

      <!-- <div class="slidecontainer">
        <p>Rating</p>
        <br />
        <input type="range" min="1" max="5" value="5" class="slider" />
        <div class="text-p">
          <p>0</p>
          <p>5</p>
        </div>
      </div> -->

    
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
    eventtypechanged(e) {
      this.$emit('eventtypechanged', e.target.value)
    },
  },
}
</script>

<style scopped>
.row2 {
  display: flex;
  flex-direction: column;
  border-radius: 20px;
  background-color: rgba(2, 247, 255, 0.247);
  width: 339px;
  height: 3rem;
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
  background-color: rgba(2, 247, 255, 0.781);
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
  background-color: rgba(2, 247, 255, 0.781);
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
