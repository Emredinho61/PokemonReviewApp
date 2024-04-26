<template>
    <div class="q-pa-md">
        <div class="q-gutter-md">
            <q-carousel v-model="slide" transition-prev="scale" transition-next="scale" swipeable animated
                control-color="blue" navigation padding arrows height="600px" class="shadow-1 rounded-borders">
                <q-carousel-slide name="style" class="column no-wrap flex-center">
                    <SeeResults></SeeResults>
                </q-carousel-slide>
                <q-carousel-slide name="tv" class="column no-wrap flex-center">
                    <q-icon name="live_tv" size="56px" />
                    <div class="q-mt-md text-center">
                        {{ lorem }}
                    </div>
                </q-carousel-slide>
                <q-carousel-slide name="layers" class="column no-wrap flex-center">
                    <q-icon name="layers" size="56px" />
                    <div class="q-mt-md text-center">
                        {{ lorem }}
                    </div>
                </q-carousel-slide>
                <q-carousel-slide name="map" class="column no-wrap flex-center">
                    <q-icon name="terrain" size="56px" />
                    <div class="q-mt-md text-center">
                        {{ lorem }}
                    </div>
                </q-carousel-slide>
            </q-carousel>
        </div>
    </div>
</template>

<script>
import { ref } from 'vue'
import SeeResults from 'components/SeeResults.vue'

export default {
    name: "CarouselOptions",
    components: {
        SeeResults,
    },
    setup() {
        return {
            slide: ref('style'),
            lorem: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo.'
        }
    }
}
</script>