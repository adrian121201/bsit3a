<template>

  <div class="main-container">
    <v-card class="form-container elevation-4">
      <div class="logo-container"><img src="../assets/logo.png" alt="Logo" class="logo-img"></div>
      <div class="social-link-button-container">


        <v-row class="mx-12 mt -5">
          <v-col cols="auto" class="mr-auto">
            <v-btn outlined color="blue-grey"><v-icon color="red" left>mdi-google</v-icon>GOOGLE</v-btn>
          </v-col>
          <v-col cols="auto">
            <v-btn outlined color="blue-grey"><v-icon color="blue" left>mdi-facebook</v-icon>FACEBOOK</v-btn>
          </v-col>
        </v-row>

      </div>
      <v-card-text>
        <v-form ref="form" v-model="valid" lazy-validation>


          <v-text-field v-model="email" :rules="emailRules" label="E-mail" required prepend-inner-icon="mdi-account"
            outlined=15></v-text-field>
          <v-text-field v-model="password" :rules="passwordRules" label="Pasword" required type="password"
            prepend-inner-icon="mdi-lock" outlined=15></v-text-field>

          <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate" block>
            SIGNIN
          </v-btn>

        </v-form>

      </v-card-text>
      <div class="Link">
        <a>Create an account</a>
      </div>

    </v-card>
  </div>



</template>


<script>
export default {

  layout: 'auth',
  name: 'IndexPage',
  data: () => ({
    valid: true,
    password: '',
    passwordRules: [
      v => !!v || 'Password is required',
      v => (v && v.length <= 10) || 'Name must be less than 10 characters',
    ],
    email: '',
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ],

  }),
  methods: {
    validate() {
      if (this.$refs.form.validate()) {
        console.log("Logging In");
        this.$router.push("/dashboard");
      }
    }
  }


}

</script>


<style>

.Link {
  display: flex;
  align-items: center;
  flex-direction: column;
  color: blue;
}

.main-container {

  display: flex;
  align-items: center;
  flex-direction: column;
  height: 100%;
  width: 100%;
  background-image: url('../assets/background.png');
  background-size: cover;
  background-position: center;
  height: 100vh;


}

.form-container {


  height: 600px;
  width: 500px;
  margin-top: 100px;
  border-radius: 10px;

}

.logo-container {


  display: flex;
  align-items: center;
  flex-direction: column;
  width: 100%;
  height: 200px;

}

.logo-img {

  height: 150px;
  margin-top: 50px;
}

.social-link-button-container {

  display: flex;
  align-items: center;
  justify-content: space-around;
  height: 100px;
  width: 100%;
}

.btn-google {
  border-color: blue;
  border-width: 1px;
}
</style>
