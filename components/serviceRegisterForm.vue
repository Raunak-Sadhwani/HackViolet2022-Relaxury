<template>
  <section class="rForm">
    <div class="container">
      <form id="contact" action="" method="post">
       <center> <h3>Registration Form</h3> <br> <br></center>
        <fieldset>
          <input
            placeholder="Your name"
            type="text"
            tabindex="1"
            v-model="name"
            required
            autofocus
          />
        </fieldset>
        <fieldset>
          <input
            placeholder="Your Email Address"
            type="email"
            tabindex="2"
            v-model="email"
            required
          />
        </fieldset>
        <fieldset>
          <input
            placeholder="Your Phone Number"
            type="tel"
            tabindex="3"
            v-model="phone"
            required
          />
        </fieldset>
        <fieldset>
          <select name="service-type" v-model="serviceType" tabindex="4">
            <option value="">Select service type</option>
            <option value="cook">Cook</option>
            <option value="homeservice">home service</option>
            <option value="laundry">Laundry</option>
            <option value="spa">Spa</option>
          </select>
        </fieldset>
        <fieldset>
          <select
            name="city"
            v-model="city"
            @change="cityChanged($event)"
            tabindex="5"
          >
            <option value="">Select Location</option>
            <option value="pune">Pune</option>
            <option value="mumbai">Mumbai</option>
            <option value="banglore">Bangalore</option>
            <option value="chennai">Chennai</option>
          </select>
        </fieldset>
        <fieldset>
          <select name="area" v-model="area" tabindex="6">
            <option value="">Select Area</option>
            <option v-for="area in areas" :key="area.id" :value="area.name">
              {{ area.name }}
            </option>
          </select>
        </fieldset>
        <fieldset>
          <input
            type="text"
            placeholder="Your Comapany Name"
            tabindex="7"
            v-model="company"
          />
        </fieldset>
        <fieldset>
          <input
            type="tel"
            name="price"
            v-model="price"
            placeholder="Price"
            tabindex="8"
          />
        </fieldset>
        <fieldset>
          <textarea
            placeholder="Type your bio here...."
            tabindex="9"
            v-model="bio"
            required
          ></textarea>
        </fieldset>
        <fieldset>
          <button
            name="submit"
            type="submit"
            id="contact-submit"
            data-submit="...Sending"
            tabindex="10"
            @click.prevent="submitForm"
          >
            Submit
          </button>
        </fieldset>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      serviceType: '',
      city: '',
      area: '',
      company: '',
      price: '',
      bio: '',

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
    cityChanged(e) {
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
    submitForm() {
      let user = {
        name: this.name,
        email: this.email,
        phone: this.phone,
        serviceType: this.serviceType,
        city: this.city,
        area: this.area,
        company: this.company,
        price: this.price,
        bio: this.bio,
      }
    },
  },
}
</script>

<style scopped>
@import url(https://fonts.googleapis.com/css?family=Roboto:400,300,600,400italic);
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-font-smoothing: antialiased;
  -moz-font-smoothing: antialiased;
  -o-font-smoothing: antialiased;
  text-rendering: optimizeLegibility;
}

.container {
  max-width: 400px;
  width: 100%;
  margin: 0 auto;
  position: relative;
}

#contact input[type='text'],
#contact input[type='email'],
#contact input[type='tel'],
#contact input[type='url'],
#contact textarea,
#contact button[type='submit'] {
  font: 400 12px/16px 'Roboto', Helvetica, Arial, sans-serif;
}

#contact {
  background: #f9f9f9;
  padding: 25px;
  margin: 150px 0;
  box-shadow: 0 0 20px 0 rgba(0, 0, 0, 0.2), 0 5px 5px 0 rgba(0, 0, 0, 0.24);
}

fieldset select {
  width: 100%;
  border: 1px solid #ccc;
  background: #fff;
  border-radius: 0px;
  color: #aaa;
  margin: auto;
  font-weight: 300;
  font-size: 15px;
  text-align: left;
  align-items: left;
}
fieldset option {
  text-align: left;
  color: #aaa;
}

#contact h3 {
  display: block;
  font-size: 30px;
  font-weight: 300;
  margin-bottom: 10px;
}

#contact h4 {
  margin: 5px 0 15px;
  display: block;
  font-size: 13px;
  font-weight: 400;
}

fieldset {
  border: medium none !important;
  margin: 0 0 10px;
  min-width: 100%;
  padding: 0;
  width: 100%;
}

#contact input[type='text'],
#contact input[type='email'],
#contact input[type='tel'],
#contact input[type='url'],
#contact textarea {
  width: 100%;
  border: 1px solid #ccc;
  background: #fff;
  margin: 0 0 5px;
  padding: 10px;
}

#contact input[type='text']:hover,
#contact input[type='email']:hover,
#contact input[type='tel']:hover,
#contact input[type='url']:hover,
#contact textarea:hover {
  -webkit-transition: border-color 0.3s ease-in-out;
  -moz-transition: border-color 0.3s ease-in-out;
  transition: border-color 0.3s ease-in-out;
  border: 1px solid #aaa;
}

#contact textarea {
  height: 100px;
  max-width: 100%;
  resize: none;
}

#contact button[type='submit'] {
  cursor: pointer;
  width: 100%;
  border: none;
  background: #4caf50;
  color: #fff;
  margin: 0 0 5px;
  padding: 10px;
  font-size: 15px;
}

#contact button[type='submit']:hover {
  background: #43a047;
  -webkit-transition: background 0.3s ease-in-out;
  -moz-transition: background 0.3s ease-in-out;
  transition: background-color 0.3s ease-in-out;
}

#contact button[type='submit']:active {
  box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.5);
}

.btm {
  text-align: center;
  background-color: #f9f9f9;
  color: black;
}

#contact input:focus,
#contact textarea:focus {
  outline: 0;
  border: 1px solid #aaa;
}

::-webkit-input-placeholder {
  color: #888;
}

:-moz-placeholder {
  color: #888;
}

::-moz-placeholder {
  color: #888;
}

:-ms-input-placeholder {
  color: #888;
}
</style>
