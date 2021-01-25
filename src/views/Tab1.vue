<template>
    <ion-page>
        <ion-header>
            <ion-toolbar>
                <ion-title>Tab 1</ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-content :fullscreen="true">
            <ion-item-sliding v-for="item in items"
                              :key="item.id">
                <ion-item detail="false"
                          @click="router.push(`/tabs/tab1/${ item.id }`)"
                          button>
                    <ion-icon :icon="trophyOutline"
                              slot="end"></ion-icon>
                    <ion-label>
                        <h2>{{ item.name }}</h2>
                    </ion-label>
                </ion-item>

                <ion-item-options side="start">
                    <ion-item-option>
                        <ion-icon slot="icon-only"
                                  :icon="createOutline"></ion-icon>
                    </ion-item-option>
                </ion-item-options>
            </ion-item-sliding>
        </ion-content>
    </ion-page>
</template>

<script>
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonItemOptions, IonItemOption } from '@ionic/vue';
import { ref }                                                                                 from 'vue';
import { useRouter }                                                                           from 'vue-router';

export default {
    name: 'Tab1',
    components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonItemOptions, IonItemOption },

    setup() {
        const router = useRouter();

        const items = ref([
            {
                name: 'item 1',
                id: 1
            },
            {
                name: 'item 2',
                id: 2
            }
        ])

        return {
            items,
            router
        }
    }
}
</script>
