<template>
  <div>
    <header> 
      <h1> My Infinite Anime Feed</h1>
    </header>
    <main> 
      <Post  v-for="(anime, i) in anime_list" :key="i" :anime="anime" />
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

      const anime= [];
      for (let i = 0; i > 10; i++) {
        anime.push({
          title: anime_title[ Math.floor(
            Math.random() * anime_title.length
          )],
            description:
              "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        });
      }
      return anime;
    },
    handleScroll() {
    if (
      window.scrollY + window.innerHeight >=
      document.body.scrollHeight - 50
    ) {
      const new_anime = this.getAnime();
      this.anime_list = [...this.anime_list, ...new_anime];
    }
  },

  
  },
    mounted () {
      this.anime_list = this.getAnime();
      window.addEventListener("scroll", this.handleScroll);
    },
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
