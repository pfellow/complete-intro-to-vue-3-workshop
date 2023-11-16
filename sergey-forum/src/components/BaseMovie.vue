<script lang="ts">
import AddNewActor from './AddNewActor.vue';
import CharacterCoolness from './CharacterCoolness.vue'
import FavoriteList from './FavoriteList.vue';

export default {
    components: {
    CharacterCoolness,
    FavoriteList,
    AddNewActor
},
    data() {
        return {
            movie: {
                title: "Friends",
                createdBy: "David Crane, Marta Kauffman",
                starring: [
                    "Jennifer Aniston",
                    "Courteney Cox",
                    "Lisa Kudrow",
                    "Matt LeBlanc",
                    "Matthew Perry",
                    "David Schwimmer"
                ],
                seasons: 10,
                dates: "September 22, 1994 – May 6, 2004"
            },
            favorList: [] as string[]
        };
    },
    methods: {
        favor(actor: string) {
            if (this.favorList.includes(actor)) {
                this.favorList = this.favorList.filter((fav) => fav !== actor);
            }
            else {
                this.favorList.push(actor);
            }
        },
        addActor(newActor: string) {
            this.movie.starring.push(newActor);
        },
        lettersCount(name: string) {
            return name.length;
        }
    },
}
</script>

<template>
  <h2>{{ movie.title }}</h2>
  <div>Created by: {{ movie.createdBy }}</div>
  <div v-if="movie.starring.length === 0">Starring: sorry, no data</div>
  <ul v-else>
    Starring:
    <li v-for="(actor, index) in movie.starring" :key="index">
      <span @click="favor(actor)"> ❤️ {{ actor }}: {{ lettersCount(actor) }}</span>
    </li>
  </ul>
  <AddNewActor v-on:add-actor="addActor" />
  <div>Seasons: {{ movie.seasons }}</div>
  <div>Release dates: {{ movie.dates }}</div>
  <FavoriteList :favorList="favorList" />
  <CharacterCoolness :movie="movie" />
</template>
