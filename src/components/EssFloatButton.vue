<template>
  <button class="ess float" :class="[type, shape, size, theme, color]">
    <slot></slot>
  </button>
</template>

<script lang="ts">
/* eslint-disable lines-between-class-members */
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';

@Component({
  name: 'EssFloatButton',
})
export default class EssFloatButton extends Vue {
  @Prop({ default: 'filled' })
  type!: string;

  @Prop({ default: 'circle' })
  shape!: string;

  @Prop({ default: 'medium' })
  size!: string;

  // @Prop({ default: 'light' })
  // theme!: string;

  @Prop({ default: 'primary' })
  color!: string;
}
</script>
