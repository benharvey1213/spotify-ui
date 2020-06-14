<template>
  <div class="container">
      <div class="top-nav">
          <img class="arrow-left" height="20px" width="20px" src="../assets/arrowup.png">
          <img class="arrow-right" height="20px" width="20px" src="../assets/arrowup.png">
          <div>
              <input type="text" placeholder="Search">
          </div>
          <div class="expanded"></div>
          <img height="20px" width="20px" src="../assets/profile.png">
          <div class="username">
              <div>ben.harvey1213</div>
          </div>
          <img class="arrow-down" height="20px" width="20px" src="../assets/arrowup.png">
      </div>
      <div class="scrollable">

        <div class="side-padding">
            <div class="title">Home</div>
            
            <div class="subheading-with-nav">
                <div class="subheading">Best Kanye albums</div>
                <div class="expanded"></div>
                <img @click="scrollLeft(1)" class="arrow-left" height="20px" width="20px" src="../assets/arrowup.png">
                <div class="hor-arrow-spacing"></div>
                <img @click="scrollRight(1)" class="arrow-right" height="20px" width="20px" src="../assets/arrowup.png">
            </div>

            <div class="separator"></div>            

            <div id="albums1" class="albums">
                <AlbumArt title="The College Dropout" description="Kanye West" art="kanye1.jpg" first />
                <AlbumArt title="Late Registration" description="Kanye West" art="kanye2.jpg"/>
                <AlbumArt title="Graduation" description="Kanye West" art="kanye3.jpg"/>
                <AlbumArt title="808s and Heartbreak" description="Kanye West" art="kanye4.png"/>
                <AlbumArt title="My Beautiful Dark Twisted Fantasy" description="Kanye West" art="kanye5.jpg"/>
                <AlbumArt title="Yeezus" description="Kanye West" art="kanye6.png"/>
                <AlbumArt title="The Life of Pablo" description="Kanye West" art="kanye7.jpg"/>
                <AlbumArt title="Ye" description="Kanye West" art="kanye8.jpg"/>
                <AlbumArt title="Jesus Is King" description="Kanye West" art="kanye9.png"/>
            </div>

            <div class="subheading-with-nav">
                <div class="subheading">Great artists</div>
                <div class="expanded"></div>
                <img @click="scrollLeft(2)" class="arrow-left" height="20px" width="20px" src="../assets/arrowup.png">
                <div class="hor-arrow-spacing"></div>
                <img @click="scrollRight(2)" class="arrow-right" height="20px" width="20px" src="../assets/arrowup.png">
            </div>

            <div class="separator"></div>
            
            <div id="albums2" class="albums">
                <AlbumArt title="Kanye West" art="kanye.jpg" first artist />
                <AlbumArt title="The Beatles" art="beatles.jpg" artist />
                <AlbumArt title="Tyler, the Creator" art="tyler.jpg" artist />
                <AlbumArt title="Kendrick Lamar" art="kendrick.jpg" artist />
                <AlbumArt title="Mac Miller" art="mac.jpg" artist />
                <AlbumArt title="Daniel Caesar" art="daniel.jpg" artist />
                <AlbumArt title="Rex Orange County" art="rex.jpg" artist />
            </div>

            <div class="subheading-with-nav">
                <div class="subheading">Other great albums</div>
                <div class="expanded"></div>
                <img @click="scrollLeft(3)" class="arrow-left" height="20px" width="20px" src="../assets/arrowup.png">
                <div class="hor-arrow-spacing"></div>
                <img @click="scrollRight(3)" class="arrow-right" height="20px" width="20px" src="../assets/arrowup.png">
            </div>

            <div class="separator"></div>

            <div id="albums3" class="albums">
                <AlbumArt title="Swimming" description="Mac Miller" art="swimming.png" first />
                <AlbumArt title="Sgt. Pepper's Lonely Hearts Club" description="The Beatles" art="pepper.jpg" />
                <AlbumArt title="To Pimp a Butterfly" description="Kendrick Lamar" art="tpab.png"/>
                <AlbumArt title="The Stranger" description="Billy Joel" art="stranger.jpg"/>
                <AlbumArt title="Acid Rap" description="Chance the Rapper" art="acid.jpg"/>
                <AlbumArt title="Kind of Blue" description="Miles Davis" art="blue.jpg"/>
                <AlbumArt title="Steve Lacy's Demo" description="Steve Lacy" art="steve.jpg"/>
            </div>


      </div>
     
        
      </div>
     
  </div>
</template>

<script>
import AlbumArt from './AlbumArt';

export default {
    name: 'MainNav',
    components: {
        AlbumArt
    },
    methods: {
        scrollLeft(id){
            var scrollElem = document.getElementById('albums' + id);
            scrollElem.scroll(scrollElem.scrollLeft - 400, 0);
        },
        scrollRight(id){
            var scrollElem = document.getElementById('albums' + id);
            scrollElem.scroll(scrollElem.scrollLeft + 400, 0);
        }
    }
}
</script>

<style scoped>
    * {
        color: white;
    }

    .test {
        height: 500px;
        background-color: green;
    }

    ::-webkit-scrollbar {
        width: 13px;
    }

    ::-webkit-scrollbar-thumb {
        background: rgb(88, 88, 88);
    }

    .container {
        width: 100%;
        height: 90vh;
        
        background: rgb(41,41,41);
        /* background: linear-gradient(0deg, rgba(41,41,41,1) 70%, rgba(62,62,62,1) 100%); */

        display: flex;
        /* flex-direction: column; */
        flex-flow: column;
        /* overflow-y: scroll; */
    }

    .scrollable {
        /* height: 80vh; */
        flex: 2;
        /* height: 100%; */
        overflow-y: scroll;
    }

    .separator {
        height: 1px;
        margin-top: 15px;
        margin-bottom: 15px;
        background-color: rgb(53, 53, 53);
    }

    .hor-arrow-spacing {
        width: 15px;
    }

    .top-nav {
        display: flex;
        padding: 10px;
        align-items: center;
    }

    .top-nav img {
        margin-right: 8px;
    }

    .top-nav input {
        border-radius: 25px;
        border: none;
        outline: none;
        padding-top: 5px;
        padding-bottom: 5px;
        padding-left: 10px;
        padding-right: 10px;
        color: rgb(87, 87, 87);
    }

    .expanded {
        flex-grow: 2;
    }

    .side-padding {
        padding-left: 25px;
        padding-right: 25px;
    }

    .title {
        font-size: 3em;
        font-weight: 900;
        margin-top: 75px;
        margin-bottom: 50px;
        letter-spacing: 1.5px;
    }

    .username {
        margin-right: 8px;
    }

    .arrow-down {
        transform: rotate(180deg);
    }

    .arrow-left {
        transform: rotate(270deg);
    }

    .arrow-right {
        transform: rotate(90deg);
    }

    .subheading-with-nav {
        margin-top: 35px;
        display: flex;
        align-items: center;
    }

    .subheading {
        font-weight: bold;
        letter-spacing: 0.8px;
    }

    .albums {
        display: flex;
        flex-direction: row;
        overflow-x: hidden;
        scroll-behavior: smooth;
    }

    .arrow-left, .arrow-right {
        cursor: pointer;
        filter: brightness(0.5);
    }

    .arrow-left:hover, .arrow-right:hover {
        filter: brightness(0.8);
    }

</style>