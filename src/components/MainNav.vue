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
                <div class="subheading">Recently played</div>
                <div class="expanded"></div>
                <img class="arrow-left" height="20px" width="20px" src="../assets/arrowup.png">
                <div class="hor-arrow-spacing"></div>
                <img class="arrow-right" height="20px" width="20px" src="../assets/arrowup.png">
            </div>

            <div class="separator"></div>            

            <div class="albums">
                <AlbumArt title="The College Dropout" description="Kanye West" art="kanye1.jpg" first="True"/>
                <AlbumArt title="Late Registration" description="Kanye West" art="kanye2.jpg"/>
                <AlbumArt title="Graduation" description="Kanye West" art="kanye3.jpg"/>
                <AlbumArt title="808s and Heartbreak" description="Kanye West" art="kanye4.png"/>
                <AlbumArt title="My Beautiful Dark Twisted Fantasy" description="Kanye West" art="kanye5.jpg"/>
            </div>

            <div class="subheading-with-nav">
                <div class="subheading">Recently played</div>
                <div class="expanded"></div>
                <img class="arrow-left" height="20px" width="20px" src="../assets/arrowup.png">
                <div class="hor-arrow-spacing"></div>
                <img class="arrow-right" height="20px" width="20px" src="../assets/arrowup.png">
            </div>

            <div class="separator"></div>
            
            <div class="albums">
                <AlbumArt title="The College Dropout" description="Kanye West" art="kanye1.jpg" first="True"/>
                <AlbumArt title="Late Registration" description="Kanye West" art="kanye2.jpg"/>
                <AlbumArt title="Graduation" description="Kanye West" art="kanye3.jpg"/>
                <AlbumArt title="808s and Heartbreak" description="Kanye West" art="kanye4.png"/>
                <AlbumArt title="My Beautiful Dark Twisted Fantasy" description="Kanye West" art="kanye5.jpg"/>
            </div>

            <div class="subheading-with-nav">
                <div class="subheading">Recently played</div>
                <div class="expanded"></div>
                <img class="arrow-left" height="20px" width="20px" src="../assets/arrowup.png">
                <div class="hor-arrow-spacing"></div>
                <img class="arrow-right" height="20px" width="20px" src="../assets/arrowup.png">
            </div>

            <div class="separator"></div>

            <div class="albums">
                <AlbumArt title="The College Dropout" description="Kanye West" art="kanye1.jpg" first />
                <AlbumArt title="Late Registration" description="Kanye West" art="kanye2.jpg" />
                <AlbumArt title="Graduation" description="Kanye West" art="kanye3.jpg"/>
                <AlbumArt title="808s and Heartbreak" description="Kanye West" art="kanye4.png"/>
                <AlbumArt title="My Beautiful Dark Twisted Fantasy" description="Kanye West" art="kanye5.jpg"/>
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
        height: 100%;
        
        background: rgb(41,41,41);
        /* background: linear-gradient(0deg, rgba(41,41,41,1) 70%, rgba(62,62,62,1) 100%); */

        flex-direction: column;
        /* overflow-y: scroll; */
    }

    .scrollable {
        height: 80vh;
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
        color: black;
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
        margin-top: 20px;
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
    }

</style>