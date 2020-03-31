<template>
  <div class="ess toolbar" :class="[isSeparator]">
    <slot></slot>
  </div>
</template>

<script lang="ts">

/* eslint-disable lines-between-class-members */
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';

@Component({
  name: 'EssToolbar',
})
export default class EssToolbar extends Vue {
  @Prop({ default: false })
  separator!: boolean;

  get isSeparator(): string | null {
    if (this.separator) {
      return 'toolbar-separator';
    }

    return null;
  }
}
</script>
