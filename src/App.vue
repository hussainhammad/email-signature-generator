<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        Email Signature Generator
      </div>

      <v-spacer></v-spacer>

      <v-tooltip bottom>
        <template v-slot:activator="{ on }">
          <v-btn text v-on="on">
            <v-icon @click="saveJson()">
              mdi-json
            </v-icon>
            <a
              ref="signatureJson"
              :href="jsonFile"
              target="_blank"
              :download="fileName"
              hidden
            ></a>
          </v-btn>
        </template>
        <span>Save data as JSON file</span>
      </v-tooltip>

      <v-tooltip bottom>
        <template v-slot:activator="{ on }">
          <v-btn text v-on="on">
            <v-icon @click="$refs.file.click()">
              mdi-file-upload
            </v-icon>
            <input
              ref="file"
              type="file"
              accept="application/json"
              @change="uploadFile"
              style="display: none"
            />
          </v-btn>
        </template>
        <span>Upload data as JSON file</span>
      </v-tooltip>

      

      

      <v-btn
        href="https://github.com/hussainhammad/email-signature-generator"
        target="_blank"
        text
      >
        <v-icon>mdi-github-circle</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content>
      <EmailSignatureGenerator :item="item" />
    </v-content>
  </v-app>
</template>

<script>
  import EmailSignatureGenerator from "./components/EmailSignatureGenerator";

  export default {
    name: "App",
    components: {
      EmailSignatureGenerator
    },
    data: () => ({
      item: {
        name: null,
        position: null,
        department: null,
        company: null,
        city: null,
        region: null,
        country: null,
        phone: null,
        fax: null,
        mobile: null,
        email: null,
        website: null
      }
    }),
    computed: {
      fileName() {
        return this.item
          ? "signature - " + this.item.name + ".json"
          : "signature.json";
      },
      jsonFile() {
        let data =
          "data:text/json;charset=utf-8," +
          encodeURIComponent(JSON.stringify(this.item));
        return data;
      }
    },
    methods: {
      uploadFile(e) {
        let file = e.target.files[0] || e.dataTransfer.files[0];
        const reader = new FileReader();
        reader.onload = e => (this.item = JSON.parse(e.target.result));
        reader.readAsText(file);
      },
      saveJson() {
        this.$refs.signatureJson.click();
      }
    }
  };
</script>
