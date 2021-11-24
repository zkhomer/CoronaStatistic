<template>
  <div class="header">
    <div class="header__wrapper">
      <div class="header__wrapper__img">
        <img v-bind:src="imgUrl" alt="Covid statistic logo">
      </div>
      <div class="header__wrapper__search">
        <input
            v-on:keyup="$emit('findHandler', inputValue)"
            v-model="inputValue"
            type="text"
            placeholder="Search..."
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      imgUrl: "https://osr.statisticsauthority.gov.uk/wp-content/uploads/2020/04/Covid-19.png",
      inputValue: ''
    }
  },
  methods: {
    getName() {
      console.log(this.inputValue)
    }
  }
}

</script>

<style scoped lang="scss">
.header {
  max-width: 700px;
  display: block;
  margin: 0 auto;

  &__wrapper {
    display: flex;
    justify-content: space-between;
      @media (max-width: 530px) {
        flex-direction: column;
        align-items: center;
      }
    &__img img {
      width: 300px;
    }

    &__search {
      display: flex;
      align-items: center;

      & input {
        border:none;
        height: 30px;
        width: 200px;
        padding: 5px;
        border-radius: 20px;
        box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.25);
        outline: none;
      }
    }
  }
}
</style>