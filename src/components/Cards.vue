<template>
    <div
        class="flex flex-col w-64 rounded-md border-t-4 text-center mt-10 mx-2 md:mx-0 basis-2/4 sm:basis-1/3 md:basis-1/5"
        v-for="data in cardData"
        :key="data.id"
        :class="[
            {
                facebook: data.name == 'facebook',
                instagram: data.name == 'instagram',
                twitter: data.name == 'twitter',
                youtube: data.name == 'youtube',
                darkBg: isDark,
                lightBg: isDark == false,
            },
        ]"
    >
        <div class="flex flex-row justify-center items-center mt-6">
            <img class="mr-1" :src="data.logo" />
            <span class="ml-1 font-bold text-sm" :class="[{ lightTxt: isDark == false, darkTxt: isDark }]">{{ data.id }}</span>
        </div>
        <div class="flex flex-col">
            <h3 class="mt-7 text-5xl font-bold" :class="[{ darkTxtLight: isDark, lightTxtDark: isDark == false }]">
                {{ data.number }}
            </h3>
            <p class="font-normal text-sm" style="letter-spacing: 5px" :class="[{ lightTxt: isDark == false, darkTxt: isDark }]">{{ data.text }}</p>
        </div>
        <div class="my-6 text-sm font-bold mx-auto" :class="[{ up: data.up, down: data.up == false }]">{{ data.subtext }}</div>
    </div>
</template>

<script>
export default {
    name: "Cards",
    props: {
        isDark: Boolean,
    },
    data() {
        return {
            cardData: [
                {
                    name: "facebook",
                    logo: require("../assets/facebook.svg"),
                    id: "@nathanf",
                    number: 1987,
                    text: "FOLLOWERS",
                    subtext: "12 Today",
                    up: true,
                },
                {
                    name: "twitter",
                    logo: require("../assets/twitter.svg"),
                    id: "@nathanf",
                    number: 1044,
                    text: "FOLLOWERS",
                    subtext: "99 Today",
                    up: true,
                },
                {
                    name: "instagram",
                    logo: require("../assets/instagram.svg"),
                    id: "@realnathanf",
                    number: "11k",
                    text: "FOLLOWERS",
                    subtext: "1099 Today",
                    up: true,
                },
                {
                    name: "youtube",
                    logo: require("../assets/youtube.svg"),
                    id: "Nathan F.",
                    number: 8239,
                    text: "Subscribers",
                    subtext: "144 Today",
                    up: false,
                },
            ],
        };
    },
};
</script>

<style>

/* up triangle styles*/
.up {
    position: relative;
    color: #1db489;
}
.up::before {
    content: "\25B4";
    position: absolute;
    color: #1db489;
    left: -15px;
}

/* down triangle styles */
.down {
    position: relative;
    color: #dc414c;
}
.down::before {
    content: "\25Be";
    position: absolute;
    color: #dc414c;
    left: -15px;
}

/* social medias top border styles */
.facebook {
    border-color: #198ff5;
}
.twitter {
    border-color: #1ca0f2;
}
.instagram {
    border-color: #cf6a61;
}
.youtube {
    border-color: #c4032a;
}
</style>
