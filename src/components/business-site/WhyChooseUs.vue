<template>
    <div class="" >
        <div class="container px-3 px-md-0">
            <h1 class="text-center text-capitalize">Lots of other features</h1>
            <h4 class="text-center text-capitalize">to manage your fame</h4>
            <div class="row d-flex justify-content-center pb-5 pt-2">
                <div class="col-lg-4 row row-cols-1 g-3 mt-0">
                    <div v-for="(service, index) in servicesLeft" :key="index" class="col">
                        <div class="d-flex align-items-start">
                            <i class="bi fs-4 pe-4" :class="service.icon"></i>
                            <div class="d-flex flex-column text-start flex-fill">
                                <p class="fs-5 fw-b title mb-0">{{ service.title }}</p>
                                <small class="smaller fw-light mb-0">{{ service.description }}</small>
                            </div>
                        </div>
                    </div>
                </div>


                <div class="col-lg-4 overflow-hidden p-5 mt-0">
                    <img src="/img/whychoose.svg" class="h-100 w-100 of-cover">
                </div>


                <div class="col-lg-4 row row-cols-1 g-3 mt-0">
                    <div v-for="(service, index) in servicesRight" :key="index" class="col">
                        <div class="d-flex align-items-start">
                            <i class="bi fs-5 pe-4" :class="service.icon"></i>
                            <div class="d-flex flex-column text-start flex-fill">
                                <p class="fs-5 fw-b title mb-0">{{ service.title }}</p>
                                <small class="smaller fw-light mb-0">{{ service.description }}</small>
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "OurService",
    data() {
        return {
            servicesLeft: [
                {
                    id: 1,
                    title: "Contact Details",
                    icon: "bi-headset",
                    description: "Providing round-the-clock support to address your needs anytime, anywhere.",
                },
                {
                    id: 2,
                    title: "Social Profiles",
                    icon: "bi-person-square",
                    description: "Ensuring the highest standards of quality in every project we deliver.",
                },
                {
                    id: 3,
                    title: "Skillset",
                    icon: "bi-pie-chart ",
                    description: "Offering fully tailored solutions to meet your unique business requirements.",
                },
                {
                    id: 4,
                    title: "Timeline",
                    icon: "bi-clock-history",
                    description: "Delivering high-quality services at affordable and competitive prices.",
                },
                {
                    id: 4,
                    title: "Share",
                    icon: "bi-share",
                    description: "Delivering high-quality services at affordable and competitive prices.",
                },
            ],
            servicesRight: [
                {
                    id: 1,
                    title: "Qr Code",
                    icon: "bi-qr-code",
                    description: "Proven success and reliability in delivering exceptional results.",
                },
                {
                    id: 2,
                    title: "Website Widget",
                    icon: "bi-window-plus",
                    description: "A decade of experience and expertise in the industry.",
                },
                {
                    id: 3,
                    title: "Fun Facts",
                    icon: "bi-123",
                    description: "Minimized maintenance expenses for long-term savings.",
                },
                {
                    id: 4,
                    title: "Attributes",
                    icon: "bi-stars",
                    description: "Scalable solutions to accommodate businesses of all sizes.",
                },
                {
                    id: 4,
                    title: "Payment",
                    icon: "bi-bank",
                    description: "Scalable solutions to accommodate businesses of all sizes.",
                },
            ]
        }
    }
}
</script>
<style lang="">

</style>