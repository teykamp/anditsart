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
}

.front {
    position: absolute;
    height: 30px;
    width: 30px;
    opacity: 0;
    transition-duration: 500ms;
    transition-delay: 500ms;
}
.mid {
    position: absolute;
    height: 30px;
    width: 30px;
    opacity: 0;
    transition-duration: 500ms;
    transition-delay: 250ms;
}
.back {
    position: absolute;
    height: 30px;
    width: 30px;
    opacity: 0;
    transition-duration: 500ms;
    transition-delay: 100ms;
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
/*
5f5fd3ff
2c2ca0ff
161650ff
 */
</style>