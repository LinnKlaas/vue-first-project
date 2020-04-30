<template>
  <!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Speiseplan</title>
    <link rel="stylesheet" href="style.css">
    <script src="webserver.js"></script>
  </head>
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
    <br><br>
    <table border="1">
      <tr>
        <th>Category</th>
        <th>Content Information</th>
        <th>Cost</th>
      </tr>
      <tr>
        <td>Suppe</td>
        <td>mit Antioxidationsmittel, A,
          Weizengluten,
          Eier,
          Sellerie</td>
        <td>employees: 0,90€,
          guests: 1,40€,
          students: 0,70€</td>
       </tr>
    </table>
  </body>
</html>


</template>

<script>
export default {
  name: 'Plan',
  props: {
    msg: String
  }
}
</script>

<style scoped>

</style>
