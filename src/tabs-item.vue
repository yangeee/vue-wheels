<template>
  <div class="tabs-item" @click="onClick" :class="classes" :data-name="name">
    <slot></slot>
  </div>
</template>


<script>
export default {
  name: 'NinjaTabsItem',
  inject: ['eventBus'],
  data() {
    return {
      active: 'sports',
      item_active: true
    }
  },
  props: {
    name: {
      type: String || Number,
      required: true
    },
    disabled: {
      type: Boolean,
      default: false
    }
  },
  created() {
    this.eventBus &&
      this.eventBus.$on('update:selected', (name) => {
        return this.item_active = name === this.name
      })

  },
  methods: {
    onClick() {
      if (this.disabled) { return }
      this.eventBus && this.eventBus.$emit('update:selected', this.name, this)
      this.$emit('click', this)
    }
  },
  computed: {
    classes() {
      return {
        item_active: this.item_active,
        disabled: this.disabled
      }
    }
  }
}
</script>


<style scoped lang="scss">
$active-color: #409eff;
$disabled-text-color: #aaa;
.tabs-item {
  flex-shrink: 0;
  text-align: center;
  padding: 0 1em;
  height: 100%;
  cursor: pointer;
  display: flex;
  align-items: center;
  &.item_active {
    color: $active-color;
    .n-icon {
      fill: #409eff;
    }
  }
  &.disabled {
    color: $disabled-text-color;
  }
}
</style>
