<template>
  <div>
    <button
      :style="style"
      @click="clickButton">
      {{label}}<br/>
      code = {{code}}<br/>
      selected = {{selectedCode}}
    </button>
    <div class="content">
      <Component
        v-if="label"
        :is="component"
        :href="url"
        >
        <slot></slot>
      </Component>
    </div>
  </div>
</template>

<style scoped>
.content {
  margin-left: 40px;
}
</style>

<script>
export default {
  name: 'TheButton',
  props: ['label', 'url', 'code', 'selectedCode'],
  computed: {
    component () {
      return this.url ? 'a': 'div'
    },
    isSelected () {
      return this.code === this.selectedCode
    },
    style () {
      return {
        backgroundColor: this.isSelected ? 'green' : ''
      }
    }
  },
  methods: {
    clickButton () {
      this.$emit('myclick', this.code)
    }
  }
}
</script>