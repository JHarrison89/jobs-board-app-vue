<template>
  <b-card title="Card title" sub-title="Card subtitle">
    <b-card-text>
      Some quick example text to build on the <em>card title</em> and make up
      the bulk of the card's content.
    </b-card-text>

    <b-card-text>A second paragraph of text in the card.</b-card-text>

    <a href="#" class="card-link">Card link</a>
    <b-link href="#" class="card-link">Another link</b-link>
  </b-card>
</template>

<!-- <script>
import axios from "axios";
export default {
  data() {
    return {
      meals: [],
    };
  },
  mounted() {
    axios
      .get("https://www.themealdb.com/api/json/v1/1/categories.php")
      .then(response => {
        this.meals = response.data.categories;
      })
      .catch(err => {
        console.log(err);
      });
  }
};
</script> -->
