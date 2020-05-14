<template>
<div>
    <h1>Speiseplan HfG Gmünd</h1>
    Wähle einen Wochentag:
    <select name="Wochentag" id="selectBox">
      <option v-for="day in days" :key="day">{{day}}</option>
    </select>
</div>
</template>

<script>
export default {
  name: 'Dropdown',
  props: {
    days: Array
  }
}
</script>

<style scoped>

</style>