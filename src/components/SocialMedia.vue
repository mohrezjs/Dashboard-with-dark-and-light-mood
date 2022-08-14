<template>
    <div class="container mx-auto compo absolute xl:px-36 lg:px-10 pb-5 mt-10">
        <div class="flex flex-row items-center justify-between mt-10 flex-wrap">
            <div>
                <h1 class="font-bold text-3xl" :class="[{ darkTxtLight: this.isDark, lightTxtDark: this.isDark == false }]">
                    Social Media Dashboard
                </h1>
                <p class="font-bold" :class="[{ darkTxt: this.isDark, lightTxt: this.isDark == false }]">
                    Total Followers: 23,004
                </p>
            </div>
            <hr class="visible w-screen sm:invisible sm:w-auto my-3" />
            <div class="flex flex-row items-center w-screen justify-between px-2 sm:w-auto sm:p-0">
                <span class="font-bold mr-3" :class="[{ darkTxt: this.isDark, lightTxt: this.isDark == false }]">Dark Mode</span>
                <label class="switch">
                    <input type="checkbox" checked @click="changeBg()" />
                    <span class="slider round"></span>
                </label>
            </div>
        </div>

        <!-- card component -->
        <div class="flex flex-row justify-center sm:justify-between flex-wrap mt-7">
            <Cards :isDark="isDark" />
        </div>

        <div class="mt-10">
            <h1 class="font-bold text-3xl" :class="[{ darkTxtLight: this.isDark, lightTxtDark: this.isDark == false }]">
                Overview - Today
            </h1>
        </div>

        <!-- over view cards -->
        <div class="flex flex-row justify-center sm:justify-between flex-wrap">
            <Overview :isDark="isDark" />
        </div>
    </div>
</template>

<script>
import Cards from "./Cards.vue";
import Overview from "./Overview.vue";

export default {
    name: "SocialMedia",
    components: {
        Cards,
        Overview,
    },
    data() {
        return {
            isDark: true,
            bodyBg: document.querySelector("body"),
        };
    },

    methods: {
        changeBg() {
            this.isDark = !this.isDark;
        },
    },

    beforeMount() {
        this.bodyBg.style.backgroundImage = "url(" + require("@/assets/dark.png") + ")";
    },

    beforeUpdate() {
        if (this.isDark) {
            this.bodyBg.style.backgroundImage = "url(" + require("@/assets/dark.png") + ")";
        } else {
            this.bodyBg.style.backgroundImage = "url(" + require("@/assets/light.png") + ")";
        }
    },
};
</script>
