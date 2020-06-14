<template>
  <div :class="{ 'first' : first }" class="container-album">
      <div class="art" @mouseover="overAlbum()" @mouseleave="leaveAlbum()">
        <img :class="{ 'greyed' : onAlbum , 'artist' : artist }" :src="require(`@/assets/${art}`)">
        <div v-if="onAlbum" class="more-info"> 
            <div class="middle">
                <img id="heart" src="../assets/heart.png">
            </div>
            <div class="middle">
                <img id="play" src="../assets/play.png">
            </div>
            <div class="middle">
                <img id="ellipses" src="../assets/ellipses.png">
            </div>
        </div>
      </div>
      <a href="#" class="title" :class="{ 'centered' : artist }" >{{ title }}</a>
      <div class="description">{{ description }}</div>
  </div>
</template>

<script>

export default {
    name: 'AlbumArt',
    props: {
        title: String,
        description: String,
        art: String,
        first: Boolean,
        artist: Boolean
    },
    data: function() {
        return {
            onAlbum: false
        }
    },
    methods: {
        overAlbum() {
            this.onAlbum = true;
        },

        leaveAlbum() {
            this.onAlbum = false;
        }
    },
    beforeMount(){
        if (!this.first){
            this.first = false;
        }
    }
}
</script>

<style scoped>
    .container-album {
        display: flex;
        flex-direction: column;
        flex: 0 0 190px;
        padding: 10px;
    }

    .artist {
        border-radius: 50%;
    }

    .first {
        padding-left: 0px;
    }

    .container img {
        width: 190px;
        /* height: 190px; */
        object-fit: cover;
    }

    .title {
        font-weight: bold;
        letter-spacing: 0.8px;
        margin-top: 12px;
        margin-bottom: 3px;
    }

    .description {
        color: rgb(153, 153, 153);
        font-size: 0.9em;
    }

    a {
        color: white;
        text-decoration: none;
    }

    .centered {
        text-align: center;
    }

    a:hover {
        text-decoration: underline;
    }

    .art {
        display: grid;
    }

    .greyed {
        filter: brightness(0.4);
    }

    .art img {
        grid-area: 1 / 1 / 4 / 2;
    }

    .more-info {
        grid-area: 1 / 1 / 2 / 2;
        width: 100%;
        height: 190px;
        /* background-color: green; */
        color: white;
        z-index: 2;
        text-align: center;
        vertical-align: middle;
        display: flex;
        justify-content: space-between;
        padding: 20px;
    }

    .middle {
        margin-top: auto;
        margin-bottom: auto;
    }

    #play {
        width: 65px;
        transition: 0.2s;
        border-radius: 50px;
    }

    #play:hover {
        width: 70px;
    }

    #heart {
        width: 30px;
        filter: brightness(0.6);
    }

    #heart:hover {
        filter: brightness(1);
    }

    #ellipses {
        width: 30px;
        filter: brightness(0.6);
    }

    #ellipses:hover {
        filter: brightness(1);
    }

</style>