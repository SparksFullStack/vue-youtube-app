

<template>
    <div>
        <SearchBar @termChange="onTermChange">
        </SearchBar>
        <VideoList :videos="videos">
        </VideoList>
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