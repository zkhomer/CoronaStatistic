<template>
  <li>
    <div class="countryList__list-item">
      <div class="countryList__list-item-number">{{ index + 1 }}</div>
      <div class="countryList__list-item-country">{{ country.Country }}</div>
      <div class="countryList__list-item-total">{{ country.TotalConfirmed }}</div>
    </div>
  </li>
</template>
<script>
export default {

  props: {
    country: {
      type: Object,
      required: true
    },
    index: Number
  },
  methods: {
    testLog() {
      console.log(this.country)
    }
  }
}
</script>
<!--////////////////////////////////////////////////////////-->
<style scoped lang="scss">
.countryList__list-item{
  transition: background-color 0.3s;
  cursor: pointer;
  &:hover{
    background-color: #2196F3;
  }
}
</style>