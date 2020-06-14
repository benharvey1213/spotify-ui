<template>
  <div class="sidebar">
    <div class="main-nav">
        <div class="options"><div class="options-inner" v-on:click="options()">...</div></div>
        <div id="nav-select-0" class="main-nav-section" v-bind:class="{ 'selected': activeIndex == 0 }" v-on:click="selectNav(0)">
            <div class="flex-container">
                <div class="current-selection" v-bind:class="{ 'selected-nav': activeIndex == 0 }"></div>
                <img class="main-nav-icon" height="20px" width="20px" src="../assets/home.png">
                <div class="section-text">Home</div>
            </div>
        </div>

        <div id="nav-select-1" class="main-nav-section" v-bind:class="{ 'selected': activeIndex == 1 }" v-on:click="selectNav(1)">
            <div class="flex-container">
                <div class="current-selection" v-bind:class="{ 'selected-nav': activeIndex == 1 }"></div>
                <img class="main-nav-icon" height="20px" width="20px" src="../assets/disc.png">
                <div class="section-text">Browse</div>
            </div>
        </div>

        <div id="nav-select-2" class="main-nav-section" v-bind:class="{ 'selected': activeIndex == 2 }" v-on:click="selectNav(2)">
            <div class="flex-container">
                <div class="current-selection" v-bind:class="{ 'selected-nav': activeIndex == 2 }"></div>
                <img class="main-nav-icon" height="20px" width="20px" src="../assets/radio.png">
                <div class="section-text">Radio</div>
            </div>
        </div>

        <div class="library">
            <div class="section-heading first-heading">YOUR LIBRARY</div>
            <div class="section-listing">Made For You</div>
            <div class="section-listing">Recently Played</div>
            <div class="section-listing">Liked Songs</div>
            <div class="section-listing">Albums</div>
            <div class="section-listing">Artists</div>
            <div class="section-listing">Podcasts</div>

            <div class="section-spacing"></div>

            <div class="section-heading">PLAYLISTS</div>
            <div class="section-listing">Rap Bops 🔥</div>
            <div class="section-listing">Soft Pop Hits</div>
            <div class="section-listing">Discover Weekly</div>
            <div class="section-listing">Music I Like</div>
        </div>

        <div class="separator"></div>

        <div class="new-playlist">
            <img height="25px" width="25px" src="../assets/add.png">
            <div>New Playlist</div>
        </div>

        <div class="preview" @mouseover="onAlbum = true" @mouseleave="onAlbum = false" :class="{ 'hidden' : albumHidden}">
            <img class="album-art-img" src="../assets/kanye1.jpg">
            <div class="overlay" v-if="onAlbum">
                <div class="middle" v-on:click="hideArt()" v-if="!albumHidden">
                    <img class="down-arrow" src="../assets/arrowup.png">
                </div>
            </div>
        </div>

    </div>
  </div>
</template>

<script>
export default {
    name: 'LeftNav',
    data: function() {
        return {
            activeIndex: 0,
            onAlbum: false,
            albumHidden: false
        }
    },
    methods: {
        selectNav(index){
            this.activeIndex = index;
        },
        options(){
            console.log('options');
        },
        hideArt(){
            this.albumHidden = true;
            this.$root.$emit('hideArt');
        }
    },
    mounted() {
        this.$root.$on('showArt', () => {
            this.albumHidden = false;
        });
    }
}
</script>

<style scoped>
    * {
        color: white;
    }

    .sidebar {
        width: 200px;
        height: 90vh;
        background-color: rgb(29, 29, 29);
    }

    .main-nav {
        display: flex;
        flex-direction: column;
        height: 100%;
    }

    .options {
        font-size: 2em;
        padding-left: 15px;
        margin-bottom: 30px;
        
        -webkit-user-select: none;  
        -moz-user-select: none;    
        -ms-user-select: none;      
        user-select: none;
    }

    .options-inner {
        width: fit-content;
        cursor: pointer;
    }

    .main-nav-section {
        margin-bottom: 18px;
        cursor: pointer;
        filter: brightness(0.5);
        /* align-items: center; */
    }

    .main-nav-section:hover {
        filter: brightness(0.8);
    }

    .current-selection {
        width: 3px;
        height: 25px;
        margin-right: 15px;
    }

    .section-text {
        margin-left: 15px;
        font-weight: bold;
    }

    .flex-container {
        display: flex;
    }
    
    .selected {
        filter: brightness(1);
    }

    .selected-nav {
        background-color: #1DB954;
    }

    .library {
        padding-left: 20px;
        overflow-y: scroll;
        flex-grow: 2;
        padding-bottom: 20px;
        margin-top: 15px;
    }

    .section-spacing {
        height: 40px;
    }

    .section-heading {
        margin-top: 20px;
        color: rgb(150, 150, 150);
        letter-spacing: 1px;
        font-size: 0.75em;
        font-weight: 600;
    }

    .first-heading {
        margin-top: 0px;
    }

    .section-listing {
        color: rgb(150, 150, 150);
        font-weight: bold;
        margin-top: 18px;
        cursor: pointer;
    }

    .section-listing:hover {
        color: rgb(202, 202, 202);
    }

    .new-playlist {
        max-height: 100px;
        text-align: center;
        display: flex;
        padding-left: 20px;
        padding-top: 15px;
        padding-bottom: 15px;
        align-items: center;
        font-size: 0.9em;
        cursor: pointer;
        color: rgb(255, 255, 255);
        filter: opacity(0.5);
    }

    .new-playlist:hover {
        filter: opacity(0.8);
    }

    .new-playlist img {
        margin-right: 5px;
    }

    .new-playlist div {
        color: inherit;
        font-weight: bold;
    }

    .album-art-img {
        width: 100%;
        height: 200px;
        transition: 0.2s ease-out;
    }

    .separator {
        background-color: rgb(51, 51, 51);
        height: 1px;
    }


    ::-webkit-scrollbar {
        width: 13px;
    }

    ::-webkit-scrollbar-thumb {
        background: rgb(88, 88, 88);
    }

    .preview {
        min-height: 200px;
        height: 200px;
        display: grid;
        transition: 0.2s ease-out;
        overflow: hidden;
        position: relative;
    }

    .hidden {
        min-height: 0px;
        height: 0px;
    }

    .preview img {
        grid-area: 1 / 1 / 4 / 2;
    }

    .overlay {
        grid-area: 1 / 1 / 2 / 2;
        width: 100%;
        height: 200px;
        z-index: 2;
        text-align: right;
        animation: fadein 0.5s;
        -moz-animation: fadein 0.5s;
        -webkit-animation: fadein 0.5s;
        -o-animation: fadein 0.5s;
    }

    .middle {
        margin-top: auto;
        margin-bottom: auto;
    }

    .down-arrow {
        background-color: rgba(0, 0, 0, 0.541);
        border-radius: 25px;
        padding: 5px;
        padding-top: 4px;
        margin: 5px;
        transform: rotate(180deg);
        width: 30px;
        height: 30px;
        cursor: pointer;
    }

    @keyframes fadein {
        from {
            opacity:0;
        }
        to {
            opacity:1;
        }
    }

    @-moz-keyframes fadein {
        /* Firefox */
        from {
            opacity:0;
        }
        to {
            opacity:1;
        }
    }
    @-webkit-keyframes fadein {
        /* Safari and Chrome */
        from {
            opacity:0;
        }
        to {
            opacity:1;
        }
    }
    @-o-keyframes fadein {
        /* Opera */
        from {
            opacity:0;
        }
        to {
            opacity: 1;
        }
    }
   

</style>