<script>
import singlecard from "./card.vue";
export default {
  components: {
    singlecard,
  },
  name: "cards",

  data() {
    return {
      array: [
        {
          prova: 1,
        },
        {
          prova: 1,
        },
        {
          prova: 1,
        },
      ],
      ricerca: "",
      repositories: "",
    };
  },
  methods: {
    getElements() {
      console.log(this.ricerca);
      console.log(this.repositories);
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="row">
      <div class="col-12 text-center">
        <form @submit.prevent="getElements">
          <input type="text" v-model="ricerca" />
          <select name="" id="" v-model="repositories">
            <option value="repositories" selected>repositories</option>
            <option value=">user">user</option>
          </select>
          <input type="submit" value="cerca" />
        </form>
      </div>
      <div class="col-12">
        <div v-for="number in array">
          <singlecard :item="number" />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
@import "./../style/general.scss";
</style>
