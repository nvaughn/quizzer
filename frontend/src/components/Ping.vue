<template>
  <div class="container">
    <h1 class="text-6xl font-bold underline mb-6">{{ finalRes }}!</h1>
    <button
      type="button"
      class="px-6 py-3.5 text-base rounded-lg font-medium text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 rounded-lg text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
    >
      Extra large
    </button>
  </div>
</template>

<script>
export default {
  name: 'PingMe',
  data() {
    return {
      finalRes: '',
    }
  },
  methods: {
    async getMessage() {
      const path = 'http://localhost:5000/ping'
      const res = await fetch(path)
      const data = await res.json()
      this.finalRes = data // Update the finalRes data property
      console.log(data)
    },
  },
  created() {
    this.getMessage()
  },
}
</script>
