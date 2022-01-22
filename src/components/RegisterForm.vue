<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <v-text-field
      v-model="name"
      :counter="10"
      :rules="nameRules"
      label="Name"
      required
    ></v-text-field>

    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
    ></v-text-field>

    <v-text-field
      v-model="password"
      :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
      :rules="passwordRules"
      :type="show1 ? 'text' : 'password'"
      name="password"
      label="Password"
      hint="At least 8 characters"
      counter
      required
      @click:append="show1 = !show1"
    ></v-text-field>

    <v-text-field
      v-model="password"
      :append-icon="show2 ? 'mdi-eye' : 'mdi-eye-off'"
      :rules="passwordConfirmRules"
      :type="show2 ? 'text' : 'password'"
      name="confirm-password"
      label="Confirm password"
      hint="At least 8 characters"
      counter
      required
      @click:append="show2 = !show2"
    ></v-text-field>

    <v-checkbox
      v-model="checkbox"
      :rules="[(v) => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate">
      Validate
    </v-btn>

    <v-btn color="error" class="mr-4" @click="reset"> Reset Form </v-btn>
  </v-form>
</template>

<script>
export default {
  name: "RegisterForm",

  data: () => ({
    show1: false,
    show2: false,
    valid: true,
    name: "",
    nameRules: [
      (v) => !!v || "Name is required",
      (v) => (v && v.length <= 10) || "Name must be less than 10 characters",
    ],
    email: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
    ],
    passwordRules: [
      (v) => !!v || "Password is required",
      (v) => v.length >= 8 || "Min 8 characters",
    ],
    passwordConfirmRules: [
      (v) => !!v || "Confirm password is required",
      (v) => (v && v.length <= 8) || "Password must match",
    ],
    checkbox: false,
  }),

  methods: {
    validate() {
      this.$refs.form.validate();
    },
    reset() {
      this.$refs.form.reset();
    },
  },
};
</script>
