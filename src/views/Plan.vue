<template>
  <div>
    <Dropdown :days="dropdownData"></Dropdown>
    <List :listEssen="loadedData.data"></List>
  </div>

</template>

<script>
import Dropdown from "../components/Dropdown.vue"
import List from "../components/List.vue"
import axios from 'axios'

export default {
  name: 'Plan',
  components: {
    Dropdown, List
  },
  props: {
    msg: String
  },
  data:function() {
    return {
      loadedData: "no data loaded",
      dropdownData: ["Montag", "Dienstag", "Mittwoch", "Donnerstag", "Freitag"],
    }
  },
  mounted() {
    axios.get("http://localhost:3000/mensa/Di")
      .then(response => {
        this.loadedData = response
      })
      .catch(err => {
        console.log(err);
      })
  }
}
</script>

<style scoped>

</style>
