<template>
  <v-container>
    <v-container>
      <v-row justify="center">
        <v-col md="6">
          <div
            class="text-center elevation-4 pa-12 headline green darken-4 white--text"
          >
            BECOME A MEMBER!
          </div>
        </v-col>
      </v-row>
    </v-container>

    <v-img
      class="mt-5 mx-auto"
      src="Club.jpg"
      transition="scale-transition"
      width="50%"
    />
    <v-form v-model="valid">
      <v-row justify="center">
        <v-col md="3">
          <v-text-field
            v-model="firstName"
            counter="40"
            hint="Please enter your last name"
            label="First Name"
            required
            :rules="firstNameRules"
          ></v-text-field
        ></v-col>
        <v-col md="3">
          <v-text-field
            v-model="lastName"
            counter="10"
            hint="Please enter your first name"
            label="Last Name"
            required
            :rules="lastNameRules"
          ></v-text-field
        ></v-col>
      </v-row>
      <v-row justify="center">
        <v-col md="3">
          <v-text-field
            prepend-inner-icon="mdi-at"
            color="green darken-4"
            hint="This field uses counter prop"
            label="E-Mail"
            :rules="emailRules"
            required
          ></v-text-field
        ></v-col>
        <v-col md="3">
          <v-text-field
            prepend-inner-icon="mdi-phone"
            color="green darken-4"
            hint="This field uses counter prop"
            label="Phone"
            :rules="phoneRules"
            required
          ></v-text-field
        ></v-col>
      </v-row>
      <v-row justify="center">
        <v-col md="6">
          <v-checkbox
            label="I agree to pay Robert Baumgartner 1000€ each month"
            :rules="[(v) => !!v || 'You must agree to continue!']"
            required
          ></v-checkbox>
        </v-col>
      </v-row>
      <v-row justify="center">
        <v-col md="6">
          <div class="d-block text-center">
            <v-btn
              class="ma-2"
              color="green darken-4 white--text"
              :disabled="!valid"
            >
              Submit
            </v-btn>
          </div>
        </v-col>
      </v-row>
    </v-form>
  </v-container>
</template>

<script>
export default {
  name: 'Member',
  data: () => ({
    valid: true,
    firstName: '',
    lastName: '',
    firstNameRules: [
      (v) => !!v || 'Name is required',
      (v) => (v && v.length > 5) || 'Name must be at least 5 characters',
      (v) => (v && v.length <= 40) || 'Name must be under 40 characters',
    ],
    lastNameRules: [
      (v) => !!v || 'Name is required',
      (v) => (v && v.length > 5) || 'Name must be at least 5 characters',
      (v) => (v && v.length <= 10) || 'Name must be under 10 characters',
    ],
    emailRules: [
      (v) => !!v || 'E-mail is required',
      (v) => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ],
    phoneRules: [(v) => !!v || 'Phone Number is required'],
  }),
};
</script>

<style lang="scss" scoped></style>
