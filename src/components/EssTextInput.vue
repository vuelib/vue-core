<template>
  <input
    class="ess"
    type="text"
    :id="id"
    :name="name"
    :placeholder="placeholder"
    :class="[type, shape, theme, color]"
  />
</template>

<script lang="ts">
/* eslint-disable lines-between-class-members */
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';

@Component({
  name: 'EssTextInput',
})
export default class EssTextInput extends Vue {
  @Prop()
  id!: string;

  @Prop()
  name!: string;

  @Prop()
  placeholder!: string;

  @Prop({ default: 'outlined' })
  type!: string;

  @Prop({ default: 'rounded' })
  shape!: string;

  @Prop({ default: 'medium' })
  size!: string;

  @Prop({ default: 'light' })
  theme!: string;

  @Prop()
  color!: string;
}
</script>
