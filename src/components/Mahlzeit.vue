<template>
  <div>
      
      <h5>{{mahlzeiten.category}}</h5>
      <hr/>
      <h3>{{mahlzeiten.name}}</h3>
      {{mahlzeiten.cost.students}} <br/>
      DV: {{mahlzeiten.upvotes}}
      <div class="ci" v-for="ci in mahlzeiten.contentInformation" :key="ci"><small>{{ci}}</small></div>
      <button v-on:click="sendUpvote(mahlzeiten.id)"><b-icon icon="hand-thumbs-up" variant="success"></b-icon> (0)</button>
      <button v-on:click="sendDownvote(mahlzeiten.id)"><b-icon icon="hand-thumbs-down" variant="danger"></b-icon> (0)</button>
  </div>
</template>

<script>
//import axios from 'axios'
import Vue from 'vue'
import { BootstrapVue, BootstrapVueIcons } from 'bootstrap-vue'

Vue.use(BootstrapVue)
Vue.use(BootstrapVueIcons)

export default {
  name: 'Mahlzeit',
  props: {
    mahlzeiten: Object
  },
  methods: {
    sendUpvote: function(likedId) {
      console.log("sending upvote for "+likedId);
      this.$socket.emit("broadcastLike", likedId);
    },
    sendDownvote: function(id) {
      console.log("Sending downvote for "+id);
      //Axios
    }
  },
  mounted() {
      this.sockets.subscribe("broadcastLike", (likedId) => {
          if(likedId === this.mahlzeiten.id) {
            this.mahlzeiten.upvotes++;
          }
      });
  }
}
</script>

<style scoped>
  .ci {
    font-size:8pt;
    display: inline-block;
    margin-right:10px;
  }
</style>