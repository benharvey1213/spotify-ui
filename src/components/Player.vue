<template>
    <div class="container">
        <div class="song-info">
            <div class="art" :class="{ 'hide' : !artHidden }" @mouseover="onAlbum = true" @mouseleave="onAlbum = false">
                <img class="thumbnail" src="../assets/kanye1.jpg">
                <div class="overlay" :class="{ 'overlay-on' : onAlbum}" >
                    <div class="middle" v-on:click="hideArt()">
                        <img class="down-arrow" src="../assets/arrowup.png">
                    </div>
                </div>
            </div>

            <div class="info">
                <div class="song-title">
                    <a href="#">Through the Wire</a>
                    <img class="heart" height="18px" width="18px" src="../assets/heart.png">
                </div>
                <div>
                    <a class="song-artist" href="#">Kanye West</a>
                </div>
            </div>
            
        </div>

        <div class="player">
            <div class="progress-controls">
                <img class="shuffle" height="15px" width="15px" src="../assets/shuffle.png">
                <div class="control-spacer"></div>
                <img class="rotate180" height="15px" width="15px" src="../assets/skip-right.png">
                <div class="control-spacer"></div>
                <img height="35px" width="35px" src="../assets/play.png">
                <div class="control-spacer"></div>
                <img height="15px" width="15px" src="../assets/skip-right.png">
                <div class="control-spacer"></div>
                <img class="repeat" height="15px" width="15px" src="../assets/repeat.png">
            </div>
            <div class="progress-container">
                <div class="time-left">2:01</div>
                <div class="progress-bar">
                    <div class="progress-bar-inner">

                    </div>
                </div>
                <div class="time-right">3:59</div>
            </div>
        </div>

        <div class="controls">
            <img height="22px" width="22px" src="../assets/queue.png">
            <div class="spacer"></div>
            <img height="18px" width="18px" src="../assets/devices.png">
            <div class="spacer"></div>
            <img height="20px" width="20px" src="../assets/volume-high.png">
            <div class="spacer"></div>
            <input class="volume-slider" type="range" id="points" name="points" min="0" max="100">
            <div class="spacer"></div>
            <img height="18px" width="18px" src="../assets/fullscreen.png">
            <div class="spacer"></div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Player',
    mounted() {
        this.$root.$on('hideArt', () => {
            this.artHidden = true;
        });
    },
    data: function() {
        return {
            artHidden: false,
            onAlbum: false
        }
    },
    methods: {
        hideArt(){
            this.artHidden = false;
            this.$root.$emit('showArt');
        }
    }
}
</script>

<style scoped>
    * {
        color: white;
    }

    .rotate180 {
        transform: rotate(180deg);
    }

    .spacer {
        width: 15px;
    }

    a {
        text-decoration: none;
    }

    a:hover {
        text-decoration: underline;
    }

    .container {
        height: 10vh;
        /* height: 20px; */
        width: 100vw;
        background-color: rgb(51, 51, 51);
        display: flex;
        /* z-index: 4; */
    }

    .song-info {
        padding: 10px;
        /* width: 200px; */
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }

    .player {
        flex-grow: 2;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 10px;
    }

    .art {
        height: 60px;
        width: 60px;
        /* margin-right: 15px;
        margin-left: 5px; */
        display: grid;
        transition: 0.2s ease-out;
        overflow: hidden;
        grid-area: 1 / 1 / 4 / 2;
        margin-right: 15px;
    }

    .thumbnail {
        height: 60px;
        width: 60px;
        grid-area: 1 / 1 / 4 / 2;
    }

    .overlay {
        grid-area: 1 / 1 / 2 / 2;
        height: 200px;
        text-align: right;

        animation: fadein 0.5s;
        -moz-animation: fadein 0.5s;
        -webkit-animation: fadein 0.5s;
        -o-animation: fadein 0.5s;
        opacity: 0.2;
    }

    .overlay-on {
        opacity: 1;
    }

    .down-arrow {
        background-color: rgba(0, 0, 0, 0.541);
        border-radius: 25px;
        padding: 2px;
        margin: 5px;
        height: 20px;
        width: 20px;
        cursor: pointer;
    }

    .hide {
        width: 0px;
    }

    .song-title {
        font-weight: 500;
        margin-bottom: 5px;
        letter-spacing: 0.5px;
        font-size: 0.95em;
        display: flex;
        align-items: center;
    }

    .song-artist {
        font-size: 0.75em;
        color: rgb(145, 145, 145);
        letter-spacing: 0.5px;
    }

    .controls {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        padding: 10px;
    }

    .controls img {
        filter: brightness(0.5);
        cursor: pointer;
    }

    .controls img:hover {
        filter: brightness(0.8);
    }

    .heart {
        margin-left: 10px;
        /* margin-top: 2px; */
        filter: brightness(0.7);
    }

    .heart:hover {
        filter: brightness(1);
    }

    .progress-controls {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    .progress-controls img:hover {
        cursor: pointer;
    }

    .play-button {
        margin-left: 15px;
        margin-right: 15px;
    }

    .control-spacer {
        width: 20px;
    }

    .volume-slider {
        width: 100px;
        height: 5px;
        -webkit-appearance: none;
        /* background: transparent; */
        border-radius: 25px;
        background-color: rgb(63, 63, 63);
        outline: none;
        cursor: pointer;
    }

    .volume-slider::-webkit-slider-thumb {
        -webkit-appearance: none;
        width: 13px;
        height: 13px;
        background-color: rgb(219, 219, 219);
        border-radius: 25px;
        cursor: pointer;
        /* visibility: hidden; */
        outline: none;
    }

    .volume-slider::-moz-range-track {
        background-color: green;
    }

    .volume-slider::webkit-slider-thumb:hover {
        visibility: visible;
    }
    
    .controls .progress {
        width: 100%;
    }

    .progress-container{
        display: flex;
        flex-direction: row;
        align-items: center;
        margin-top: 5px;
    }

    .progress-bar {
        width: 600px;
        /* max-width: 800px; */
        flex-grow: 2;
        /* max-width: 5; */
        height: 5px;
        background-color: rgb(63, 63, 63);
        margin-left: 10px;
        margin-right: 10px;
        border-radius: 25px;
    }

    .progress-bar-inner {
        width: 20%;
        background-color: rgb(139, 23, 23);
    }

    .time-left {
        font-size: 0.8em;
        color: rgb(182, 182, 182)
    }

    .time-right {
        font-size: 0.8em;
        color: rgb(182, 182, 182)
    }

    .shuffle, .repeat {
        filter: brightness(0.5);
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