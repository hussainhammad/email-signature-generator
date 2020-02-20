<template>
  <v-container>
    <v-row>
      <!-- Input -->
      <v-col>
        <v-text-field v-model="name" label="Name"></v-text-field>
        <v-row>
          <v-col><v-text-field v-model="position" label="Position"></v-text-field></v-col>
          <v-col><v-text-field v-model="department" label="Department"></v-text-field></v-col>
        </v-row>
        <v-text-field v-model="company" label="Company"></v-text-field>
        <v-row>
          <v-col><v-text-field v-model="city" label="City"></v-text-field></v-col>
          <v-col><v-text-field v-model="region" label="Region"></v-text-field></v-col>
        </v-row>
        <v-text-field v-model="country" label="Country"></v-text-field>
        <v-row>
          <v-col><v-text-field v-model="phone" label="Phone"></v-text-field></v-col>
          <v-col><v-text-field v-model="fax" label="Fax"></v-text-field></v-col>
          <v-col><v-text-field v-model="mobile" label="Mobile"></v-text-field></v-col>
        </v-row>
        <v-row>
          <v-col></v-col>
          <v-col></v-col>
        </v-row>
        <v-text-field v-model="email" label="Email"></v-text-field>
        <v-text-field v-model="website" label="Website"></v-text-field>
      </v-col>

      <!-- New Email Signature -->
      <v-col>
        <v-card>
          <v-card-title>New Email</v-card-title>
          <v-card-content>
            <p class="px-5 pb-5">
              <span v-if="name"><b>{{ name }}</b></span>
              <span v-if="position">{{ " | " + position }}</span>
              <span v-if="department">{{ " | " + department }}</span>
              <br />
              <span v-if="company"><b>{{ company }}</b></span>
              <span v-if="city">{{ " | " + city }}</span>
              <span v-if="region">{{ " | " + region }}</span>
              <span v-if="country">{{ " | " + country }}</span>
              <br />
              <span v-if="phone"><b>T</b>{{ phone }}</span>
              <span v-if="fax"><b>{{" | "}}F</b>{{ fax }}</span>
              <span v-if="mobile"><b>{{"  |  "}}M </b>{{ mobile }}</span>
              <br />
              <span v-if="email"><a :href="'mailto:' + email">{{email}}</a></span>
              <span v-if="website">{{ " | " }}<a :href="website" target="_blank">{{website}}</a></span>
            </p>
          </v-card-content>
        </v-card>
        <v-card>
          <v-card-title>Reply/Forward</v-card-title>
          <v-card-content>
            <p class="px-5 pb-5">
              <span v-if="name"><b>{{ name }}</b></span>
              <span v-if="position">{{ " | " + position }}</span>
              <span v-if="department">{{ " | " + department }}</span>
              <br />
              <span v-if="mobile"><b>M</b>{{ mobile }}</span>
              <span v-if="email">{{ " | " }}<a :href="'mailto:' + email">{{ email}}</a></span>
            </p>
          </v-card-content>
        </v-card>
      </v-col>

      <!-- Reply/Forward Email Signature -->
      <v-col>
        
      </v-col>
    </v-row>
    
  </v-container>
</template>

<script>
  export default {
    name: "EmailSignatureGenerator",

    data: () => ({
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
    })
  };
</script>
