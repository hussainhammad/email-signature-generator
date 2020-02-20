<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        Email Signature Generator
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/hussainhammad/email-signature-generator"
        target="_blank"
        text
      >
        <span class="mr-2">GitHub Repo</span>
        <v-icon>mdi-github-circle</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content>
      <EmailSignatureGenerator/>
    </v-content>
  </v-app>
</template>

<script>
import EmailSignatureGenerator from './components/EmailSignatureGenerator';

export default {
  name: 'App',

  components: {
    EmailSignatureGenerator,
  },

  data: () => ({
    //
  }),
};
</script>
