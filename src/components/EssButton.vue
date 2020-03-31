<template>
  <button class="ess" :class="[type, shape, size, color]">
    <slot></slot>
  </button>
</template>

<script lang="ts">
/* eslint-disable lines-between-class-members */
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';

@Component({
  name: 'EssList',
})
export default class EssList extends Vue {
  @Prop({ default: 'filled' })
  type!: string;

  @Prop({ default: 'rounded' })
  shape!: string;

  @Prop({ default: 'medium' })
  size!: string;

  @Prop({ default: 'primary' })
  color!: string;
}
</script>
