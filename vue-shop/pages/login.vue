<template>
  <v-layout column align-content-center>
    <v-flex tag="h3">Login to Vue Shop</v-flex>
    <v-form ref="form" v-model="valid" lazy-validation width="100px">
      <v-text-field v-model="username" :rules="[rules.required]" label="ID" required>
      </v-text-field>
      <v-text-field v-model="password" :append-icon="show_password ? 'visibility_off' : 'visibility'"
        :rules="[rules.required, rules.more_than_8]" :type="show_password ? 'text' : 'password'"
        label="PASSWORD" hint="at least 8 characters" counter
        @click:append="show_password = !show_password">
      </v-text-field>
      <v-btn @click="login">login</v-btn>
      <router-link 
        to="/register"
        tag="v-btn"
      >
        <v-btn @click="register">register</v-btn>
      </router-link>
    </v-form>
  </v-layout>
</template>

<script>
  export default {
    data () {
      return {
        valid: true,
        username: '',
        password: '',
        rules: {
          required: value => !!value || 'Required',
          more_than_8: value => value.length >= 8 || 'More than 8 characters'
        },
        show_password: false
      }
    },
    methods: {
      async login () {
        if (this.$refs.form.validate()) {
          await this.$auth.loginWith('local', {
            data: { username: this.username, password: this.password }
          })
            .then(res => {
              this.$router.push({ name: 'ShowBooks' })
            })
            .catch(e => {
              console.log(e)

              this.$refs.form.reset()
              this.username = ''
              this.password = ''
            })
        }
      },
      register () {
        this.$router.push({ name: 'Register' })
      }
    }
  }
</script>
