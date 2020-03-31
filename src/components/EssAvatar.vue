<template>
  <img :src="src" class="ess avatar" :class="[type, shape, size, theme, color]">
</template>

<script lang="ts">
/* eslint-disable lines-between-class-members */
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';

@Component({
  name: 'EssAvatar',
})
export default class EssAvatar extends Vue {
  @Prop({ default: 'filled' })
  type!: string;

  @Prop({ default: 'circle' })
  shape!: string;

  @Prop({ default: 'medium' })
  size!: string;

  @Prop({ default: 'light' })
  theme!: string;

  @Prop()
  color!: string;

  @Prop()
  src!: string;
}
</script>
