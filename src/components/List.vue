<template> 
<body>
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
</template>

<script>
export default {
  name: 'List',
  props: {
    data: String
  }
}
</script>

<style scoped>

</style>