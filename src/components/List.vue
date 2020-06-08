<template> 
<div>
    <b-card
    img-src="https://picsum.photos/600/300/?image=25"
    img-alt="Image"
    img-top
    tag="article"
    style="max-width: 20rem;"
    class="mb-2">
    <b-card-text>
        <Mahlzeit class="mahlzeit" v-for="Mahlzeit in listEssen" :key="Mahlzeit" :mahlzeiten="Mahlzeit"></Mahlzeit>
    </b-card-text>
  </b-card>
</div>

</template>

<script>
import Mahlzeit from "../components/Mahlzeit.vue"

export default {
  name: 'List',
  props: {
    listEssen: Array
  },
  components: {
      Mahlzeit
    }
}
</script>

<style scoped>
.mahlzeit {
  max-width: 500px;
  margin-left:auto;
  margin-right:auto;
  margin-bottom:50px;
}

.slide {
  height:400px;
}
</style>