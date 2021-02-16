<template>
    <ul class="timeline">
        <record-card 
            v-for="(card, i) in cards" 
            :key="card.title + i" 
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

                <q-btn class="fixed-top-right closebtn" round color="grey" icon="close" v-close-popup>
                </q-btn>

                <q-card-section>
                    <div class="text-h5">{{currentRecord.title}}</div>
                    <div class="text-h6">{{currentRecord.timestamp}}</div>
                    <q-btn dense flat icon="delete" size="lg" class="primary-shadow" @click="customBtn" />
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
        },
        customBtn () {
            this.$q.dialog({
                title: 'Are you sure ?',
                message: 'Would you like to delete this entry',
                ok: {
                label: 'Delete',
                push: true
                },
                cancel: {
                label: 'Cancel',
                push: true,
                color: 'secondary'
                },
                persistent: true
            }).onOk(() => {
                // console.log('>>>> OK')
            }).onCancel(() => {
                // console.log('>>>> Cancel')
            }).onDismiss(() => {
                // console.log('I am triggered on both OK and Cancel')
            })
        },
    },
    mounted(){
        this.$el.scrollTop = this.$el.scrollHeight;
        console.log(this.$el.scrollTop, this.$el.scrollHeight)
    }
}
</script>

<style lang="scss" scoped>
ul{
    height: calc(100vh - 80px - 16vh);
    overflow-y: scroll;

    -ms-overflow-style: none;  /* IE and Edge */
    scrollbar-width: none;  /* Firefox */

    &::-webkit-scrollbar {
        display: none;
    }

    li {
        position: relative;
        margin-bottom:20px;
    }

    &::before{
        z-index:-1;
        content: ' ';
        position:fixed;
        top:0;
        left:calc(50% - 2px);
        width:4px;
        height:100%;
        background: #21222410;
    }
}

.closebtn{
    margin-top:20px;
    margin-right:20px;
}
    
</style>