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
    height: calc(100% - #{$footerHeight});

    .pin{
        position: absolute;
        bottom:20px;
        left:0;
        display:block;
        width:max-content;
        transform: translateX(-15px);

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