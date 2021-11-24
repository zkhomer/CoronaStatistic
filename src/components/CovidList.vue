<template>
  <div>
    <ul class="countryList">
      <li>
        <div class="countryList__list-item heading">
          <div class="countryList__list-item-number">№</div>
          <div class="countryList__list-item-country">Country</div>
          <div class="countryList__list-item-total">Total Confirmed</div>
        </div>
      </li>
      <CovidListItem
          v-for="(country,i) of findHandler "
          v-bind:country="country"
          v-bind:index="i"
          v-bind:key="country.id"
      />
    </ul>
  </div>
</template>

<script>
import CovidListItem from './CovidListItem'

export default {
  data() {
    return {
      test: [...this.summary],
    }
  },
  props: ['summary', 'find'],
  methods: {
    log() {
      // console.log(this.findHandler)
    }
  },
  computed: {
    findHandler() {
      return this.summary.filter((el) => {
        return el.Country.toUpperCase().indexOf((this.find).toUpperCase()) !== -1
      })
    },
  },
  components: {CovidListItem}
}
</script>

<style lang="scss">
li {
  list-style: none;
}

.countryList {
  max-width: 900px;
  margin: 0 auto;

  &__list {
    list-style: none;
    padding-left: 5px;

    &-item {
      display: flex;
      margin: 10px;
      border-radius: 20px;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.25);
      justify-content: space-between;

      &-number {
        flex: 1 0;
        padding: 20px;
        border-right: 1px solid #B2B2B2;
      }

      &-country {
        flex: 5 0;
        padding: 20px;
        border-right: 1px solid #B2B2B2;

      }

      &-total {
        flex: 3 0;
        max-width: 210px;
        padding: 20px;

      }
    }
  }
}

.heading {
  background-color: #2196F3;

  & div {
    border-right: 1px solid white;
  }
}

</style>