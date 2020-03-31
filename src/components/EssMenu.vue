<template>
  <div class="ess menu animated faster" :class="[theme, shadow, animation]" v-show="menuVisible">
    <slot></slot>
  </div>
</template>

<script lang="ts">

/* eslint-disable default-case */
/* eslint-disable no-underscore-dangle */
/* eslint-disable lines-between-class-members */

import Vue from 'vue';
import { createPopper } from '@popperjs/core';
import { Component, Prop } from 'vue-property-decorator';

@Component({
  name: 'EssMenu',
})
export default class EssMenu extends Vue {
  private fadeIn: boolean;
  private menuVisible: boolean;
  private targetEl!: HTMLElement;

  constructor() {
    super();

    this.fadeIn = false;
    this.menuVisible = false;
  }

  /**
   *
   */
  @Prop({ required: true })
  target!: string;

  /**
   * This possibles themes
   *
   * light, dark
   */
  @Prop({ default: 'light' })
  theme!: string;

  /**
   * This possibles triggers
   *
   * click, hover, context-menu
   */
  @Prop({ default: 'click' })
  trigger!: string; // click, hover, context-menu

  /**
   * This possibles placements
   *
   * top-start, top, top-end
   * right-start, right, right-end,
   * bottom-start, bottom, bottom-end,
   * left-start, left, left-end,
   */
  @Prop({ default: 'bottom' })
  placement!: string;

  /**
   * This possibles offsets
   *
   * [top, left]
   */
  @Prop({ default: () => [0, 0] })
  offset!: [number, number];

  /**
   * This possibles shadows
   *
   * shadow-dp-1,
   * shadow-dp-2.
   * shadow-dp-3,
   * shadow-dp-4,
   * shadow-dp-5
   */
  @Prop({ default: 'shadow-dp-1' })
  shadow!: string;

  get popperConf(): {} {
    return {
      placement: this.placement,
      modifiers: [
        { name: 'offset', options: { offset: this.offset } },
      ],
    };
  }

  get animation(): string {
    if (this.fadeIn) {
      return 'fadeIn';
    }

    return 'fadeOut';
  }

  private created(): void {
    this.$nextTick(() => {
      this.targetEl = document.getElementById(this.target) as HTMLElement;

      this._registryShowListener();
      this._registryHideListener();
    });
  }

  private beforeDestroy(): void {
    this.$nextTick(() => {
      this._removeShowListener();
      this._removeHideListener();
    });
  }

  private _formatTrigger(): string {
    if (this.trigger === 'hover') {
      return 'mouseover';
    }

    if (this.trigger === 'context-menu') {
      return 'contextmenu';
    }

    return this.trigger;
  }

  private _registryShowListener(): void {
    this.targetEl.addEventListener(this._formatTrigger(), (e) => this.show(e));
  }

  private _registryHideListener(): void {
    document.addEventListener('click', (e) => this.hide(e));
  }

  private _removeShowListener(): void {
    this.targetEl.removeEventListener(this._formatTrigger(), (e) => this.show(e));
  }

  private _removeHideListener(): void {
    document.removeEventListener('click', (e) => this.hide(e));
  }

  public show(e: Event): void {
    // e.preventDefault();
    this.fadeIn = true;
    this.menuVisible = true;
    createPopper(this.targetEl, this.$el as HTMLElement, this.popperConf);
  }

  public hide(e: Event): void {
    if (this.menuVisible && e.target !== this.targetEl && e.target !== this.$el) {
      this.fadeIn = false;
      setTimeout(() => { this.menuVisible = false; }, 500);
    }
  }
}
</script>
