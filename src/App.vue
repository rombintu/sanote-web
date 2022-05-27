<template>
    <h2>NOTES</h2>
    <div v-if="notes == []">
        <ul>
            <li v-for="note in notes" :key="note.id">{{note.Title}}</li>
        </ul>
    </div>

    <div v-else>Notes not found.</div>
</template>

<script>
// import IndexNotes from './components/IndexNotes.vue'
import axios from 'axios'

const host = "http://172.18.9.6:8081"

export default {
  name: 'App',
  components: {
   // IndexNotes,
  },
  data() {
    return {
        notes: [],
    }
  },
  mounted() {
    axios.get(`${host}/note`, {params: {'author': 'admin'}})
        .then((response) => {
            console.log(response.data)
            this.notes = response.data;
        }).catch((err) => {
            console.log("ERROR", err)
        })
  }
}
</script>

<style>

</style>
