<template>
  <ion-item>
    <ion-label position="stacked">Ville ou Commune</ion-label>
    <ion-input v-model="communeSearch"></ion-input>
  </ion-item>
  <ion-button expand="block" @click="input()">Recherche</ion-button>
</template>

<script>
import {IonLabel, IonInput, IonItem, IonButton} from '@ionic/vue';

export default {
name: "SearchCommunes",
  components: {
    IonLabel,
    IonInput,
    IonButton,
    IonItem
  },
  data() {
    return {
      communeSearch: "",
      data: [],

    }
  },

  methods: {
    input: function () {
      if (parseInt(this.communeSearch)) {
        fetch(`https://geo.api.gouv.fr/communes?codePostal=`+this.communeSearch+`&fields=region,departement,population,codesPostaux&boost=population`).then((response)=>{
          response.json().then((data)=> {
            this.$emit('inputData', data);
            console.log("chiffre");
            console.log(data);
          });
        });
      }
      else {
        fetch(`https://geo.api.gouv.fr/communes?nom=`+this.communeSearch+`&fields=region,departement,population,codesPostaux&boost=population`).then((response)=>{
          response.json().then((data)=> {
            this.data = data;
            this.$emit('inputData', this.data);
            console.log("nom");
            console.log(data);
          });
        });

      }
        
      }
    }
  }


</script>

<style scoped>

</style>