<template>
  <div class="container">
      <div class="top-nav">
          <img class="menu" height="25px" width="25px" src="../assets/menu.png" v-on:click="togglePopout()">

          <img class="arrow-left nav-left" height="20px" width="20px" src="../assets/arrowup.png">
          <img class="arrow-right nav-right" height="20px" width="20px" src="../assets/arrowup.png">

          <div>
              <input type="text" placeholder="Search">
          </div>
          <div class="expanded"></div>
          <img class="profile" height="20px" width="20px" src="../assets/profile.png">
          <div class="username">
              <div>ben.harvey1213</div>
          </div>
          <div class="dropdown">
            <img class="arrow-down profile-arrow" height="20px" width="20px" src="../assets/arrowup.png" v-on:click="userDropdownToggled = !userDropdownToggled">
            <div class="user-dropdown" :class="{ 'dropdown-show' : userDropdownToggled }">
                <a href="https://www.github.com" target="_blank">
                    <div class="dropdown-text">
                        Check out this project on Github
                    </div>
                </a>
                
                <a href="https://www.benharvey.dev" target="_blank">
                    <div class="dropdown-text-2">
                        <a href="https://www.benharvey.dev" target="_blank">View the rest of my portfolio</a>
                    </div>
                </a>
                
            </div>
          </div>
          
      </div>
      <div class="scrollable">

        <div class="title">
            <div class="title-inner">Home</div>
        </div>

        <div class="side-padding">
            
            
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
    data: function() {
        return {
            userDropdownToggled: false,
        }
    },
    methods: {
        scrollLeft(id){
            var scrollElem = document.getElementById('albums' + id);
            scrollElem.scroll(scrollElem.scrollLeft - 400, 0);
        },
        scrollRight(id){
            var scrollElem = document.getElementById('albums' + id);
            scrollElem.scroll(scrollElem.scrollLeft + 400, 0);
        },
        togglePopout() {
            // this.popoutToggled = !this.popoutToggled;
            this.$root.$emit('togglePopout');
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
        flex: 2;
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
        /* transition: ; */
        background: rgb(41,41,41);
        background: linear-gradient(0deg, rgba(41,41,41,1) 0%, rgba(51,51,51,1) 100%);
        box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.404);
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
        padding-top: 75px;
        padding-bottom: 50px;
        
        background: rgb(41,41,41);
        background: linear-gradient(0deg, rgba(41,41,41,1) 0%, rgba(82,82,82,1) 100%);

        padding-left: 25px;
        letter-spacing: 1.5px;

        /* position: -webkit-sticky; 
        position: sticky;
        top: 0px; */
        
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
        /* overflow-x: hidden; */
        overflow-x: scroll;
        scroll-behavior: smooth;
    }

    ::-webkit-scrollbar {
        height: 0px;
    }

    .arrow-left, .arrow-right {
        cursor: pointer;
        filter: brightness(0.5);
    }

    .arrow-left:hover, .arrow-right:hover {
        filter: brightness(0.8);
    }

    .profile-arrow {
        filter: brightness(0.5);
        cursor: pointer;
    }

    .profile-arrow:hover {
        filter: brightness(0.8);
    }

    .profile {
        filter: brightness(0.5);
        cursor: pointer;
    }

    .profile:hover {
        filter: brightness(0.8);
    }

    .menu {
        display: none;
        cursor: pointer;
        filter: brightness(0.5);
    }

    .menu:hover {
        filter: brightness(0.8);
    }

    /* Dropdowns */
    .user-dropdown {
        display: inline-block;
        display: none;
        position: absolute;
        text-align: center;
        z-index: 1;
        background-color: rgb(65, 65, 65);
        box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.548);
        min-width: 250px;
        right: 0;
        /* padding: 20px; */
        border-radius: 5px;
    }

    .user-dropdown a {
        text-decoration: none;
    }

    .user-dropdown-item {
        width: 200px;
    }

    .dropdown {
        position: relative;
        display: inline-block;
    }

    .dropdown-text, .dropdown-text-2 {
        font-size: 0.9em;
        cursor: pointer;
        /* padding-top: 20px; */
        /* padding-bottom: 10px; */
    }

    .dropdown-text:hover, .dropdown-text-2:hover {
        background-color: rgb(116, 116, 116);
    }

    .dropdown-text {
        padding-top: 10px;
        padding-bottom: 10px;
        border-top-left-radius: 5px;
        border-top-right-radius: 5px;
    }

    .dropdown-text-2 {
        padding-top: 10px;
        padding-bottom: 10px;
        border-bottom-left-radius: 5px;
        border-bottom-right-radius: 5px;
    }

    .dropdown-show {
        display: block;
    }

    @media only screen and (max-width: 950px) {
        .container {
            height: 85vh;
            /* height: 100%; */
        }

        .menu {
            display: inline;
        }

        .username {
            display: none;
        }

        .nav-left, .nav-right {
            display: none;
        }
    }

    @media only screen and (max-width: 450px) {
        ::-webkit-scrollbar {
            width: auto;
            
        }

        ::-webkit-scrollbar-thumb {
            background: auto;
        }

        .side-padding {
            padding-left: 10px;
            padding-right: 10px;
        }
    }




</style>