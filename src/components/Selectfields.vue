<template>
  <div>
    <h1>Vue Select Comparison</h1>
    <div class="select-container">
      <fieldset>
        <h3>Vue Multiselect</h3>
        <label><strong>Users:</strong></label>
        <multiselect
            v-model="value"
            :options="options"
            :searchable="false"
            :close-on-select="false"
            :show-labels="false" placeholder="Pick a value">
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
</template>

<script>
import vSelect from 'vue-select';
import Multiselect from 'vue-multiselect';
export default {
  name: "Selectfields",
  components: { vSelect, Multiselect},
  data() {
    return {
      // options: ['Select option', 'options', 'selected', 'mulitple', 'label', 'searchable', 'clearOnSelect', 'hideSelected', 'maxHeight', 'allowEmpty', 'showLabels', 'onChange', 'touched'],
      options: [],
      loading: false,
      multiSelectUser: null,
      vSelectUser: null,
      value: ''

    };
  },
  created(){
    console.log(this);
  },
  mounted () {
    console.log(this.value, "VALUE");
    this.options = ['Select option', 'options', 'selected', 'mulitple', 'label', 'searchable', 'clearOnSelect', 'hideSelected', 'maxHeight', 'allowEmpty', 'showLabels', 'onChange', 'touched']
    // this.search();
  },
  methods: {
    search(queryString) {
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