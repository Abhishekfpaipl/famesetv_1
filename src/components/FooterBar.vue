<template>
    <div class="container-fluid text-white pt-3" style="background-color: black !important;">
        <div class="row">
            <div class="col-12 col-md-4 mb-3">
                <router-link to="/">
                    <img :src="img" style="width: 100px;object-fit: contain;filter: invert(1);">
                </router-link>
                <p class="mb-0 fs-1 text-uppercase">Fameset</p>
            </div>

            <div class=" col-12 col-md-4 mb-3 text-center">
                <p class="mb-2 fw-bold">Contact Us</p>
                <p class="mb-2">Email : support@fameset.com</p>
                <p class="mb-2">Mob no. : 91 8860012001</p>
                <p class="mb-2">Address : 2nd Floor, Block B1/632, <br> Janakpuri, 110058, Delhi, India</p>
                <div class="d-flex gap-2 justify-content-center">
                    <p class="fw-bold">Follow Us :</p>
                    <i class="bi bi-twitter-x"></i>
                    <i class="bi bi-facebook"></i>
                    <i class="bi bi-linkedin"></i>
                    <i class="bi bi-youtube"></i>
                    <i class="bi bi-instagram"></i>
                </div>
            </div>
            <div class="col-12 col-md-4 d-flex justify-content-around">
                <div class="mb-3 text-start">
                    <p class="mb-2 fw-bold">Company</p>
                    <div class="d-flex flex-column">
                        <router-link :to="link.link" class="text-decoration-none my-1 text-white"
                            v-for="(link, index) in company" :key="index">{{ link.name }}</router-link>
                    </div>
                </div>
                <div class="mb-3 text-start">
                    <p class="mb-2 fw-bold">Resources</p>
                    <div class="d-flex flex-column">
                        <router-link :to="link.link" class="text-decoration-none my-1 text-white"
                            v-for="(link, index) in links" :key="index">{{ link.name }}</router-link>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <!-- <FameFoot /> -->
</template>

<script>
// import FameFoot from '@/components/FameFoot.vue'
export default {
    name: 'FooterBar',
    components: {
        // FameFoot,
    },
    data() {
        return {
            img: '/img/logo.svg',
            company: [
                {
                    id: 4,
                    name: 'Contact Us',
                    link: '/contact-us'
                },
                {
                    id: 42,
                    name: 'About Us',
                    link: '/about-us'
                },
                {
                    id: 3,
                    name: 'Authorized seller',
                    link: '/authorized-reseller'
                },
                {
                    id: 3,
                    name: 'Bulk seller',
                    link: '/bulk-seller'
                },
                {
                    id: 9,
                    name: 'Career',
                    link: '/career'
                },
                {
                    id: 9,
                    name: 'List your business',
                    link: '/list-your-business'
                },
                {
                    id: 9,
                    name: 'Explore',
                    link: '/explore'
                },
            ],
            links: [
                {
                    id: 13,
                    name: 'Legal',
                    link: '/legal-warning'
                },
                {
                    id: 1,
                    name: 'Privacy Policy',
                    link: '/privacy-policy'
                },
                {
                    id: 1,
                    name: 'Terms Of Use',
                    link: '/term-of-use'
                },
                {
                    id: 3,
                    name: 'Business',
                    link: '/business'
                },
                {
                    id: 3,
                    name: 'Business Account',
                    link: '/business-seller'
                },

            ],
        }
    },
}
</script>

<style></style>
