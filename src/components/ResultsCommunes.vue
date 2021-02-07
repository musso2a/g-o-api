<template>
  <ion-card v-for="commune in myData" :key="commune">
    <ion-card-header>
      <ion-card-subtitle>{{commune.code}}</ion-card-subtitle>
      <ion-card-title>{{commune.nom}}</ion-card-title>
    </ion-card-header>

      <ion-item>
        <ion-label>Département</ion-label>
        <ion-note slot="end" color="tertiary">{{commune.departement.code}}</ion-note>
      </ion-item>
      <ion-item>
        <ion-label>Région</ion-label>
        <ion-note slot="end" color="tertiary">{{commune.region.nom}}</ion-note>
      </ion-item>

      <ion-item>
        <ion-label>Codes postaux :</ion-label>
        <ion-note slot="end" color="tertiary">{{commune.codesPostaux}}</ion-note>
      </ion-item>

      <ion-item>
        <ion-label>Population</ion-label>
        <ion-note slot="end" color="tertiary">{{commune.population}}</ion-note>
      </ion-item>
  </ion-card>
</template>

<script>
import {IonCard, IonCardHeader, IonCardTitle, IonCardSubtitle, IonLabel, IonNote} from '@ionic/vue';

export default {
  name: "ResultsCommunes",
  components: {
    IonCard,
    IonCardHeader,
    IonCardTitle,
    IonCardSubtitle,
    IonLabel,
    IonNote,
  },
  props: ['myData']
}



</script>

<style scoped>

</style>