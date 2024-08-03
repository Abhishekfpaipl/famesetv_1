<template>
  <div>
    <div class="container-fluid row g-0 pt-23">
      <div class="col-md-4 position-sticky sticky-container bg-dark">
        <DigitalCardNav :title="title" />
        <CarouselBanner :images="images" />
        <ResellerBottomNav />
      </div>
      <div class="px-md-5 col-md-8 mt-3 mt-md-0">
        <InfoSection heading="Employees"
          subheading="Data entry clerk, finance speciaist, payroll coordinator, general manager, accountant, management analyst" />
        <InformationSection :skills="skills" :education="education" :courses="courses" />
      </div>
    </div>
  </div>
</template>

<script>
// import TopSection from '@/components/digitalcard/TopSection.vue'
import DigitalCardNav from '@/components/DigitalCardNav.vue';
import InfoSection from '@/components/digitalcard/InfoSection.vue';
import InformationSection from '@/components/InformationSection.vue';
import CarouselBanner from '@/components/ResellerCarousel.vue';
import ResellerBottomNav from '@/components/ResellerBottomNav.vue';

export default {
  name: "DigitalCard",
  components: {
    DigitalCardNav,
    // TopSection,
    InfoSection,
    InformationSection,
    CarouselBanner,
    ResellerBottomNav,
  },
  data() {
    return {
      title: "Digital Card",
      images: [
        {
          src: 'https://img101.urbanic.com/v1/goods-pic/3d7cf0e503fc4ad3b5ce3851dbdf584fUR_w1440_q90.webp',
          // alt: 'First slide',
          // label: 'First slide label',
          // content: 'Some representative placeholder content for the first slide.'
        },
        {
          src: 'https://img101.urbanic.com/v1/goods-pic/2a8f2aed210c4841b9ef564e8c21ba3bUR_w1440_q90.webp',
          // alt: 'Second slide',
          // label: 'Second slide label',
          // content: 'Some representative placeholder content for the second slide.'
        },
        {
          src: 'https://img101.urbanic.com/v1/goods-pic/f90d99ccd699497b9a4f1970823e8e11UR_w1440_q90.webp',
          // alt: 'Third slide',
          // label: 'Third slide label',
          // content: 'Some representative placeholder content for the third slide.'
        }
      ],
      courses: [
        { title: "Web Design for Everybody Specialization Course", description: "University of Michigan (Online Course)", },
        { title: "Front End Web Developer Learning Path", description: "Lynda.com", },
        { title: "Web Developer Bootcamp Course", description: "Udemy.com", },
        { title: "The Complete JavaScript Course", description: "Udemy.com", },
        { title: "Post-Graducation (M.Tech)", description: "Delhi University", },
        { title: "Graducation (B.Tech)", description: "Delhi University", },
        { title: "High Secondary  (12th)", description: "Delhi Police School", },
        { title: "High School (10th)", description: "Delhi Police School", },
      ],
      skills: [
        { bg: 'bg-danger', skill: 'HTML', percent: '100' },
        { bg: 'bg-dark', skill: 'CSS3', percent: '50' },
        { bg: 'bg-primary', skill: 'JavaScript', percent: '75' },
        { bg: 'bg-success', skill: 'jQuery', percent: '50' },
        { bg: 'bg-warning', skill: 'Php', percent: '75' },
        { bg: 'bg-info', skill: 'sql', percent: '75' },
        { bg: 'bg-info', skill: 'Adobe Creative Suite', percent: '75' },
        { bg: 'bg-info', skill: 'WordPress', percent: '100' },
        { bg: 'bg-info', skill: 'XML', percent: '100' },
      ],
      education: [
        {
          year: '2016 - present',
          post: 'Web Developer',
          company: "Precious Technology Co.",
          points: [
            "Design and establish user-friendly websites, including optimized check-out page, resulting in a 25% increase in user clicks and subsequently 33% in customer purchases.",
            "Provide adequate training to 60+ staff members and 20+ junior web developers in internal web functions, including steps on how to make minor updates/changes independently.",
            "Establish an interactive and dynamic website that guarantees high traffic, page views, and maximum user experience, generating a 45% increase in the company's sales revenue.",
            "Administer the full lifecycle of software development for 12 critical projects of the company with 100% on-time delivery while staying 7% under budget.",
            "Conceptualize and enforce a server that accelerated document generation as well as the search- functionality of current websites by 15%, garnering consistent commendation and award from the top management."
          ],
        },
        {
          year: '2012 - 2016',
          post: 'Web Developer',
          company: "Virtual Solutions International Company",
          points: [
            "Formulated and implement improvements on cleanup processes and performance, minimizing downtime by 10%.",
            "Devised various custom responsive WordPress sites from design comps that included advanced WordPress features, such as Custom Post Types, Advanced Custom Fields, and WordPress Customize API.",
            "Diagnosed and troubleshoot different websites of the company's critical clients by deploying updated knowledge of the modern technologies and techniques in the industry.",
            "Proactively liaised with the design team and project manager to ensure efficient and timely delivery of significant projects.",
          ],
        },
      ],
    }
  }
};
</script>

<style scoped>
@media (min-width: 768px) {
  .sticky-container {
    top: 50px;
    position: -webkit-sticky;
    /* For Safari */
    position: sticky;
    height: 100vh;
    /* Ensures full height */
    /* overflow-y: auto; */
    /* Adds scrolling if needed */
  }
}

@media (max-width: 767px) {
  .sticky-container {
    position: initial !important;
  }
}
</style>
