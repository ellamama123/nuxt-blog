<template>
  <v-row>
    <v-col class="text-center">
      <v-form
        ref="form"
        v-model="valid"
        lazy-validation
      >
        <v-text-field
          :counter="10"
          :rules="emailRules"
          label="Email"
          v-model="userForm.email"
          required
        ></v-text-field>

        <v-text-field
          type="password"
          label="Password"
          v-model="userForm.password"
          required
        ></v-text-field>

        <v-btn
          color="success"
          @click="userLogin"
        >
          Login
        </v-btn>
      </v-form>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'LoginPage',
  data() {
      return {
          userForm: {
              email: '',
              password: ''
          }
      }
  },
  methods: {
      async userLogin() {
          try {
              await this.$auth
              .login({
                data: this.userForm,
              })
              this.$router.push("/");
          } catch (err) {
              this.$notify.error({
                  title: 'Error',
                  message: 'Sai email hoặc mật khẩu'
              })
          }
      }
  }
}
</script>
