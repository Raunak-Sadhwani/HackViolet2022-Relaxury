<template>
  <div class="main">
    <div class="form">
      <input type="text" name="name" v-model="name" placeholder="Name" />
      <input type="email" name="email" v-model="email" placeholder="Email" />
      <input
        type="password"
        name="password"
        v-model="password"
        placeholder="Password"
      />
      <button class="btn" @click="postUser">Signup</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      password: '',
    }
  },
  methods: {
    postUser() {
      const user = {
        name: this.name,
        email: this.email,
        password: this.password,
      }
      fetch(
        'https://aiobuddy-default-rtdb.asia-southeast1.firebasedatabase.app/user.json',
        {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify(user),
        }
      )
      fetch(
        'https://aiobuddy-default-rtdb.asia-southeast1.firebasedatabase.app/user.json'
      )
        .then((response) => {
          if (response.ok) {
            return response.json()
          }
        })
        .then((data) => {
          let users = []
          for (var usr in data) {
            users.push({
              name: data[usr].name,
              email: data[usr].email,
              password: data[usr].password,
            })
            
          }
        })
    },
  },
}
</script>

<style></style>
