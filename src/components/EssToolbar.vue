<template>
  <div class="ess toolbar shadow-dp-1 light">
    <slot></slot>
  </div>
</template>

<style>
  .ess.toolbar {
    width: 100%;
    height: 60px;
    padding: 16px;
    /* background: red; */
    position: relative;
    display: inline-flex;
    align-items: center;
  }
</style>

<script lang="ts">

/* eslint-disable lines-between-class-members */
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';

@Component({
  name: 'EssToolbar',
})
export default class EssToolbar extends Vue {
  @Prop({ default: 'light' })
  theme!: string;
}
</script>
