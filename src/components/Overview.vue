<template>
    <div
        class="flex flex-col w-64 rounded-md text-center mt-10 mx-0.5 md:mx-0.5 basis-2/4 sm:basis-1/3 lg:basis-1/5 justify-around"
        v-for="data in overData"
        :key="data.number"
        :class="[{ darkBg: isDark, lightBg: isDark == false }]"
    >
        <div class="flex flex-row justify-between mx-7 items-center mt-7">
            <span class="font-bold" :class="[{ lightTxt: isDark == false, darkTxt: isDark }]">{{ data.text }}</span>
            <img :src="data.logo" />
        </div>
        <div class="flex flex-row justify-between items-end mt-6 mx-7 pb-6">
            <h3 class="text-3xl font-bold" :class="[{ darkTxtLight: isDark, lightTxtDark: isDark == false }]">
                {{ data.number }}
            </h3>
            <p class="text-sm font-bold" :class="[{ up: data.up, down: data.up == false }]">{{ data.subtext }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: "Overview",
    props: {
        isDark: Boolean,
    },
    data() {
        return {
            overData: [
                {
                    logo: require("../assets/facebook.svg"),
                    number: 87,
                    text: "Page Views",
                    subtext: "3%",
                    up: true,
                },
                {
                    logo: require("../assets/facebook.svg"),
                    number: 52,
                    text: "Likes",
                    subtext: "2%",
                    up: false,
                },
                {
                    logo: require("../assets/instagram.svg"),
                    number: 5462,
                    text: "Likes",
                    subtext: "2257%",
                    up: true,
                },
                {
                    logo: require("../assets/instagram.svg"),
                    number: "52k",
                    text: "Profile Views",
                    subtext: "1375%",
                    up: true,
                },
                {
                    logo: require("../assets/twitter.svg"),
                    number: 117,
                    text: "Retweets",
                    subtext: "303%",
                    up: true,
                },
                {
                    logo: require("../assets/twitter.svg"),
                    number: 507,
                    text: "Likes",
                    subtext: "553%",
                    up: true,
                },
                {
                    logo: require("../assets/youtube.svg"),
                    number: 107,
                    text: "Likes",
                    subtext: "19%",
                    up: false,
                },
                {
                    logo: require("../assets/youtube.svg"),
                    number: 1407,
                    text: "Total Views",
                    subtext: "12%",
                    up: false,
                },
            ],
        };
    },
};
</script>
