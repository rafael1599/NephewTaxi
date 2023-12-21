<template>
  <v-app>
    <v-app-bar
      elevation="0"
      :height="isMobile ? 80 : 126"
      color="transparent"
      absolute>
      <v-spacer v-if="isMobile"></v-spacer>
      <img src="@/assets/svg/logo-va.svg" :height="isMobile ? '70px' : '100px'" @click="goTo()"/>
      <v-spacer></v-spacer>
      <div class="d-flex align-center" style="gap: 32px;" v-if="!isMobile">
        <v-btn
          class="links"
          height="60"
          elevation="0">
          Reserve
        </v-btn>
        <v-btn
          class="links"
          height="60"
          elevation="0"
          href="#new-rochelle">
          New Rochelle
        </v-btn>
        <v-btn
          class="links"
          height="60"
          elevation="0"
          href="#westchester">
          Westchester
        </v-btn>
        <v-btn
          class="links"
          height="60"
          elevation="0"
          href="#long-distance">
          Long Distance
        </v-btn>
        <v-btn
          class="links"
          height="60"
          elevation="0"
          href="#to-the-airport">
          To The Airport
        </v-btn>
      </div>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" v-else color="white"></v-app-bar-nav-icon>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" absolute right style="z-index: 1000;">
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="warning--text text--accent-4">
          <v-list-item href="#new-rochelle" @click="drawer = false">
            <v-list-item-title>New Rochelle</v-list-item-title>
          </v-list-item>
          <v-list-item href="#westchester" @click="drawer = false">
            <v-list-item-title>Westchester</v-list-item-title>
          </v-list-item>
          <v-list-item href="#long-distance" @click="drawer = false">
            <v-list-item-title>Long Distance</v-list-item-title>
          </v-list-item>
          <v-list-item href="#to-the-airport" @click="drawer = false">
            <v-list-item-title>To The Airport</v-list-item-title>
          </v-list-item>
          <v-list-item href="#contact" @click="drawer = false">
            <v-list-item-title>Contact</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <Nuxt />
    </v-main>
    <v-footer 
      id="contact"
      color="rgb(224, 220, 0)"
      class="d-flex flex-column py-4"
      style="gap: 8px">
      <span>CONTACT</span>
      <a href="tel: (914)564-0279">(914) 564-0279</a>
      <a href="mailto: VandAtaxi@gmail.com">VandAtaxi@gmail.com</a>
    </v-footer>
  </v-app>
</template>

<script>
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'DefaultLayout',
  data () {
    return {
      drawer: false,
      group: null
    }
  },
  watch: {
    "$vuetify.breakpoint.name"(val){
      this.validateSize(val)
    }
  },
  computed: {
    ...mapState("vuetify", ['isMobile'])
  },
  methods: {
    ...mapMutations("vuetify", ['SET_IS_MOBILE', 'SET_BREAKPOINT']),
    validateSize(param){
      if(['xs','sm','md'].includes(param)){
        this.SET_IS_MOBILE(true)
      }else{
        this.SET_IS_MOBILE(false)
      }
      this.SET_BREAKPOINT(this.$vuetify.breakpoint.name)
    },
    goTo(){
      window.scroll({
        top: 0,
        left: 0,
        behavior: "smooth",
      })
    }
  },
  mounted() {
    this.validateSize(this.$vuetify.breakpoint.name)
  }
}
</script>

<style lang="scss">
body{
  overflow: hidden;
}
.v-main{
  background-image: url("@/assets/img/taxi.png");
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
}
.v-toolbar__content{
  padding-left: 48px;
  padding-right: 48px;
  .v-app-bar-title{
    img{
      margin-top: 1rem;
    }
  }
  .links{
    text-transform: none;
    background-color: transparent !important;
    color: #ffffff;
  }
}
.v-footer{
  span, a{
    font-weight: 700;
    color: #000000;
  }
}

@media (max-width: 450px) {
  .v-app-bar{
    width: 100%;
    .v-toolbar__content{
      width: 100%;
      padding: 0px 32px;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      .v-app-bar-title{
        width: 100%;
        &__content{
          max-width: 100%;
        }
      }
    }
  }
}
</style>
