<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <v-container id="contact">
      <h2 class="text-center text-decoration-underline" elevation="1">
        Contact US
      </h2>
      <v-row>
        <v-col cols="12" sm="6">
          <v-text-field
            v-model="name"
            :rules="[rules.required]"
            label="Names"
            outlined
            required
          ></v-text-field>
          <v-text-field
            v-model="title"
            :rules="[rules.required, rules.counter]"
            label="Subject"
            outlined
            maxlength="20"
            required
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6">
          <v-text-field
            v-model="email"
            :rules="[rules.required, rules.email]"
            label="E-mail"
            outlined
            required
          ></v-text-field>
          <v-textarea
            v-model="message"
            outlined
            label="Description"
            clear-icon="mdi-close-circle"
          ></v-textarea>
        </v-col>
        <v-col cols="12" sm="12">
          <v-btn class="mr-4 btnsend" @click="validate" block> Send </v-btn>
          <!--  message send confirmed-->
          <v-snackbar v-model="snackbar">
            {{ messageform }}

            <template v-slot:action="{ attrs }">
              <v-btn
                color="#007d7d"
                text
                v-bind="attrs"
                @click="snackbar = false"
              >
                Close
              </v-btn>
            </template>
          </v-snackbar>
        </v-col>
      </v-row>
    </v-container>
  </v-form>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      title: '',
      email: '',
      message: '',
      valid: true,
      snackbar: false,
      messageform: '',
      rules: {
        required: (value) => !!value || 'Required.',
        counter: (value) => value.length <= 20 || 'Max 20 characters',
        email: (value) => {
          const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
          return pattern.test(value) || 'Invalid e-mail.'
        },
      },
    }
  },
  methods: {
    validate() {
      if (this.$refs.form.validate()) {
        this.snackbar = true
        this.messageform = 'Message Send'
        this.name= '',
        this.title='',
        this.email='',
        this.message=''
        this.$refs.form.resetValidation()
      } else {
        this.snackbar = true
        this.messageform = 'error send message completed all textfield'
      }
    },
  },
}
</script>
<style>
.btnsend {
  border-radius: 10px;
  background: linear-gradient(145deg, #007373, #008989);
  box-shadow: 1px 2px 2px #007d7d, -1px -2px -1px #008383;
}
</style>
