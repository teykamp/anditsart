<template>
    <div>
        <b-container fluid class="footer">
            <b-row align-h="center">
                <b-col class="left" align-h="center">
                    <!-- <h4>Artists:</h4> -->
                    <h4>anditsart</h4>
                </b-col>
                <!-- <b-col class="right" align-h="center">Contact Us</b-col> -->
                <b-col class="right" align-h="center">
                    <a href="" >
                        <img class="logo" src="../assets/logofooter.svg">
                    </a>
                    <a href="https://github.com/" >
                        <img class="icon" src="https://cdn4.iconfinder.com/data/icons/iconsimple-logotypes/512/github-512.png">
                    </a>
                </b-col>
            </b-row>
            <p class="copyright">&copy; Copyright 2021 </p>
        </b-container>
    </div>
</template>

<script>
export default {
    // nothing yet
}
</script>

<style scoped>

.copyright {
    font-size: 15px;
    color: #0D2636;
}
.footer {
  position: relative;
  bottom: 0;
  width: 100%;
  height: 203px;
  background: #5f5fd3ff;
  padding-top: 50px;
}

.right {
    text-align: left;
    margin-left: 50px;
}

.left {
    text-align: right;
    margin-right: 50px;
    color: #0D2636;
}

.icon {
    height: 30px;
    width: 30px;
    margin-left: 20px;
}
.logo {
    height: 30px;
    width: 30px;
    transform: translateY(0);
}

.copyright {
    margin-top: 60px;
}
</style>