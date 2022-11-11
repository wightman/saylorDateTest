<template>
  <v-app>
    <v-main>
      <AddSaylor />
      <!--<SaylorDate @dateString="setWillDate"/>
      <SaylorDate @dateString="setProbateDate"/>-->
    </v-main>
  </v-app>
</template>

<script>
//import SaylorDate from './components/SaylorDate';
import AddSaylor from './components/AddSaylor';
//import SaylorDate from './components/SaylorDate';

export default {
  name: 'App',

  components: {
   // SaylorDate,
    AddSaylor,
  },

  data: () => ({
    noteSet: '',
    willDate: '',
    probateDate: '',
    showAddSaylor: false,
  }),
  methods: {
    setWillDate({year, month, day}) {
      this.willDate = year+'-'+month+'-'+day
    },
    setProbateDate({year, month, day}) {
      this.probateDate = year+'-'+month+'-'+day
    },
  }
};
</script>
