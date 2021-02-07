<template>
  <ion-item>
    <ion-label>Département :</ion-label>
    <ion-select ok-text="Okay" cancel-text="Nah" v-model="departementListed">
      <ion-select-option :value="departement.code" v-for="departement in departementReturn" :key="departement">{{departement.nom}} -{{departement.code}}- </ion-select-option>
    </ion-select>
  </ion-item>
  <ion-button expand="block" @click="getTheDepartement">Recherche</ion-button>
</template>

<script>
import {IonLabel, IonSelect, IonSelectOption, IonItem, IonButton} from '@ionic/vue';

export default {
  emits: ["myData"],
name: "SelectDepartements",
  components: { IonLabel, IonSelectOption, IonItem ,IonSelect, IonButton },
methods : {
  departementList: function () {
    fetch(`https://geo.api.gouv.fr/departements`).then((response) => {
      response.json().then((data) => {
        this.departementReturn = data;
        console.log("page departement");
      });
    });
  },
  getTheDepartement: function () {
    fetch(`https://geo.api.gouv.fr/departements/` + this.departementListed + `/communes`).then((response) => {
      response.json().then((data) => {
        this.data = data;
        this.$emit('departementData', this.data);
        console.log("page departement");
        console.log(data);
      });
    });
  }
},
data() {
  return {
    departementListed: "",
    selectedDepartement: "",
    departementReturn: [],
    data: [],
  }
},


mounted() {
  this.departementList();
}

}
</script>

<style scoped>

</style>