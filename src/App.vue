<template>
  <div id="app">
    <Header
        @findHandler="findHandler"
    />
    <CovidList
        v-bind:find="find"
        v-bind:summary="summary"
    />
    <Modal/>
  </div>
</template>

<script>
import Header from "@/components/Header.vue"
import CovidList from "@/components/CovidList.vue"
import Modal from "@/components/Modal.vue"

export default {
  name: 'App',
  components: {
    Header, CovidList, Modal
  },
  data() {
    return {
      summary: [],
      find: ""
    }
  },
  methods: {
    findHandler(inputValue) {
      this.find = inputValue
    }
  },

  async mounted() {
    try {
      const summary = await fetch('https://api.covid19api.com/summary')
      const res = await summary.json()
      this.summary.push(...res.Countries)
    } catch (err) {
      console.log(err)
    }
  },
}
</script>

<style>

</style>
