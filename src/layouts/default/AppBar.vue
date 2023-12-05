<template>
  <v-img
    src="https://www.biletdukkani.com/content/product-images/landingpage.webp"
  ></v-img>
  <v-app-bar :elevation="0" :color="bg" class="animated-navbar">
    <v-container class="pa-0 fill-height">
      <div>
        <a href="#" title="BiletDükkanı"
          ><v-img height="29" width="161" :src="logo"></v-img
        ></a>
      </div>
      <nav class="d-flex align-center navbar-header pl-4 pl-lg-7">
        <div>
          <a
            class="nav-item rounded-medium mr-1 px-2"
            href="#"
            :style="{ color: navbarItemsColor }"
          >
            <span><v-icon>mdi-airplane</v-icon>Uçak</span>
          </a>
        </div>
        <div>
          <a
            class="nav-item rounded-medium mr-1 px-2"
            href="#"
            :style="{ color: navbarItemsColor }"
          >
            <span><v-icon>mdi-bed</v-icon>Otel</span>
          </a>
        </div>
        <div>
          <a
            class="nav-item rounded-medium mr-1 px-2"
            href="#"
            :style="{ color: navbarItemsColor }"
          >
            <span><v-icon>mdi-bus</v-icon>Otobüs</span>
          </a>
        </div>
        <div>
          <a
            class="nav-item rounded-medium mr-1 px-2"
            href="#"
            :style="{ color: navbarItemsColor }"
          >
            <span><v-icon>mdi-car</v-icon>Araç</span>
          </a>
        </div>
        <div>
          <a
            class="nav-item rounded-medium mr-1 px-2"
            href="#"
            :style="{ color: navbarItemsColor }"
          >
            <span><v-icon>mdi-van-passenger</v-icon>Transfer</span>
          </a>
        </div>
      </nav>
      <v-spacer></v-spacer>
      <div>
        <a id="agenty" class="rounded-medium mr-1 px-2" href="#">
          <span><v-icon>mdi-home</v-icon>Acente</span>
        </a>
      </div>
      <div>
        <v-select
          class="rounded-medium mr-1 px-2"
          :items="['Türkçe', 'English']"
        ></v-select>
      </div>
      <div>
        <a
          class="nav-item rounded-medium mr-1 px-2"
          href="#"
          :style="{ color: navbarItemsColor }"
        >
          <span>Üye Ol</span>
        </a>
      </div>
      <div>
        <a
          class="nav-item rounded-medium mr-1 px-2"
          href="#"
          :style="{ color: navbarItemsColor }"
        >
          <span>Giriş Yap</span>
        </a>
      </div>
    </v-container>
  </v-app-bar>
</template>

<script>
export default {
  data: () => ({
    bg: "transparent",
    logo: "https://www.biletdukkani.com/_nuxt/img/biletdukkani-logo-white.7b13bb7.svg",
    navbarItemsColor: "white",
  }),
  mounted() {
    this.changeColor();
    window.addEventListener("scroll", this.changeColor);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.changeColor);
  },
  methods: {
    changeColor() {
      if (window.scrollY > 0) {
        this.bg = "white";
        this.logo =
          "https://www.biletdukkani.com/_nuxt/img/biletdukkani-logo.7a1b601.svg";
        this.navbarItemsColor = "black";
      } else {
        this.bg = "transparent";
        this.logo =
          "https://www.biletdukkani.com/_nuxt/img/biletdukkani-logo-white.7b13bb7.svg";
        this.navbarItemsColor = "white";
      }
    },
  },
};
</script>
<style scoped>
.animated-navbar {
  transition: background-color 0.3s ease;
}

.nav-item {
  padding: 0.3rem;
  border-radius: 10px;
  text-decoration: none;
  border: 1px solid transparent;
}

.nav-item:hover {
  background: hsla(0, 0%, 100%, 0.2);
}

#agenty {
  padding: 0.3rem;
  border-radius: 10px;
  text-decoration: none;
  background-color: white;
  color: blue;
}
</style>
