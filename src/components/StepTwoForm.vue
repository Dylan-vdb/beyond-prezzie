<template>
  <foreignObject y="445" x="283.5" height="59" width="63">
    <div
      style="
        position: relative;
        border: 1px dotted #0000ff00;
        width: 200px;
        height: 180px;
        transform-origin: 0 0;
        transform: scale(0.28);
        overflow: hidden;
        z-index: 1000;
      "
    >
      <p>
        I am a vue form component embedded inside this SVG within it's inherently scalable/zoomable
        world.
      </p>
      <p>I could therefore include a video or a map or whatever.</p>

      <base-input-text
        v-model="howMuchItRocks"
        label="How much does this rock!!!?"
      ></base-input-text>
      <base-button class="submit-button" @click="$emit('save-form', howMuchItRocks)"
        >Use form inputs in app</base-button
      >
    </div>
  </foreignObject>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import BaseInputText from '@/components/BaseComponents/BaseInputText.vue'
import BaseButton from '@/components/BaseComponents/BaseButton.vue'

export default defineComponent({
  components: { BaseInputText, BaseButton },
  setup() {
    const howMuchItRocks = ref('A LOT!!')
    return {
      howMuchItRocks
    }
  },

  watch: {
    howMuchItRocks(value) {
      console.log('howMuchItRocks -> value', value)
    }
  }
})
</script>

<style scoped>
p {
  font-size: 0.5rem;
}

.submit-button {
  margin-top: 10px;
}
</style>
