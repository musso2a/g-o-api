<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Recherche par Commune</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
<!--      <ion-header collapse="condense">-->
<!--        <ion-toolbar>-->
<!--          <ion-title size="large">Commune</ion-title>-->
<!--        </ion-toolbar>-->
<!--      </ion-header>-->
    
      <search-communes @inputData="myData"/>
    </ion-content>
    <results-communes :myData="myDatas"/>
  </ion-page>
</template>

<script>
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import SearchCommunes from "@/components/SearchCommunes";
import ResultsCommunes from "@/components/ResultsCommunes";

export default  {
  name: 'Communes',
  components: {ResultsCommunes, SearchCommunes, IonHeader, IonToolbar, IonTitle, IonContent, IonPage },

  data() {
  return {
    myDatas: [],
  }
  },
  methods : {
    myData(value) {
      this.myDatas = value;
    }
  },
}

</script>