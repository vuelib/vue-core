<template>
  <div id="app">

    <ess-toolbar>

      <div>

        <!-- <ess-button type="cleaned" size="small" id="pages-btn">
          Pages
        </ess-button>

        <ess-tooltip target="pages-btn"> Your pages </ess-tooltip>

        <ess-button type="cleaned" size="small" id="features-btn">
          Features
        </ess-button>

        <ess-tooltip target="features-btn"> Your features </ess-tooltip>

        <ess-button type="cleaned" size="small" id="apps-btn">
          Apps
        </ess-button>

        <ess-tooltip target="apps-btn"> Your applications </ess-tooltip> -->

        <ess-tabs v-model="tab" color="primary">
          <ess-tab name="pages"> Pages </ess-tab>
          <ess-tab name="features"> Features </ess-tab>
          <ess-tab name="apps"> Apps </ess-tab>
          <ess-tab name="deploy"> Deployment Center </ess-tab>
          <ess-tab name="search"> <i class="fas fa-search"></i> </ess-tab>
        </ess-tabs>

        <!-- <ess-menu target="apps-btn">
          <ess-list>
            <ess-list-item> Reporting </ess-list-item>
            <ess-list-item> Social Presence </ess-list-item>
            <ess-list-item> Sales & marketing </ess-list-item>
            <ess-list-item> Campaigns </ess-list-item>
            <ess-separator />
            <ess-list-item> Deployment Center </ess-list-item>
          </ess-list>
        </ess-menu> -->
      </div>

      <div>

        <ess-float-button type="cleaned" shape="rounded" size="small" color="dark" id="search-btn">
          <i class="fas fa-search"></i>
        </ess-float-button>

        <ess-tooltip target="search-btn"> Search in application </ess-tooltip>

        <ess-float-button type="cleaned" shape="rounded" size="small" color="dark" id="not-btn">
          <i class="fas fa-bell"></i>
        </ess-float-button>

        <ess-tooltip target="not-btn"> View your notifications </ess-tooltip>

        <ess-menu target="not-btn">
          <ess-list>
            <ess-list-item> New order has been received </ess-list-item>
            <ess-list-item> New order has been received </ess-list-item>
            <ess-list-item> New order has been received </ess-list-item>
            <ess-list-item> New order has been received </ess-list-item>
            <ess-list-item> New order has been received </ess-list-item>
          </ess-list>
        </ess-menu>

        <ess-float-button type="cleaned" shape="rounded" size="small" color="dark" id="chart-btn">
          <i class="fas fa-chart-bar"></i>
        </ess-float-button>

        <ess-tooltip target="chart-btn"> View your charts </ess-tooltip>

        <ess-float-button type="cleaned" shape="rounded" size="small" color="dark" id="shop-btn">
          <i class="fas fa-shopping-bag"></i>
        </ess-float-button>

        <ess-tooltip target="shop-btn"> View your products </ess-tooltip>

        <ess-float-button type="cleaned" shape="rounded" size="small" color="dark" id="app2-btn">
          <i class="fas fa-th-large"></i>
        </ess-float-button>

        <ess-tooltip target="app2-btn"> View your apps </ess-tooltip>

        <ess-button type="cleaned" size="small" color="dark">
          Hi, <strong> Bruno </strong>
        </ess-button>
      </div>

    </ess-toolbar>

  </div>
</template>

<style>
  @import './css/main.css';
</style>

<script lang="ts">

/* eslint-disable */
/* eslint-disable no-useless-constructor */

import { Component, Vue } from 'vue-property-decorator';

import EssTab from '@/components/EssTab.vue';
import EssTabs from '@/components/EssTabs.vue';
import EssMenu from '@/components/EssMenu.vue';
import EssList from '@/components/EssList.vue';
import EssListItem from '@/components/EssListItem.vue';
import EssAvatar from '@/components/EssAvatar.vue';
import EssTextInput from '@/components/EssTextInput.vue';
import EssButton from '@/components/EssButton.vue';
import EssFloatButton from '@/components/EssFloatButton.vue';
import EssSeparator from '@/components/EssSeparator.vue';
import EssTooltip from '@/components/EssTooltip.vue';
import EssToolbar from '@/components/EssToolbar.vue';

@Component({
  components: {
    EssTab,
    EssTabs,
    EssMenu,
    EssList,
    EssListItem,
    EssAvatar,
    EssTextInput,
    EssButton,
    EssFloatButton,
    EssSeparator,
    EssTooltip,
    EssToolbar,
  },
})
export default class App extends Vue {
  private tab: string;

  constructor() {
    super();

    this.tab = 'pages';
  }
}
</script>
