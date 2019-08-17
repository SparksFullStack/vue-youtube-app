

<template>
    <div>
        <div class="columns is-centered">
            <SearchBar @termChange="onTermChange" class="column is-half">
            </SearchBar>
        </div>
        <div class="columns main-column">
            <div class="column is-two-thirds">
                Video goes here
            </div>
            <VideoList :videos="videos" class="column is-one-third">
            </VideoList>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
import axios from 'axios';

import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
const API_KEY = 'AIzaSyAdskY9qJ8TK8crZ-Yug7XcVLH2dpZRAcs';

export default {
    name: 'App',
    data() {
        return {
            videos: []
        }
    },
    components: {
        SearchBar,
        VideoList
    },
    methods: {
        onTermChange(searchTerm) {
           axios.get('https://www.googleapis.com/youtube/v3/search', {
               params: {
                   key: API_KEY,
                   type: 'video',
                   part: 'snippet',
                   q: searchTerm
               }
           })
           .then(response => this.videos = response.data.items)
           .catch(err => console.log('err', err));
        }
    }
};
</script>

<style>
    @import "~bulma/css/bulma.css";
    .main-column {
        margin-left: 15px;
        margin-right: 15px;
    }
</style>