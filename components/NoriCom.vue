<template lang="html">
  <div class="sample">
    Hello, I'm {{ name }}
    reverse: {{ reverseName }}
    num: {{ num }}
    <button 
      type="button" 
      @click="plus">+</button>

    <div 
      :class="['hide', seven]">
      seven times click disappear
    </div>
    <h1>{{ title }}</h1>
    <slot />
  </div>
</template>
​
<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Defalut Title'
    }
  },
  data() {
    return {
      name: 'hiroki',
      num: 0
    }
  },
  computed: {
    reverseName() {
      return this.name
        .split('')
        .reverse()
        .join('')
    },
    seven() {
      return this.num === 7 ? 'seven' : null
    }
  },
  methods: {
    plus() {
      this.num++
    }
  }
}
</script>
​
<style lang="scss" scoped>
.hide {
  display: none;
  &.seven {
    display: block;
  }
}
</style>
