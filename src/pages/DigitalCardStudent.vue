<template>
  <div>
    <div class="container-fluid row g-0 pt-23">
      <div class="col-md-4 position-sticky sticky-container bg-dark">
        <DigitalCardNav :title="title" />
        <CarouselBanner :images="images" />
        <ResellerBottomNav />
      </div>
      <div class="px-md-5 col-md-8 mt-3 mt-md-0">
        <InfoSection heading="Students"
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
        { src: 'https://img101.urbanic.com/v1/goods-pic/3d7cf0e503fc4ad3b5ce3851dbdf584fUR_w1440_q90.webp', },
        { src: 'https://img101.urbanic.com/v1/goods-pic/2a8f2aed210c4841b9ef564e8c21ba3bUR_w1440_q90.webp', },
        { src: 'https://img101.urbanic.com/v1/goods-pic/f90d99ccd699497b9a4f1970823e8e11UR_w1440_q90.webp', }
      ],
      education: [
        {
          year: '2016',
          post: 'Academic Excellence Award',
          company: "Delhi Public School",
          points: [
            "Recognized as Top Student: Awarded for maintaining the highest GPA in the class for three consecutive semesters.",
            "Excellence in Coursework: Demonstrated exceptional performance in core subjects, including Mathematics, Science, and Literature.",
            "Leadership and Participation: Actively participated in academic clubs and led study groups, fostering a collaborative learning environment.",
            "Research and Projects: Completed advanced research projects that received commendations from faculty and contributed to school-wide academic initiatives.",
            "Consistent Improvement: Showed continuous improvement and dedication to academic growth, setting a positive example for peers."
          ],
        },
        {
          year: '2017',
          post: 'Community Service Leader',
          company: "Delhi Public School",
          points: [
            "Volunteer Coordination: Organized and led a team of 20 volunteers for various community service projects, including food drives, environmental clean-ups, and fundraising events.",
            "Project Impact: Successfully executed over 15 community service events, benefiting over 500 local residents and raising awareness on critical social issues.",
            "Collaboration with Organizations: Partnered with local non-profits and community groups to maximize the reach and effectiveness of service initiatives.",
            "Recognition: Received a certificate of appreciation from the city council for outstanding contributions to the community and exemplary leadership.",
            "Skills Development: Enhanced organizational, communication, and leadership skills through hands-on project management and team coordination.",
          ],
        },
      ],
      skills: [
        { bg: 'bg-danger', skill: 'Microsoft Office Suite', percent: '100' },
        { bg: 'bg-dark', skill: 'Programming Languages', percent: '50' },
        { bg: 'bg-primary', skill: 'Data Analysis', percent: '75' },
        { bg: 'bg-success', skill: 'Time Management', percent: '50' },
        { bg: 'bg-warning', skill: 'Project Management', percent: '75' },
        { bg: 'bg-info', skill: 'Team Leadership', percent: '100' },
        { bg: 'bg-info', skill: 'Decision Making', percent: '75' },
        { bg: 'bg-info', skill: 'Creativity', percent: '100' },
        { bg: 'bg-info', skill: 'Problem Solving', percent: '100' },
      ],
      courses: [
        { title: "Advanced Placement (AP) Course", description: "AP Biology: In-depth study of biological concepts, including genetics, evolution, and cellular processes. Emphasis on laboratory work and research projects.", },
        { title: "Honors Course", description: "Honors Physics: Exploration of fundamental physics concepts, including mechanics, electricity, and magnetism. Emphasis on problem-solving and experimental techniques.", },
        { title: "Elective Course", description: "Creative Writing: Development of writing skills through various genres, including poetry, short stories, and essays. Emphasis on creativity and self-expression.", },
        { title: "The Complete JavaScript Course", description: "Udemy.com", }
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
