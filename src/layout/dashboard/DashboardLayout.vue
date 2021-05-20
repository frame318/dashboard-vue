<template>
  <div class="wrapper " >
    <side-bar>
      <template slot="links">
        <sidebar-link to="/dashboard" :name="$t('sidebar.dashboard')" icon="tim-icons icon-chart-pie-36"/>
        <sidebar-link to="/" :name="$t('Logs(Data)')" icon="tim-icons icon-app"/>
        <sidebar-link to="/" :name="$t('About PT')" icon="tim-icons icon-bank"/>
        <sidebar-link to="/" :name="$t('team')" icon="tim-icons icon-trophy"/>
        <sidebar-link to="/" :name="$t('tracking')" icon="tim-icons icon-zoom-split"/>
        <sidebar-link to="/" :name="$t('logout')" icon="tim-icons icon-minimal-left"/>
        <!-- <sidebar-link to="/typography" :name="$t('sidebar.typography')" icon="tim-icons icon-align-center"/>
        <sidebar-link to="/dashboard?enableRTL=true" :name="$t('sidebar.rtlSupport')" icon="tim-icons icon-world"/> -->
      </template>
    </side-bar>
    <div class="main-panel" >
      <top-navbar></top-navbar>

      <dashboard-content @click.native="toggleSidebar">

      </dashboard-content>

      <content-footer></content-footer>
    </div>
  </div>
</template>
<style lang="scss">
  
</style>
<script>
import TopNavbar from "./TopNavbar.vue";
import ContentFooter from "./ContentFooter.vue";
import DashboardContent from "./Content.vue";
import MobileMenu from "./MobileMenu";
export default {
  components: {
    TopNavbar,
    ContentFooter,
    DashboardContent,
    MobileMenu
  },
  methods: {
    toggleSidebar() {
      if (this.$sidebar.showSidebar) {
        this.$sidebar.displaySidebar(false);
      }
    }
  }
};
</script>
