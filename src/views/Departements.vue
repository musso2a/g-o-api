<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Recherche par Département</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Departements</ion-title>
        </ion-toolbar>
      </ion-header>

      <select-departements  @returnData="returnData"/>

    </ion-content>
    <results-departements :myData="departementData"/>
  </ion-page>
</template>

<script >
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import SelectDepartements from "@/components/SelectDepartements";
import ResultsDepartements from "@/components/ResultsDepartements";

export default  {
  name: 'Departements',
  components: {ResultsDepartements, SelectDepartements, IonHeader, IonToolbar, IonTitle, IonContent, IonPage },
data() {
  return {
    departementData: [],
  }
},
methods: {
  returnData(value) {
    this.departementData = value;
  }
},
}
</script>