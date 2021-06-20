<template>
  <div class="tab-control">
    <div v-for="(item, index) in titles"
      class="tab-bar-control"
         :class="{active: index === currentIndex}"
         @click="itemClick(index)">
      <span>{{item}}</span>

    </div>
  </div>
</template>

<script>
export default {
  name: "tabControl",
  props:{
    titles:{
      type: Array,
      default(){
        return []
      }
    }
  },
  data(){
    return {
      currentIndex: 0
    }
  },
  methods: {
    itemClick(index) {
      this.currentIndex = index;
      this.$emit('tabClick', index)
    }
  }
}
</script>

<style scoped>

</style>
