<template>
<body>
    <h1>Speiseplan HfG Gmünd</h1>
    Wähle einen Wochentag:
    <select name="Wochentag">
      <option>Montag</option>
      <option>Dienstag</option>
      <option>Mittwoch</option>
      <option>Donnerstag</option>
      <option>Freitag</option>
    </select>
</body>
</template>

<script>
export default {
  name: 'Dropdown',
  props: {
    data: String
  }
}
</script>

<style scoped>

</style>