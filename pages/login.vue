<template>
  <v-row>
    <v-col class="text-center">
      <v-form
        ref="form"
        v-model="valid"
        lazy-validation
      >
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
          type="password"
          label="Password"
          required
        ></v-text-field>


        <v-btn
          :disabled="!valid"
          color="success"
          class="mr-4"
        >
          Validate
        </v-btn>

        <v-btn
          color="error"
          class="mr-4"
        >
          Reset Form
        </v-btn>

        <v-btn
          color="warning"

        >
          Reset Validation
        </v-btn>
      </v-form>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'InspirePage'
}
</script>
