<template>
    <v-row justify="center">
      <v-dialog v-model="dialog" persistent max-width="600px">
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="primary" dark v-bind="attrs" v-on="on">
            On Board Saylor
          </v-btn>
        </template>
        <v-card>
          <v-card-title>
            <span class="text-h5">New Saylor on-boarding</span>
          </v-card-title>
          <v-card-text>
            <v-container>
              <v-row>
                <v-col cols="12" sm="6" md="4" >
                  <v-text-field label="First name" required></v-text-field>
                </v-col>
                <v-col cols="12" sm="6" md="4">
                  <v-text-field label="Last name" persistent-hint>
                  </v-text-field>
                </v-col>
              </v-row>
              <v-row>
                <v-col>
                    <SaylorDate @dateString="setWillDate"/>
                    <SaylorDate @dateString="setProbateDate"/>
                </v-col>
              </v-row>
            </v-container>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="blue darken-1" text @click="dialog = false">
              Close
            </v-btn>
            <v-btn color="blue darken-1" text @click="dialog = false">
              Save
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-row>
</template>
<script>
    import SaylorDate from './components/SaylorDate';
    export default {
        components: {
            SaylorDate,
        },
        data: () => ({
            dialog: false,
            willDate: '',
            probateDate: '',
        }),
        methods: {
            setWillDate({year, month, day}) {
                this.willDate = year+'-'+month+'-'+day
            },
            setProbateDate({year, month, day}) {
                this.probateDate = year+'-'+month+'-'+day
            },
        },
    }
</script>
