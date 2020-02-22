<template>
  <v-container>
    <v-row>
      <!-- Input -->
      <v-col>
        <v-text-field v-model="item.name" label="Name"></v-text-field>
        <v-row>
          <v-col
            ><v-text-field
              v-model="item.position"
              label="Position"
            ></v-text-field
          ></v-col>
          <v-col
            ><v-text-field
              v-model="item.department"
              label="Department"
            ></v-text-field
          ></v-col>
        </v-row>
        <v-text-field v-model="item.company" label="Company"></v-text-field>
        <v-row>
          <v-col
            ><v-text-field v-model="item.city" label="City"></v-text-field
          ></v-col>
          <v-col
            ><v-text-field v-model="item.region" label="Region"></v-text-field
          ></v-col>
        </v-row>
        <v-text-field v-model="item.country" label="Country"></v-text-field>
        <v-row>
          <v-col
            ><v-text-field v-model="item.phone" label="Phone"></v-text-field
          ></v-col>
          <v-col
            ><v-text-field v-model="item.fax" label="Fax"></v-text-field
          ></v-col>
          <v-col
            ><v-text-field v-model="item.mobile" label="Mobile"></v-text-field
          ></v-col>
        </v-row>
        <v-text-field v-model="item.email" label="Email"></v-text-field>
        <v-text-field v-model="item.website" label="Website"></v-text-field>
      </v-col>

      <!-- New Email Signature -->
      <v-col>
        <v-row>
          <v-col>
            <v-card>
              <v-card-title>New Email</v-card-title>
              <v-card-text>
                <p class="px-5 pb-5">
                  <span v-if="item.name"
                    ><b>{{ item.name }}</b></span
                  >
                  <span v-if="item.position">&nbsp;&nbsp;|&nbsp;&nbsp;{{ item.position }}</span>
                  <span v-if="item.department">&nbsp;&nbsp;|&nbsp;&nbsp;{{ item.department }}</span>
                  <br />
                  <span v-if="item.company"
                    ><b>{{ item.company }}</b></span
                  >
                  <span v-if="item.city">&nbsp;&nbsp;|&nbsp;&nbsp;{{item.city }}</span>
                  <span v-if="item.region">&nbsp;&nbsp;|&nbsp;&nbsp;{{item.region }}</span>
                  <span v-if="item.country">&nbsp;&nbsp;|&nbsp;&nbsp;{{ item.country }}</span>
                  <br />
                  <span v-if="item.phone"><b>T</b>&nbsp;{{ item.phone }}</span>
                  <span v-if="item.fax"
                    >&nbsp;&nbsp;|&nbsp;&nbsp;<b>F</b>&nbsp;{{ item.fax }}</span
                  >
                  <span v-if="item.mobile"
                    >&nbsp;&nbsp;|&nbsp;&nbsp;<b>M</b>&nbsp;{{ item.mobile }}</span
                  >
                  <br />
                  <span v-if="item.email"
                    ><a :href="'mailto:' + item.email">{{
                      item.email
                    }}</a></span
                  >
                  <span v-if="item.website"
                    >&nbsp;&nbsp;|&nbsp;&nbsp;<a :href="'http://' + item.website" target="_blank">{{
                      item.website
                    }}</a></span
                  >
                </p>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
        <v-row>
          <v-col>
            <v-card>
              <v-card-title>Reply/Forward</v-card-title>
              <v-card-text>
                <p class="px-5 pb-5">
                  <span v-if="item.name"
                    ><b>{{ item.name }}</b></span
                  >
                  <span v-if="item.position">&nbsp;&nbsp;|&nbsp;&nbsp;{{ item.position }}</span>
                  <span v-if="item.department">&nbsp;&nbsp;|&nbsp;&nbsp;{{ item.department }}</span>
                  <br />
                  <span v-if="item.mobile"><b>M</b>&nbsp;{{ item.mobile }}</span>
                  <span v-if="item.email"
                    >&nbsp;&nbsp;|&nbsp;&nbsp;<a :href="'mailto:' + item.email">{{
                      item.email
                    }}</a></span
                  >
                </p>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-col>

      <!-- Reply/Forward Email Signature -->
      <v-col> </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: "EmailSignatureGenerator",
    props: {
      item: Object
    },
    data: () => ({})
  };
</script>
