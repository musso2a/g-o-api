<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Recherche par Région</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Region</ion-title>
        </ion-toolbar>
      </ion-header>
      
      <select-region @returnData="returnData"/>
    </ion-content>
    <results-region :myData="regionData"/>
  </ion-page>
</template>

<script>
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import SelectRegion from "@/components/SelectRegion";
import ResultsRegion from "@/components/ResultsRegion";

export default {
  name: 'Region',
  components: {ResultsRegion, SelectRegion, IonHeader, IonToolbar, IonTitle, IonContent, IonPage},
  data() {
    return {
      regionData: [],
    }
  },
  methods: {
    returnData(value) {
      this.regionData = value;
    }
  },
}


</script>