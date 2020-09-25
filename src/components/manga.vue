<template>
    <div>
        <input type="text" v-model="textSearch" />
        <button @click="searchData()">Search</button><br><br>
        <div v-for="list in playList" :key="list.mal_id">
            <b-card-group columns>
                <b-card
                    v-for="list in playList"
                    :key="list.null"
                    :title="list.title"
                    :img-src="list.image_url"
                    :img-alt="list.null"
                    :href="list.url"
                    img-top
                    tag="article"
                    style="max-width: 20rem;"
                    class="mb-2"
                >
                    <b-button :href="list.url" variant="primary">Go somewhere</b-button>
                </b-card>
            </b-card-group>
        </div>
        <!--{{playList}}-->
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            playList:null,
            textSearch:"",
        }
    },
    methods: {
        searchData(){
            axios
            .get('https://api.jikan.moe/v3/search/manga?q='+this.textSearch+'&page=1')
            .then((Response)=>{
                this.playList = Response.data.results
            })
            .catch((err)=>{
                console.log(err)
            })
        }
    },
}
</script>

<style>
    
</style>