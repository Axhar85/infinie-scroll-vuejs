<template>
  <div>
    <header> 
      <h1> My Anime Feed</h1>
    </header>
    <main> 
      <Post />
    </main>
  </div>
</template>

<script>
import Post from "./components/Post.vue";
export default {
  name: 'App',
  data () {
    return {
      anime_list: []
    }
  },
  components: {
    Post,
  },
  methods: {
    getAnime () {
      const anime_title = [
        "Naruto",
				"Demon Slayer",
				"Dragon Ball",
				"My Hero Academia",
				"Sword Art Online",
				"Tokyo Ghoul",
				"Darling in the Franxx",
				"Code Geass",
				"One Piece",
				"Fairy Tail",
				"Bleach",
				"Attack on Titan",
				"Hunter x Hunter",
      ];
    }
  }
}
</script>

<style>
* {
  margin: 0;
  box-sizing: border-box;
}
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  background-color: #2c3e50;
  color: #fff;
  min-height: 100vh;
  padding-top: 3rem;
}

header{
  margin-bottom: 2rem;
}

header h1{
  text-align: center;
}

main{
  padding: 0 2rem;
  max-width: 640px;
  margin: 0 auto;
}
</style>
