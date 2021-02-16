<template>
    <li>
        <img :src="imgSource" alt="record snapshot">
        <div>
            <p>{{title}}</p>
            <p>{{timestamp}}</p>

            <p>{{duration}}</p>
        </div>
    </li>
</template>

<script>
export default {
    name: 'RecordCard',
    props: {
        imgSource: {
            type: String,
            required: false,
            default: () => 'records/theo_le_bg.png'
        },
        title: {
            type: String,
            required: true,
        },
        timestamp: {
            type: String,
            required: true,
        },
        duration: {
            type: String,
            required: true,
        }
    }
}
</script>

<style lang="scss" scoped>
    li{
        display:grid;
        grid-template-columns: 27vw auto;
        grid-auto-rows:120px;
        grid-column-gap:15px;

        &:hover{
            cursor: pointer;
        }

        img{
            object-fit: cover;
            width:100%;
            height:100%;

            border: 4px solid #EBEBEB50;
            border-radius: 21px;
            background:#F7F7F7;
        }

        div{
            position: relative;

            p:first-child{
                font-weight:600;
                font-size: 15px;
                margin-bottom:2px;
            }

            p:nth-child(2){
                font-weight: 400;
                font-size:15px;
                text-transform: uppercase;
            }

            p:last-child{
                position: absolute;
                bottom:0;
                right:8px;
                font-weight: 300;
                font-size:15px;

                &::after{
                    content: ' ';
                    position:absolute;
                    top: -8px;
                    right: -8px;

                    border-radius:8px;
                    width:8px;
                    height:8px;
                    background-color: $primary;
                }
            }
        }
    }
    
</style>