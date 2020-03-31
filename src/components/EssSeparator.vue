<template>
  <div class="ess separator" :class="[theme, isVertical]" :style="[style]"></div>
</template>

<script lang="ts">
/* eslint-disable lines-between-class-members */
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';

@Component({
  name: 'EssSeparator',
})
export default class EssSeparator extends Vue {
  @Prop({ default: 16 })
  vspace!: string;

  @Prop({ default: 0 })
  hspace!: string;

  @Prop({ default: false })
  vertical!: boolean;

  @Prop({ default: 'light' })
  theme!: string;

  get style() {
    return {
      margin: `${this.vspace}px ${this.hspace}px`,
    };
  }

  get isVertical(): string | null {
    if (this.vertical) {
      return 'vertical';
    }

    return null;
  }
}
</script>
