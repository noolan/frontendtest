<template>
  <aside>
    <h2>Current Square</h2>
    <p>{{ selected }}</p>

    <h2>Selection History</h2>
    <ol>
      <li v-for="(square, index) of history" :key="index">{{ square }}</li>
    </ol>
  </aside>
</template>
<script>
export default {
  name: 'side-bar',
  props: {
    selected: {
      required: true,
      type: String
    },
    history: {
      required: true,
      type: Array
    }
  }
}
</script>
