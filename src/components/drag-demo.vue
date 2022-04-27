<template>
  <div>
    <draggable v-model="myArray" group="people" @start="drag=true" @end="drag=false">
      <div v-for="element in myArray" :key="element.value" class="a">
        <span v-if="element.type==='text'">{{ element.value }}</span>
        <button v-if="element.type==='link'">{{ element.value }}</button>
      </div>
    </draggable>
  </div>
</template>

<script>
import draggable from 'vuedraggable'
export default {
  components: { draggable },
  data() {
    return {
      myArray: [
        {
          type: 'text',
          value: 'demo1',
        },
        {
          type: 'link',
          value: 'demo2'
        }
      ]
    }
  }
}
</script>

<style>
.a {
  display: inline-block;
}
</style>