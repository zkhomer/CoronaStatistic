<template>
  <li>
    <div class="countryList__list-item">
      <div class="countryList__list-item-number">{{ index + 1}}</div>
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
    testLog(){
      console.log(this.country)
    }
  }
}
</script>
<!--////////////////////////////////////////////////////////-->
<style scoped lang="scss">
li{

}
</style>