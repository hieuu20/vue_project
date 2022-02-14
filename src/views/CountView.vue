<script lang="ts">
import { defineComponent, nextTick } from "vue";

export default defineComponent({
  data() {
    return {
      count: 1,
    };
  },
  methods: {
    increment() {
      this.count++;
    },
  },

  mounted() {
    this.count = 2;
  },

  computed: {
    log() {
        console.log('log',this.count);
    } 
  },
});
</script>

<template>
  <button class="buttonCount" @click="increment">{{ count }}</button>
</template>

<style scoped>
.buttonCount {
  height: 32px;
  width: 70px;
}
</style>
