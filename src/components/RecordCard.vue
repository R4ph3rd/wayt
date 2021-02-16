<template>
    <li>
        <img src="" alt="record snapshot">
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
        },
        title: {
            type: String,
            required: true,
        },
        timeStamp: {
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