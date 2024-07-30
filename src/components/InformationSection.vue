<template> 
    <div>
        <ul class="px-2 nav nav-pills justify-content-start align-items-center sticky-nav" id="pills-tab"
            role="tablist">
            <div class="d-flex overflow-x-scroll gap-1 p-2 pe-3 px-0 rounded" id="scroll">
                <li class="nav-item border rounded" role="presentation" v-for="(collection, index) in tabs"
                    :key="index">
                    <div class="d-md-flex justify-content-center align-items-center gap-2 nav-link p-2 text-dark"
                        style="background-color:rgba(255, 206, 86, 0.2); border:1px solid rgba(255, 206, 86, 1) !important;white-space:nowrap;"
                        :class="{ 'active': index === activeTabIndex }" :id="'tab-' + index" data-bs-toggle="pill"
                        :data-bs-target="'#content-' + index" role="tab" :aria-controls="'#content-' + index"
                        :aria-selected="index === activeTabIndex" @click="onTabClick(index)">
                        <p class="mb-0">{{ collection.name }}</p>
                        <p class="mb-0">{{collection.count}} + </p>
                    </div>
                </li>
            </div>
        </ul>
        <div class="tab-content mt-3" id="pills-tabContent">
            <div class="tab-pane fade" :class="{ 'show active': index === activeTabIndex }"
                v-for="(collection, index) in tabs" :key="index" :id="'content-' + index" role="tabpanel"
                :aria-labelledby="'tab-' + index" tabindex="0">
                <!-- <h3 class="text-center bill mb-4 "><span class="fs-2">~ {{ collection.name }} ~</span></h3> -->
                <component :is="collection.component" />
            </div>
        </div>
    </div>
    <!-- <div class="sticky-nav my-4">
        <div class="d-flex gap-3 p-3 ps-md-5 overflow-x-scroll py-3" id="scroll"
            style="background-color:rgba(255, 206, 86, 0.2); border:1px solid rgba(255, 206, 86, 1) !important;">
            <div v-for="(section, index) in sections" :key="index">
                <a :href="'#' + section.id" class="nav-link text-dark" @click.prevent="scrollToSection(section.id)"
                    :class="{ active: activeSection === section.id }">
                    {{ section.name }}
                </a>
            </div>
        </div>
    </div>

    <div class="container">
        <section v-for="(section, index) in sections" :key="index" :id="section.id" class="section"
            style="padding-top:30px">
            <h3 class="text-center bill mb-4 "><span class="fs-2">~ {{ section.name }} ~</span></h3>
            <component :is="section.component"></component>
        </section>
    </div> -->

</template>

<script>
// import ContactSection from '@/components/ContactSection.vue';
import TimelineSection from '@/components/TimelineSection.vue';
import AboutusSection from "@/components/AboutusSection.vue";
import AchievementsSection from "@/components/AchievementsSection.vue";
// import GalleryCollage from "@/components/GalleryCollage.vue";
import ReviewSection from "@/components/ReviewSection.vue";
import PromotionSection from '@/components/PromotionSection.vue';
export default {
    name: "InformationSection",
    components: {
        // ContactSection,
        AboutusSection,
        AchievementsSection,
        // GalleryCollage,
        TimelineSection,
        ReviewSection,
        PromotionSection,
    },
    data() {
        return {
            tabs: [
                { count:"10", id: 'Showcase', name: 'Showcase', component: 'AchievementsSection' },
                { count:"20", id: 'Review', name: 'Review', component: 'ReviewSection' },
                { count:"30", id: 'Timeline', name: 'Timeline', component: 'TimelineSection' },
                // { count:"40", id: 'Gallery', name: 'Gallery', component: 'GalleryCollage' },
                { count:"50", id: 'Promoters', name: 'Promoters', component: 'PromotionSection' },
                { count:"50", id: 'About', name: 'About', component: 'AboutusSection' },
                // { count:"60", id: 'connect', name: 'Connect', component: 'ContactSection' },
            ],
            activeTabIndex: 0,
            // activeSection: '',
        }
    },

    methods: {
        onTabClick(index) {
            this.activeTabIndex = index;
            this.scrollTabIntoView(index);
        },
        scrollTabIntoView(index) {
            const tabElement = document.getElementById(`tab-${index}`);
            if (tabElement) {
                tabElement.scrollIntoView({ behavior: 'smooth', inline: 'center', block: 'nearest' });
            }
        }
    }
}
</script>
<style scoped>
.nav-link.active {
    background-color: black !important;
    color: #FFF5DD !important;
    border-bottom: 2px solid red !important;
}



.sticky-nav {
    /* position: -webkit-sticky; */
    /* For Safari */
    position: sticky;
    top: 0px !important;
    z-index: 1000;
    background-color: white;
}
</style>