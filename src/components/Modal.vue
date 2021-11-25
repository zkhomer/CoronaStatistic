<template>
  <div class="modal">
    <ul class="modal__wrapper">
      <h2 class="modal__title">{{ countryDetailsObj.Country }}</h2>
      <li class="total">
        <div class="total-confirmed-static">
          New Confirmed
        </div>
        <div class="total-confirmed">{{ countryDetailsObj.NewConfirmed }}</div>
      </li>
      <li class="total">
        <div class="total-deaths-static">
          Total Deaths
        </div>
        <div class="total-deaths">
          {{ countryDetailsObj.TotalDeaths }}
        </div>
      </li>
      <li class="total">
        <div class="total-recovered-static">
          Total Recovered
        </div>
        <div class="total-recovered">
          {{ countryDetailsObj.TotalRecovered }}
        </div>
      </li>
      <button
          class="modal__btn"
          @click="$emit('modalShow',modalShow)"
      >
        OK
      </button>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      modalShow: false,
    }
  },
  props: ['countryDetailsObj'],

  methods: {},
}
</script>

<style scoped lang="scss">
* {
  box-sizing: border-box;
}

.modal {
  position: fixed;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  transition: 0.3s;
  background-color: rgba(0, 0, 0, 0.5);

  &__title {
    display: flex;
    justify-content: center;
    font-size: 48px;
    padding: 20px;
  }

  &__wrapper {
    margin: 0 auto;
    background-color: white;
    max-width: 600px;
    height: 450px;
    border-radius: 20px;
    padding:0 20px;
  }

  &__btn {
    display: block;
    font-size: 24px;
    color: white;
    margin: 0 auto;
    background-color: #2196F3;
    border-radius: 20px;
    width: 170px;
    height: 50px;
    border: none;
    cursor: pointer;
    transition: background-color 0.4s;

    &:hover {
      background-color: #2152f3;
    }

  }

  .total {
    display: flex;
    justify-content: space-between;
    max-width: 400px;
    margin: 0 auto;

    & div {
      font-size: 24px;
      color: rgba(102, 102, 102, 1);
      margin-bottom: 50px;
    }
  }
}

</style>