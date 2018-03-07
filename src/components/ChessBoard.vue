<template>
  <figure>
    <template v-for="rank in ranks">
      <div v-for="file in files" :key="file+rank" tabindex="0" @focus="handleClick(file, rank)"></div>
    </template>
  </figure>
</template>
<script>
export default {
  name: 'chess-board',
  data () {
    return {
      files: ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'],
      ranks: ['8', '7', '6', '5', '4', '3', '2', '1']
    }
  },
  methods: {
    handleClick (file, rank) {
      // console.log(file + rank)
      this.$emit('change', file + rank)
    }
  }
}
</script>
