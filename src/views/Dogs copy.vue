
<template>
  <div class="col-8 offset-2">
    <h1>Dogs for Adoption</h1>
    <b-table striped hover :items="dogs">
      <template slot="name" slot-scope="data">
        <router-link to="`/pets/${data.index}`">{{ data.value }}</router-link>
      </template>
    </b-table>
  </div>
</template>
<script>
import { mapState } from "vuex";
export default {
  compute: {
    ...mapState(["dogs"]),
  },
};
</script>


<template>
  <div class="col-8 offset-2">
    <h1>Dogs for Adoption</h1>
    <b-table :fields="fields" :items="dogs">
      <template #cell(name)="data">
        <router-link :to="`pets/${data.index}`">{{ data.value }}</router-link>
      </template>
    </b-table>
  </div>
</template>
<script>
import dogs from "@/data/dogs";
export default {
  data() {
    return {
      dogs,
    };
  },
};
</script>

