<template>
    <div class="parent">
        <img class="full" src="../assets/logo1.svg" />
        <img class="back" src="../assets/logo_back.svg" />
        <img class="mid" src="../assets/logo_mid.svg" />
        <img class="front" src="../assets/logo_front.svg" />
    </div>
</template>

<script>
export default {
    // nothing yet
}
</script>

<style scoped>

.parent {
    position: relative;
    top: 0;
    left: 0;
    animation-direction: alternate;

}

.full {
    position: absolute;
    height: 30px;
    width: 30px;
    transform: scale(1.5);
    box-shadow: drop-shadow(0px 14px 8px 2px rgba(0,0,0,0.76)
);
}

.front {
    position: absolute;
    height: 30px;
    width: 30px;
    opacity: 0;
    transition-duration: 500ms;
    transition-delay: 100ms;
    z-index: 5;
}
.mid {
    position: absolute;
    height: 30px;
    width: 30px;
    opacity: 0;
    transition-duration: 500ms;
    transition-delay: 250ms;
    z-index: 2;
}
.back {
    position: absolute;
    height: 30px;
    width: 30px;
    opacity: 0;
    transition-duration: 500ms;
    transition-delay: 500ms;
    z-index: 1;
}


.parent:hover > .front {
    opacity: 1;
    transform: scale(1.5);
}
.parent:hover > .mid {
    opacity: 1;
    transform: scale(1.5);
}
.parent:hover > .back {
    opacity: 1;
    transform: scale(1.5);
}

</style>