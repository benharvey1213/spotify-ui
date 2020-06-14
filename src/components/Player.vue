<template>
  <div class="container">
      <div class="song-info">
          <div class="song-title">
                Through the Wire
                <!-- <img height="15px" width="15px" src="../assets/heart.png"> -->
          </div>
          <div class="song-artist">Kanye West</div>
      </div>

      <div class="player">
          <div class="progress-controls">
              <img class="rotate180" height="15px" width="15px" src="../assets/skip-right.png">
              <div class="control-spacer"></div>
              <img class="rotate180" height="15px" width="15px" src="../assets/skip-right.png">
              <div class="control-spacer"></div>
              <img height="35px" width="35px" src="../assets/play.png">
              <div class="control-spacer"></div>
              <img height="15px" width="15px" src="../assets/skip-right.png">
              <div class="control-spacer"></div>
              <img height="15px" width="15px" src="../assets/skip-right.png">
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
            <input class="volume-slider" type="range" id="points" name="points" min="0" max="100">
      </div>
  </div>
</template>

<script>
export default {
    name: 'Player'
}
</script>

<style scoped>
    * {
        color: white;
    }

    .rotate180 {
        transform: rotate(180deg);
    }

    .container {
        height: 10vh;
        /* height: 20px; */
        width: 100vw;
        background-color: rgb(51, 51, 51);
        display: flex;
    }

    .song-info {
        padding: 10px;
        width: 200px;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    .player {
        flex-grow: 2;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 10px;
    }

    .song-title {
        font-weight: 500;
        margin-bottom: 8px;
        letter-spacing: 0.5px;
    }

    .song-artist {
        font-size: 0.75em;
    }

    .controls {
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding: 10px;
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

    /* .volume-slider {
        width: 100%;
        background: transparent;
    }

    .volume-slider::-webkit-slider-thumb {
        background-color: white;
    } */
    
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
        width: 400px;
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

</style>