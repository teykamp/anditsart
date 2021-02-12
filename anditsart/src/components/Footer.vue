<template>
    <div>
        <b-container fluid class="footer">
            <b-row align-h="center">
                <b-col class="left" align-h="center">
                    <img class="logo" src="../assets/logo.png">
                    <a href="https://github.com/" >
                        <img class="icon" src="https://cdn4.iconfinder.com/data/icons/iconsimple-logotypes/512/github-512.png">
                    </a>
                </b-col>
                <b-col class="right" align-h="center">
                    <h4>Artists:</h4>
                    <p>Me</p>
                    <p>You</p>
                </b-col>
                <!-- <b-col class="right" align-h="center">Contact Us</b-col> -->
            </b-row>
        </b-container>
    </div>
</template>

<script>
export default {
    // nothing yet
}
</script>

<style scoped>

.footer {
  position: relative;
  bottom: 0;
  width: 100%;
  height: 203px;
  background: red;
  padding-top: 50px;
}

.left {
    text-align: right;
    margin-right: 50px;
}

.right {
    text-align: left;
    margin-left: 50px;
}

.icon {
    height: 30px;
    width: 30px;
    margin-left: 20px;

}
</style>