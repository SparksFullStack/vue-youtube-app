<template>
    <li class="columns">
        <div class="column is-one-quarter">
            <img :src="video.snippet.thumbnails.default.url" class="list-thumbail"/>
        </div>

        <div class="column">
            {{ video.snippet.title }}
        </div>
    </li>
</template>

<script>
export default {
    name: 'VideoListItem',
    props: {
        video: Object
    }    
}
</script>

<style scoped>
</style>