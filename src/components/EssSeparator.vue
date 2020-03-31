<template>
  <div class="ess separator" :class="[theme]"></div>
</template>

<script lang="ts">
/* eslint-disable lines-between-class-members */
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';
@Component({
  name: 'EssSeparator',
})
export default class EssSeparator extends Vue {
  @Prop({ default: 'light' })
  theme!: string;

  @Prop({ default: '1rem' })
  vspace!: string;

  @Prop({ default: '.05rem' })
  hspace!: string;

  @Prop({ required: false, default: false, type: Boolean })
  contextMenu!: boolean;

  get style() {
    return {
      margin: `${this.vspace} ${this.hspace}`,
    };
  }
}
</script>
