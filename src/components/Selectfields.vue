<template>
  <Selectfields>
  <div>
    <h1>Vue Select Comparison</h1>
    <div class="select-container">
      <fieldset>
        <h3>Vue Multiselect</h3>
        <label><strong>Users:</strong></label>
        <multiselect
            v-model="multiSelectUser"
            :options="options"
            track-by="id"
            label="name"
            :internal-search="false"
            :placeholder="`Type to search`"
            @search-change="search"
            :loading="loading"
        >
        </multiselect>
      </fieldset>
      <fieldset>
        <h3>Vue Select</h3>
        <label><strong>Users:</strong></label>
        <v-select :options="options"
                  label="name"
                  :filterable="false"
                  @search="search"
                  v-model="vSelectUser"
        ></v-select>
      </fieldset>
    </div>
  </div>
  </Selectfields>
</template>

<script>
export default {
  name: "Selectfields",
  data() {
    return {
      options: [],
      loading: false,
      multiSelectUser: null,
      vSelectUser: null
    };
  },
  mounted: function() {
    this.search();
  },
  methods: {
    search: function(queryString) {
      this.loading = true;
      fetch("https://jsonplaceholder.typicode.com/users")
          .then(response => response.json())
          .then(json => {
            this.loading = false;
            if (queryString) {
              this.options = json.filter(user =>
                  user.name.toLowerCase().includes(queryString.toLowerCase())
              );
            } else {
              this.options = json;
            }
          })
          .catch(e => {
            console.error(e);
            this.loading = false;
          });
    }
  }
};
</script>

<style scoped>
.select-container {
  display: flex;
  width: 100%;
}
fieldset {
  flex: 1 1 0;
}
</style>