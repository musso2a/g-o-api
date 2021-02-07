<template>
  <ion-card v-for="departement in myData" :key="departement">
    <ion-card-header>
      <ion-card-subtitle>{{departement.code}}</ion-card-subtitle>
      <ion-card-title>{{departement.nom}}</ion-card-title>
    </ion-card-header>
    <ion-card-content>
      <ion-item>
        <ion-label>Département</ion-label>
        <ion-note slot="end" color="tertiary">{{departement.codeDepartement}}</ion-note>
      </ion-item>
      <ion-item>
        <ion-label>Région</ion-label>
        <ion-note slot="end" color="tertiary">{{ departement.codeRegion }}</ion-note>
      </ion-item>

      <ion-item>
        <ion-label>Codes postaux :</ion-label>
        <ion-note slot="end" color="tertiary">{{departement.codesPostaux}}</ion-note>
      </ion-item>

      <ion-item>
        <ion-label>Population :</ion-label>
        <ion-note slot="end" color="tertiary">{{departement.population}}</ion-note>
      </ion-item>
    </ion-card-content>
  </ion-card>
</template>

<script>
import {IonCard, IonCardHeader, IonCardTitle, IonCardSubtitle, IonCardContent, IonLabel, IonNote} from '@ionic/vue';

export default {
  name: "ResultsDepartements",
  components: {
    IonCard,
    IonCardHeader,
    IonCardTitle,
    IonCardSubtitle,
    IonCardContent,
    IonLabel,
    IonNote,
  },
  props: ['myData'],
}
</script>

<style scoped>

</style>