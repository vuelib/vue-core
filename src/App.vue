<template>
  <div id="app">
    <ess-toolbar>
      <ess-button type="highlighted" size="small">
        Pages
      </ess-button>

      <ess-button type="highlighted" size="small">
        Features
      </ess-button>

      <ess-button type="highlighted" size="small" id="apps-btn">
        Apps
      </ess-button>

      <ess-menu target="apps-btn">
        <ess-list>
          <ess-list-item> Reporting </ess-list-item>
          <ess-list-item> Social Presence </ess-list-item>
          <ess-list-item> Sales & marketing </ess-list-item>
          <ess-list-item> Campaigns </ess-list-item>
          <ess-list-item> Deployment Center </ess-list-item>
        </ess-list>
      </ess-menu>

      <ess-float-button type="cleaned" shape="rounded" size="small" color="dark">
        <i class="fas fa-search"></i>
      </ess-float-button>
      <ess-float-button type="cleaned" shape="rounded" size="small" color="dark">
        <i class="fas fa-bell"></i>
      </ess-float-button>
      <ess-float-button type="cleaned" shape="rounded" size="small" color="dark">
        <i class="fas fa-chart-bar"></i>
      </ess-float-button>
      <ess-float-button type="cleaned" shape="rounded" size="small" color="dark">
        <i class="fas fa-shopping-bag"></i>
      </ess-float-button>
      <ess-float-button type="cleaned" shape="rounded" size="small" color="dark">
        <i class="fas fa-th-large"></i>
      </ess-float-button>

      <ess-button type="cleaned" size="small" color="dark">
        Hi, <strong> Bruno </strong>
        <ess-avatar style="margin-left: 8px" size="small" shape="rounded" src="https://keenthemes.com/metronic/themes/metronic/theme/default/demo1/dist/assets/media/users/100_1.jpg" />
      </ess-button>
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
  private imgsBaseUrl: string;

  constructor() {
    super();

    this.imgsBaseUrl = 'https://keenthemes.com/metronic/themes/metronic/theme/default/demo1/dist/assets/media/users';
  }
}
</script>
