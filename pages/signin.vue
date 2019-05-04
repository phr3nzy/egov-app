<template>
  <v-container fluid fill-height>
    <v-layout align-center justify-center>
      <v-flex xs12 sm10 md8 lg6>
        <v-card :light="true" class="elevation-12" style="border-radius: 20px;">
          <v-toolbar dark color="secondary">
            <v-toolbar-title
              ><v-icon left>person</v-icon> Sign In</v-toolbar-title
            >
          </v-toolbar>
          <v-form ref="form" v-model="valid" lazy-validation>
            <v-card-text>
              <v-text-field
                v-model="username"
                color="secondary"
                prepend-icon="person"
                :rules="usernameRules"
                name="username"
                label="Username"
                type="text"
              />
              <v-text-field
                v-model="password"
                color="secondary"
                prepend-icon="lock"
                :rules="passwordRules"
                name="password"
                label="Password"
                type="password"
              />
            </v-card-text>
            <v-card-actions>
              <v-spacer />
              <v-btn
                :loading="loading"
                type="submit"
                flat
                round
                color="secondary"
                @click.stop.prevent="signIn"
                >Sign in <v-icon right>lock_open</v-icon></v-btn
              >
            </v-card-actions>
          </v-form>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      loading: false,
      username: '',
      password: '',
      usernameRules: [v => !!v || 'Required!'],
      passwordRules: [v => !!v || 'Required!']
    }
  },
  methods: {
    signIn() {
      this.loading = true
      setTimeout(() => {
        this.loading = false
      }, 3000)
    }
  }
}
</script>
