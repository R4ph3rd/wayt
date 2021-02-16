<template>
    <ul class="timeline">
        <record-card 
            v-for="card in cards" 
            :key="card.title" 
            :title="card.title"
            :timestamp="card.timestamp"
            :duration="card.duration"
            @click.native="openRecord(card)"
        ></record-card>

            <q-dialog
            v-model="dialog"
            persistent
            :maximized="maximizedToggle"
            transition-show="slide-up"
            transition-hide="slide-down"
            >
            <q-card class="bg-primary text-white flex content-end">

                <q-btn round color="grey" icon="close" v-close-popup>
                    <q-tooltip content-class="bg-white text-primary">Close</q-tooltip>
                </q-btn>

                <q-card-section>
                    <div class="text-h5">{{currentRecord.title}}</div>
                    <div class="text-h6">{{currentRecord.timestamp}}</div>
                    <q-btn dense flat icon="delete" size="lg" class="primary-shadow"></q-btn>
                    <q-btn dense flat icon="more_vert" size="lg" class="primary-shadow"></q-btn>
                </q-card-section>
            </q-card>
            </q-dialog>
    </ul>
</template>

<script>
import recordCard from '../components/RecordCard';

export default {
    name: 'Timeline',
    components:{
        'record-card': recordCard
    },
    data(){
        return {
            dialog: false,
            maximizedToggle: true,
            currentRecord: {},
            cards: [
                {
                    title: 'Tue, 26th',
                    timestamp: '6:00 pm',
                    duration: '15:00'
                },
                {
                    title: 'Wed, 27th',
                    timestamp: '6:01 pm',
                    duration: '06:00'
                },
                {
                    title: 'Thu, 28th',
                    timestamp: '6:02 pm',
                    duration: '12:00'
                },
            ]
        }
    },
    methods: {
        openRecord(record){
            this.currentRecord = record;
            this.dialog = !this.dialog;
        }
    }
}
</script>

<style lang="scss" scoped>
ul{
    & > * {
        margin-bottom:20px;
    }
}
    
</style>