<template>
  <div id="app">
    <b-navbar toggleable="lg" type="dark" variant="info">
    <b-navbar-brand href="#">History</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="#">Link</b-nav-item>
        <b-nav-item href="#" disabled>Disabled</b-nav-item>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
          <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
        </b-nav-form>

        <b-nav-item-dropdown text="Lang" right>
          <b-dropdown-item href="#">EN</b-dropdown-item>
          <b-dropdown-item href="#">ES</b-dropdown-item>
          <b-dropdown-item href="#">RU</b-dropdown-item>
          <b-dropdown-item href="#">FA</b-dropdown-item>
        </b-nav-item-dropdown>

        <b-nav-item-dropdown right>
          <!-- Using 'button-content' slot -->
          <template v-slot:button-content>
            <em>User</em>
          </template>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
    <div class="overflow-auto">
    <b-pagination
      v-model="currentPage"
      :total-rows="rows"
      :per-page="perPage"
      aria-controls="my-table"
    ></b-pagination>

    <p class="mt-3">Current Page: {{ currentPage }}</p>

    <b-table
      id="my-table"
      :items="items"
      :per-page="perPage"
      :current-page="currentPage"
      small
    ></b-table>
  </div>
    
  </div>
</template>

<script>

 export default {
    data() {
      return {
        perPage: 3,
        currentPage: 1,
        items: [
          {  diagnosis_ID: 1, patient_ID: '1234', Weight_lb: '120lb', Blood_pressure: '112mm Hg',Temperature: '90F',Date: '4/2/20', time: '8:30 ', Doctor_Notes: ' This person has issues'},
          { diagnosis_ID: 1, patient_ID: '1234', Weight_lb: '120lb', Blood_pressure: '112mm Hg',Temperature: '90F',Date: '4/2/20', time: '8:30 ', Doctor_Notes: ' This person has issues'},
          { diagnosis_ID: 1, patient_ID: '1234', Weight_lb: '120lb', Blood_pressure: '112mm Hg',Temperature: '90F',Date: '4/2/20', time: '8:30 ', Doctor_Notes: ' This person has issues'},
          { diagnosis_ID: 1, patient_ID: '1234', Weight_lb: '120lb', Blood_pressure: '112mm Hg',Temperature: '90F',Date: '4/2/20', time: '8:30 ', Doctor_Notes: ' This person has issues'}
        ]
      }
    },
    computed: {
      rows() {
        return this.items.length
      }
    }
  }

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
