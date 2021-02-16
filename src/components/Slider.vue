<template>
    <div class="slider">

        <div class="pin">Today</div>
    </div>
</template>

<style lang="scss" scope>
.slider{
    position: absolute;
    top:0;
    left:0;
    height:100%;

    .pin{
        position: absolute;
        bottom:12px;
        left:0;
        display:block;
        width:max-content;
        transform: translateY(-15px);

        background-color: $primary;
        padding: 8px 20px;
        border-radius:0 8px 8px 0;

        text-align:left;
        font-size: 14px;
        font-weight: 600;
        color:white;
    }
}
    
</style>