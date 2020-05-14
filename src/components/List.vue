<template> 
<div>
<table border="1">
      <th>Kategorie</th>
      <th>Infos</th>
      <th>Kosten</th>
      <th>Tag</th>
      <th>Downvotes</th>
      <th>ID</th>
      <th>Labels</th>
      <th>Name</th>
      <th>Upvotes</th>

      <tr v-for="meal in listEssen" :key="meal">
            <th>{{meal.category}}</th>
            <td>{{meal.contentInformation}}</td>
            <td>{{meal.cost}}</td>
            <td>{{meal.day}}</td>
            <td>{{meal.downvotes}}</td>
            <td>{{meal.id}}</td>
            <td>{{meal.labels}}</td>
            <td>{{meal.name}}</td>
            <td>{{meal.upvotes}}</td>
          </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'List',
  props: {
    listEssen: Object
  }
}
</script>

<style scoped>

</style>