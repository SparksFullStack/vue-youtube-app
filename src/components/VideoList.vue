<template>
    <ul>
        <VideoListItem :key="video.etag" v-for="video in videos" :video="video">
        </VideoListItem>
    </ul>
</template>

<script>
import VideoListItem from './VideoListItem';
export default {
    name: 'VideoList',
    props: {
        videos: Array
    },
    components: {
        VideoListItem
    }
}
</script>

<style scoped>

</style>