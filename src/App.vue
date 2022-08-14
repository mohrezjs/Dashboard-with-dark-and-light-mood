<template>
    <SocialMedia />
</template>

<script>
import SocialMedia from "./components/SocialMedia.vue";
export default {
    name: "App",
    components: {
        SocialMedia,
    },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap");

body {
    font-family: "Inter", sans-serif;
}

/* for Cards in dark mood */

.darkBg {
    background-color:#252a41;
}

.darkTxt {
    color: #8b97c6;
}

.darkTxtLight {
    color: #ffffff;
}

/* for cards in light mood */

.lightBg {
    background-color: #f0f2fa;
}

.lightTxt {
    color: #63687e;
}

.lightTxtDark {
    color: #1e202a;
}

/* style for social media component */
.compo {
    z-index: 2;
    width: 100%;
    top: 0;
    right: 0;
    left: 0;
}

/* style for dark and light mood button */
.switch {
    position: relative;
    display: inline-block;
    width: 55px;
    height: 28px;
}

.switch input {
    opacity: 0;
    width: 0;
    height: 0;
}

.slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ccc;
    transition: 0.4s;
}

.slider:before {
    position: absolute;
    content: "";
    height: 23px;
    width: 23px;
    left: 3px;
    bottom: 3px;
    background-color: #1f212e;
    transition: 0.4s;
}

input:checked + .slider {
    background-image: -moz-linear-gradient(#378fe6, #3eda82);
}

input:focus + .slider {
    box-shadow: 0 0 1px -moz-linear-gradient(#378fe6, #3eda82);
}

input:checked + .slider:before {
    transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
    border-radius: 34px;
}

.slider.round:before {
    border-radius: 50%;
}

</style>
