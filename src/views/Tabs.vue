<template>
  <ion-page>
    <ion-tabs>
      <ion-tab-bar slot="bottom">

        <ion-tab-button tab="home" href="/tabs/home">
          <ion-icon name="home-outline" size="large"></ion-icon>
          <ion-label>Home</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="communes" href="/tabs/communes">
          <ion-icon name="navigate-circle-outline" size="large"></ion-icon>
          <ion-label>Communes</ion-label>
        </ion-tab-button>
          
        <ion-tab-button tab="departements" href="/tabs/departements">
          <ion-icon name="golf-outline" size="large"></ion-icon>
          <ion-label>Départements</ion-label>
        </ion-tab-button>
        
        <ion-tab-button tab="region" href="/tabs/region">
          <ion-icon name="map-outline" />
          <ion-label>Régions</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script >
import { IonTabBar, IonTabButton, IonTabs, IonLabel, IonIcon, IonPage } from '@ionic/vue';
import { homeOutline, mapOutline, golfOutline, navigateCircleOutline } from 'ionicons/icons';

export default {
  name: 'Tabs',
  components: { IonLabel, IonTabs, IonTabBar, IonTabButton, IonIcon, IonPage },
  setup() {
    return {
      homeOutline,
      mapOutline,
      golfOutline,
      navigateCircleOutline
    }
  }
}
</script>

<style scoped>
ion-icon {
  color: whitesmoke;
}

</style>