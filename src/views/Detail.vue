<template>
    <ion-page>
        <ion-header>
            <ion-header translucent>
                <ion-toolbar>
                    <ion-title>Detail page</ion-title>

                    <ion-buttons slot="start">
                        <ion-back-button text="Terug" default-href="/tabs/tab1"></ion-back-button>
                    </ion-buttons>
                </ion-toolbar>
            </ion-header>
        </ion-header>

        <ion-content>
            {{ route.params.id }}
        </ion-content>
    </ion-page>
</template>

<script>
import { IonPage, IonHeader, IonTitle, IonButtons, IonBackButton, IonIcon } from '@ionic/vue';
import { trashOutline, createOutline, ellipsisHorizontalCircleOutline } from 'ionicons/icons';
import { useRoute, useRouter } from 'vue-router';
import { defineComponent } from 'vue';

export default defineComponent({
    name: "DetailBeer",
    components: [
        IonPage, IonHeader, IonTitle, IonButtons, IonBackButton, IonIcon
    ],

    setup() {
        const router = useRouter();
        const route = useRoute();

        return {
            // Icons
            trashOutline,
            createOutline,
            ellipsisHorizontalCircleOutline,

            router,
            route
        }
    }
});
</script>

<style scoped>

</style>
