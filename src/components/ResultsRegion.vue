<template>
  <ion-card v-for="region in myData" :key="region">
    <ion-card-header>
      <ion-card-subtitle>{{region.code}}</ion-card-subtitle>
      <ion-card-title>{{region.nom}}</ion-card-title>
    </ion-card-header>
  </ion-card>
</template>

<script>
import {IonCard, IonCardHeader, IonCardTitle, IonCardSubtitle} from '@ionic/vue';

export default {
  name: "ResultsRegion",
  components: {
    IonCard,
    IonCardHeader,
    IonCardTitle,
    IonCardSubtitle,
  },
  props: ['myData'],
}
</script>

<style scoped>

</style>