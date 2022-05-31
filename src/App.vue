<template>
    <nav-bar />
    <h2>NOTES</h2>
    <div v-if="notes != []">
        <div id="notes" v-for="note in notes" :key="note.id">
            <div>{{note.title}}</div>
            <div>Последнее изменение: {{moment(note.updated_at).fromNow()}}</div>
            <a href="{{note/id/note._id}}">Подробнее</a>
        </div>
    </div>

    <div v-else>Notes not found.</div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import axios from 'axios'
import moment from 'moment'

moment.locale("ru")
const host = "http://172.18.9.6:8081"

export default {
  name: 'App',
  components: {
    NavBar,
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
  },
  methods: {
    moment
  }
}
</script>

<style>
body {
    background: #e4f68f;
    display: flex;
    align-items: center;
    justify-content: center;
}
#notes {
    margin: 5%;
    border-radius: 2%;
    background-color: #50c19a;
}
</style>
