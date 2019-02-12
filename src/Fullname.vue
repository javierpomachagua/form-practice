<template>
    <div>
      <input type="text" name="fullname" id="fullname" @input="input()" v-model="fullname">
    </div>
</template>

<script>
export default {
  name: 'Fullname',
  props: ['value'],
  data() {
    return {
      fullname: ''
    }
  },
  methods: {
    input() {
      console.log('cambió', this.fullname);
      this.$emit('input', this.fullname);
    }
  }
}
</script>

<style scoped>
</style>