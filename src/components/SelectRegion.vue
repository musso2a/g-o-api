<template>
  <ion-item>
    <ion-label>Région :</ion-label>
    <ion-select ok-text="Okay" cancel-text="Nah" v-model="regionListed">
      <ion-select-option :value="region.code" v-for="region in regionReturn" :key="region">{{region.nom}}</ion-select-option>
    </ion-select>
  </ion-item>
  <ion-button expand="block" @click="getTheRegion()">Recherche</ion-button>
</template>

<script>
import {IonLabel, IonSelect, IonSelectOption, IonItem, IonButton} from '@ionic/vue';

export default {
  emits: ["myData"],
name: "SelectRegion",
  components: {
  IonLabel,
    IonSelect,
    IonSelectOption,
    IonItem,
    IonButton,
  },
  methods : {
    regionList: function () {
      fetch(`https://geo.api.gouv.fr/regions/`).then((response) => {
        response.json().then((data) => {
          this.regionReturn = data;
          console.log("page region");
        });
      });
    },
    getTheRegion: function () {
      fetch(`https://geo.api.gouv.fr/regions/` + this.regionListed + `/departements`).then((response) => {
        response.json().then((data) => {
          this.data = data;
          this.$emit('returnData', this.data);
          console.log("page region");
          console.log(data);
        });
      });
    }
  },
  data() {
    return {
      regionListed: "",
      selectedRegion: "",
      regionReturn: [],
      data: [],
    }
},
  mounted() {
    this.regionList();
  }
}
</script>

<style scoped>

</style>