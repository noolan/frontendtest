<template>
  <div id="app">
    <main>
      <section>
        <chess-board @change="handleChange"></chess-board>
      </section>
      <side-bar :selected="selected" :history="history"></side-bar>
    </main>
  </div>
</template>

<script>
import ChessBoard from './components/ChessBoard.vue'
import SideBar from './components/SideBar.vue'

export default {
  name: 'app',
  components: {
    ChessBoard,
    SideBar
  },
  data () {
    return {
      selections: []
    }
  },
  computed: {
    selected () {
      if (this.selections.length) {
        return this.selections[0]
      } else {
        return '-'
      }
    },
    history () {
      if (this.selections.length > 1) {
        return this.selections.slice(1)
      } else {
        return []
      }
    }
  },
  methods: {
    handleChange (square) {
      if (square !== this.selected) {
        this.selections.splice(0, 0, square)
      }
    }
  }
}
</script>
