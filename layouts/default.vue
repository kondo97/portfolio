
<template>
  <div>
    <header class="container mx-auto">
      <div class="mt-6 mb-6 px-4 relative container mx-auto text-center">
        <div>
          <div class="flex justify-center">
            <div
              class="
                bg-center bg-cover
                w-16
                h-16
                mr-4
                rounded-full
                shadow
                photo
              "
            ></div>
            <h1 class="text-xl font-bold flex items-center">Sei Kondo</h1>
          </div>
          <p class="text-lg my-6 introduction-width mx-auto text-left">
            フロントエンドエンジニアを目指しているSei
            Kondoです。フルスタックエンジニアとして、たくさんの新サービス開発に携わるのが目標です。
          </p>
        </div>
        <div class="flex justify-around text-xs icon-length">
          <nuxt-link to="/">
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faHome" />
              </fa-layers>
              Home
            </button>
          </nuxt-link>
          <a href="https://twitter.com/NdXZizhmlwdJRWF" target="_blank" rel="noopener noreferrer">
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faTwitter" />
              </fa-layers>
              Twitter
            </button>
          </a>
          <a
            href="https://github.com/kondo97"
            target="_blank"
            rel="noopener noreferrer"
          >
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faGithub" />
              </fa-layers>
              GitHub
            </button>
          </a>
          <a
            href="https://qiita.com/kondo97"
            target="_blank"
            rel="noopener noreferrer"
          >
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faSearch" />
              </fa-layers>
              Qiita
            </button>
          </a>
        </div>
        <input
          type="text"
          placeholder="Keywords"
          class="
            bg-gray-300
            p-2
            text-xs
            rounded
            w-full
            mt-5
            focus:outline-none
            search-width
          "
          v-model="keyword"
          @keypress.enter="$router.push('/search/' + keyword)"
        />
      </div>
    </header>
    <main class="w-full mt-16 mb-16">
      <div class="items-wrap mx-auto">
        <nuxt />
      </div>
    </main>
  </div>
</template>

<script>
import { faTwitter } from "@fortawesome/free-brands-svg-icons";
import { faGithub } from "@fortawesome/free-brands-svg-icons";
import { faHome } from "@fortawesome/free-solid-svg-icons";
import { faSearch } from "@fortawesome/free-solid-svg-icons";
export default {
  data() {
    return {
      keyword: "",
    };
  },
  computed: {
    faTwitter() {
      return faTwitter;
    },
    faGithub() {
      return faGithub;
    },
    faHome() {
      return faHome;
    },
    faSearch() {
      return faSearch;
    },
  },
};
</script>

<style>
html {
  width: 100%;
}

body {
  background-color: #2a2a2a;
  color: #f2f2f2;
}

.photo {
  min-width: 4rem;
  min-height: 4rem;
  background-image: url("~/static/my-picture.png");
}
button:focus {
  outline: none;
}

.introduction-width {
  width: 60%;
  width: 50%;
  min-width: 300px;
}

.icon-length {
  width: 50%;
  margin: 0 auto;
  min-width: 300px;
  margin-top: 1rem;
}

.search-width {
  width: 40%;
  min-width: 300px;
  color: #000;
  font-size: 1.2rem;
}

.items-wrap {
  width: 80%;
}

</style>
