<template>
  <DashboardNav v-if="!hide" />
  <router-view />
  <FooterBar v-if="!hidden" />
  <FameFoot v-if="!hidden" />
</template>
<script>
import DashboardNav from "@/components/DashboardNav.vue";
import FooterBar from "@/components/FooterBar.vue";
import FameFoot from "@/components/FameFoot.vue";
export default {
  name: "App",
  components: {
    DashboardNav,
    FooterBar,
    FameFoot
  },
  computed: {
    hide() {
      const hiddenPages = [
        'LoginPage', 'RegistrationPage', 'EmailVerificationPage', 'ForgotPasswordPage', 'ResetPasswordPage','HomePage',
        'BasicDetails', 'ConnectDetails', 'OverviewDetails', 'WorktimeDetails', 'BusinessTypeDetails', 'BrandingDetails',
        'ProductList', 'CreateProduct', 'CollectionList', 'RewardsDetails', 'DashboardPage',  'ReviewListPage','SupportersDetails','FamesetDetails','CategoryDetails','BankDetails','SocialDetails',
        'DigitalCard','CollectionPage', 'NotificationDetails','RequestDetails','ShowcaseDetails','TimelineDetails', 'TestimonialDetails','StoryCoursel',
      ]
      return hiddenPages.includes(this.$route.name)
    },
    hidden() {
      const hiddenPages = [
        'LoginPage', 'RegistrationPage', 'EmailVerificationPage', 'ForgotPasswordPage', 'ResetPasswordPage',
        'BasicDetails', 'ConnectDetails', 'OverviewDetails', 'WorktimeDetails', 'BusinessTypeDetails', 'BrandingDetails',
        'ProductList', 'CreateProduct', 'CollectionList', 'RewardsDetails', 'DashboardPage',  'SupportersDetails','FamesetDetails','CategoryDetails','BankDetails','SocialDetails','DigitalCard','CollectionPage',
        'NotificationDetails','RequestDetails','ShowcaseDetails','TimelineDetails','TestimonialDetails','DemoPage', 
      ]
      return hiddenPages.includes(this.$route.name)
    }
  }
}
</script>
<style lang="scss">
#app {
  // font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
.form-control{
  box-shadow: none !important;
}
:root {
  --bg-primary: #014c75;
  --bg-secondary: #EB5E28;
  --bg-tertiary: #FEC007;
  --bg-forth: #FBF4F4;
  --brand-color: #F5C518 !important
}

.text-ellipsis {
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

.text-ellipsis2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}
.text-ellipsis3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}
.text-ellipsis4 {
  display: -webkit-box;
  -webkit-line-clamp: 4;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

.text-ellipsis5 {
  display: -webkit-box;
  -webkit-line-clamp: 5;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;

}

.text-ellipsis7 {
  display: -webkit-box;
  -webkit-line-clamp: 7;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

.smaller {
  font-size: 12px !important;
}

#scroll::-webkit-scrollbar {
  display: none;
}

.bill {
  overflow: hidden;
  text-align: center;
}

.bill>span {
  position: relative;
  display: inline-block;
}

.bill>span:before,
.bill>span:after {
  content: "";
  position: absolute;
  top: 50%;
  width: 900px;
  /* Adjust width as needed */
  margin: 0 20px;
}

.bill>span:before {
  right: 100%;
  border-bottom: 2px solid;
  border-image: linear-gradient(to left, black 0, transparent 10%);
  border-image-slice: 1;
}

.bill>span:after {
  left: 100%;
  border-bottom: 2px solid;
  border-image: linear-gradient(to right, black 0, transparent 10%);
  border-image-slice: 1;
}
</style>
