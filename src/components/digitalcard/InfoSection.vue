<template>
    <div class="pt-3">
        <div class="container">
            <div class="row rounded align-items-start">
                <div class="col-md-6 d-flex justify-content-center">
                    <img src="https://img101.urbanic.com/v1/goods-pic/3d7cf0e503fc4ad3b5ce3851dbdf584fUR_w1440_q90.webp"
                        alt="" class="rounded"
                        style="width: 320px; height: 320px;object-fit:cover; object-position: top;">
                </div>
                <div class="col-md-6 d-flex flex-column justify-content-center align-items-center mt-3 mt-md-0">

                    <p class="mb-0  fs-2 fw-bold text-capitalize">{{heading}}</p>

                    <p class="smaller text-ellipsis text-capitalize">{{ subheading }}</p>

                    <div class="d-md-flex justify-content-between align-items-start my-1 fs-5">
                        <div class="d-flex justify-content-center justify-content-md-start gap-2 align-items-start ">
                            <span>Fameset</span>
                            <i class="bi bi-star-fill text-warning"></i>
                            <span>8.5 Rating</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <TestimonialSection />
        <OffcanvasRating />
        <OffcanvasPromoters />
        <OffcanvasThankful />
    </div>
</template>

<script>
// import AutoCounter from '@/components/AutoCounter.vue';
import OffcanvasRating from '@/components/OffcanvasRating.vue';
import OffcanvasPromoters from '@/components/OffcanvasPromoters.vue';
import TestimonialSection from '@/components/TestimonialSection.vue';
import OffcanvasThankful from '@/components/OffcanvasThankful.vue';

export default {
    name: 'InfoSection',
    components: {
        // AutoCounter,
        OffcanvasRating,
        TestimonialSection,
        OffcanvasPromoters,
        OffcanvasThankful,
    },
    props:{
        heading: {
            type: String,
            required: true
        },
        subheading: {
            type: String,
            required: true
        }
    },
    data() {
        return {
            items: [
                {
                    id: 1,
                    iconClass: 'bi-chat-square-dots-fill',
                    count: 5,
                    label: 'Ratings',
                    offcanvasTarget: 'OffcanvasRating',
                    offcanvasTitle: 'Rate Us',
                    backgroundColor: '#000',
                    component: 'OffcanvasRating'
                },
                {
                    id: 2,
                    iconClass: 'bi-hand-thumbs-up-fill',
                    count: 50,
                    label: 'Promoters',
                    offcanvasTarget: 'PromoteSection',
                    offcanvasTitle: 'Promote Us',
                    backgroundColor: '#000',
                    component: 'PromoteSection'
                },
                {
                    id: 3,
                    iconClass: 'bi-trophy-fill',
                    count: 50,
                    label: 'Awards',
                    offcanvasTarget: 'AwardSection',
                    offcanvasTitle: 'Awards',
                    backgroundColor: '#FFF5DD',
                    component: 'AwardSection'
                },
                {
                    id: 4,
                    iconClass: 'bi-award-fill',
                    count: 50,
                    label: 'Rewards',
                    offcanvasTarget: 'RewardSection',
                    offcanvasTitle: 'Rewards',
                    backgroundColor: '#FFF5DD',
                    component: 'RewardSection'
                }
            ],
            fav: [
                {
                    iconClass: 'bi bi-hand-thumbs-up-fill',
                    iconColor: '#FFB2B2',
                    data: 50,
                    label: 'Promoters',
                    offcanvas: 'Promoter',
                },
                // {
                //     iconClass: 'bi bi-hearts',
                //     iconColor: '#BCDFFB',
                //     data: 10,
                //     label: 'Hearts',

                // },
                // {
                //     iconClass: 'bi bi-heart-fill',
                //     iconColor: '#BCDFFB',
                //     data: 10,
                //     label: 'Likes',

                // },
                {
                    iconClass: 'bi bi-chat-dots-fill',
                    iconColor: '#C9E7CA',
                    data: 10,
                    label: 'Reviews',
                    offcanvas: 'Review',
                },
                // {
                //     iconClass: 'bi bi-award-fill',
                //     iconColor: '#C9E7CA',
                //     data: 10,
                //     label: 'Rewards'
                // },
                {
                    iconClass: 'bi bi-shield-fill-check',
                    iconColor: '#FFB2B2',
                    data: 50,
                    label: 'Verified'
                },
                {
                    iconClass: 'bi bi-emoji-smile-fill',
                    iconColor: '#C9E7CA',
                    data: 10,
                    label: 'Thankful',
                    offcanvas: 'Thankful',
                },
                // {
                //     iconClass: 'bi bi-people-fill',
                //     iconColor: '#C9E7CA',
                //     data: 10,
                //     label: 'Reach'
                // },
            ],
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
            rating: 4.5,
            saveIcon: 'bi bi-heart',
            bookmarkIcon: 'bi bi-bookmark-plus',
            promoteIcon: 'bi bi-megaphone',
            saveText: 'Hearts',
            promoteText: 'Promote',
            addToFav: 'bi bi-heart',
            reviewButtonClass: 'btn btn-light',
            hover: false,
            counter: 0,
            likeIcon: 'bi bi-hand-thumbs-up',
            likeText: 'Like ',
            heartIcon: 'bi bi-heart',
            heartText: 'Heart',
        }
    },
    computed: {
        stars() {
            const fullStars = Math.floor(this.rating);
            const halfStar = this.rating % 1 !== 0;
            return Array.from({ length: 5 }, (_, index) => {
                if (index < fullStars) {
                    return 'full';
                } else if (index === fullStars && halfStar) {
                    return 'half';
                } else {
                    return 'empty';
                }
            });
        }
    },
    methods: {
        toggleIcon(buttonType) {
            if (buttonType === 'save') {
                this.reviewButtonClass = this.reviewButtonClass === 'btn btn-light' ? 'btn btn-danger' : 'btn btn-light';
                // this.saveText = this.saveText === 'Review Us' ? 'Reviewed' : 'Review Us';
            } else if (buttonType === 'like') {
                this.likeIcon = this.likeIcon === 'bi bi-heart' ? 'bi bi-heart-fill' : 'bi bi-heart';
                this.likeText = this.likeText === 'Like Us' ? 'Liked' : 'Like Us';
            } else if (buttonType === 'heart') {
                this.heartIcon = this.heartIcon === 'bi bi-heart' ? 'bi bi-heart-fill' : 'bi bi-heart';
                this.heartText = this.heartText === 'Heart' ? 'Liked' : 'Heart';
            } else if (buttonType === 'bookmark') {
                this.bookmarkIcon = this.bookmarkIcon === 'bi bi-bookmark-plus' ? 'bi bi-bookmark-check-fill' : 'bi bi-bookmark-plus';
                // this.favouriteText = this.favouriteText === 'Like Us' ? 'Liked' : 'Like Us';
            } else if (buttonType === 'favourite') {
                this.favouriteIcon = this.favouriteIcon === 'bi bi-hand-thumbs-up' ? 'bi bi-hand-thumbs-up-fill' : 'bi bi-hand-thumbs-up';
                this.favouriteText = this.favouriteText === 'Like Us' ? 'Liked' : 'Like Us';
            } else if (buttonType === 'promote') {
                this.promoteIcon = this.promoteIcon === 'bi bi-megaphone' ? 'bi bi-megaphone-fill' : 'bi bi-megaphone';
                this.promoteText = this.promoteText === 'Promote Us' ? 'Promoter' : 'Promote Us';
            }
        },
        submitHear(counter) {
            console.log(counter)
            this.counter = 0
        }
    }
}
</script>
<style scoped></style>
