<template>
    <ion-page>
        <ion-header>
            <ion-toolbar>
                <ion-title>Tab 3</ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-content :fullscreen="true">
            <ion-header collapse="condense">
                <ion-toolbar>
                    <ion-title size="large">Tab 3</ion-title>
                </ion-toolbar>
            </ion-header>

            <div v-for="number in [1,2,3,4,5,6,7,8,9,10]" :key="number">
                <ion-card button>
                    <ion-item>
                        <ion-label>{{number}}</ion-label>
                    </ion-item>

                    <ion-card-content>
                        This is content, without any paragraph or header tags,
                        within an ion-card-content element.
                    </ion-card-content>
                </ion-card>
            </div>
<!--            <ExploreContainer name="Tab 3 page"/>-->
        </ion-content>
    </ion-page>
</template>

<script lang="ts">
import {
    IonPage,
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent,
    IonCard,
    IonCardContent,
    IonItem,
    IonLabel,
    onIonViewDidEnter,
    onIonViewWillEnter
} from '@ionic/vue';
//import ExploreContainer from '@/components/ExploreContainer.vue';

export default {
    components: { IonLabel, IonItem, IonCard, IonCardContent, IonHeader, IonToolbar, IonTitle, IonContent, IonPage },
    setup () {
        let will = 0;
        let did = 0;

        onIonViewDidEnter(() => {
            did = Date.now();
            console.log('TAB 3 page did enter', did);
            console.log('DIFF TAB 3 ', did - will);
        });

        onIonViewWillEnter(() => {
            will = Date.now();
            console.log('TAB 3 page will enter', will);
        });
    }
};
</script>
