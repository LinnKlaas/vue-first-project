<template>
  <div>
    <Dropdown :days="dropdownData"></Dropdown>
    <List :listEssen="loadedData.data"></List>
    <Mahlzeit :mahlzeiten="mahlzeitData.data"></Mahlzeit>
  </div>
</template>

<script>
import Dropdown from "../components/Dropdown.vue"
import List from "../components/List.vue"
import Mahlzeit from "../components/Mahlzeit.vue"
import axios from 'axios'

export default {
  name: 'Plan',
  components: {
    Dropdown, List, Mahlzeit
  },
  props: {
    msg: String
  },
  data:function() {
    return {
      loadedData: "no data loaded",
      dropdownData: ["Montag", "Dienstag", "Mittwoch", "Donnerstag", "Freitag"],
      mahlzeitData: "hier stehen mahlzeiten",
    }
  },
  mounted() {
    //axios.get("http://localhost:3000/mensa/Di")
    axios.get("https://gist.githubusercontent.com/fg-uulm/666847dd7f11607fc2b6234c6d84d188/raw/2ca994ada633143903b10b2bf7ada3fd039cae35/mensa.json")
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
