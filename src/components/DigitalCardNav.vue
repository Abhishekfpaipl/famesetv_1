<template>
    <div class="containerr text-bg-dark position-fixed top-0 col-md-4 col-12 py-md-2 px-md-3 pe-md-0 p-1"
        style="z-index: 99; min-height:80px !important;">
        <div class="d-flex justify-content-between align-items-start">
            <div class="flex-fill d-flex gap-2 align-items-center position-relative">
                <img src="/img/members/12.jpg" class="rounded" style="width: 50px;height: 50px;" alt="">
                <div class="flex-fill d-flex flex-column align-items-start">
                    <div class="w-100 d-flex gap-2 justify-content-between align-items-center pe-2">
                        <p class="mb-0 text-start text-white">{{ title }}</p>
                        <i class="bi bi-share fs-5"></i>
                    </div>
                    <div class="d-flex justify-content-start w-50 overflow-x-scroll my-2 gap-2" id="scroll">
                        <img :src="image" style="width: 20px; height: 20px; object-fit: contain;"
                            v-for="image in images" :key="image.id" alt="">
                    </div>
                </div>
                <div class="position-absolute end-0 smaller" style="bottom: 10px;">
                    <div class="d-flex gap-1 align-items-start rounded-start-3 px-2 text-dark bg-warning">
                        <span>Fameset</span>
                        <i class="bi bi-star-fill"></i>
                        <span>8.5</span>
                    </div>
                </div>
            </div> 
        </div>
    </div>
</template>

<script>
export default {
    name: 'ProductTopnav',
    props: {
        title: {
            type: String,
        }
    },
    data() {
        return {
            backgroundOpacity: 0,
            hideOnScroll: true,
            bookmarkIcon: 'bi bi-bookmark-plus',
            images: [
                "/img/members/1.png",
                "/img/members/2.webp",
                "/img/members/3.png",
                "/img/members/4.png",
                "/img/members/5.jpg",
                "/img/members/6.webp",
                "/img/members/7.jpeg",
                "/img/members/8.png",
            ],
        };
    },
    methods: {
        toggleIcon(buttonType) {
            if (buttonType === 'bookmark') {
                this.bookmarkIcon = this.bookmarkIcon === 'bi bi-bookmark-plus' ? 'bi bi-bookmark-check-fill' : 'bi bi-bookmark-plus';
            }
        },
        goBack() {
            window.history.back();
        }
    }
};
</script>
