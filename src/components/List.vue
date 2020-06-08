<template> 
<div>
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      background="#ababab"
      img-width="1024"
      img-height="480"
      style="text-shadow: 1px 1px 2px #333;"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <b-carousel-slide class="slide" img-src="https://picsum.photos/1024/480/?image=52">
          <Mahlzeit class="mahlzeit" v-for="Mahlzeit in listEssen" :key="Mahlzeit" :mahlzeiten="Mahlzeit"></Mahlzeit>
      </b-carousel-slide>
    </b-carousel>
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