<template>
  <q-layout view="lHr lpR fFf">
    <q-header bordered class="bg-white text-black">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="left = !left" />

        <q-toolbar-title class="text-weight-bold">
          <span class="gt-sm">{{ $route.name }} </span>
          <q-icon
            class="header-icon q-pa-md lt-md"
            name="fas fa-dove"
            size="sm"
            color="primary"
          />
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer
      show-if-above
      v-model="leftDrawerOpen"
      side="left"
      :width="283"
      bordered
    >
      <q-icon
        class="q-pl-xl q-py-md"
        name="fas fa-dove"
        size="xl"
        color="primary"
      />

      <q-list class="q-px-lg">
        <q-item to="/" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon name="home" size="md" />
          </q-item-section>

          <q-item-section class="text-h6 text-weight-bolder"
            >Home</q-item-section
          >
        </q-item>

        <q-item to="/about" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon name="explore" size="md" />
          </q-item-section>

          <q-item-section class="text-h6 text-weight-bolder"
            >Explore</q-item-section
          >
        </q-item>

        <q-item to="/about" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon name="notifications" size="md" />
          </q-item-section>

          <q-item-section class="text-h6 text-weight-bolder"
            >Notifications</q-item-section
          >
        </q-item>

        <q-item to="/about" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon class="q-pl-md" name="messages" size="md" />
          </q-item-section>

          <q-item-section class="text-h6 text-weight-bolder"
            >Messages</q-item-section
          >
        </q-item>

        <q-item to="/about" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon name="bookmarks" size="md" />
          </q-item-section>

          <q-item-section class="text-h6 text-weight-bolder"
            >Bookmarks</q-item-section
          >
        </q-item>

        <q-item to="/about" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon class="q-pl-md" name="lists" size="md" />
          </q-item-section>

          <q-item-section class="text-h6 text-weight-bolder q-pr-xl"
            >Lists</q-item-section
          >
        </q-item>

        <q-item to="/about" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon name="person" size="md" />
          </q-item-section>

          <q-item-section class="text-h6 text-weight-bolder"
            >Profile</q-item-section
          >
        </q-item>

        <q-item to="/about" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon name="help" size="md" />
          </q-item-section>

          <q-item-section class="text-h6 text-weight-bolder"
            >Help</q-item-section
          >
        </q-item>

        <div class="col col-shrink q-pa-md">
          <q-btn
            size="20px"
            class="q-pr-md"
            unelevated
            rounded
            color="primary"
            label="Tweet"
          />
        </div>
        <div class="name-and-photo q-pa-md">
          <q-avatar size="xl">
            <img src="https://avatars.githubusercontent.com/u/98849270?v=4" />
          </q-avatar>
          <div class="profile-name">
            <strong class="text-h6">Batuhan Fidan</strong>
            <span class="text-grey-7">@batuhanfidan0 </span>
          </div>
        </div>
      </q-list>
    </q-drawer>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
      <q-input
        type="text"
        value="button"
        placeholder="Search Twitter"
        outlined
        rounded
        class="search-input q-ma-md"
        dense
      >
        <template v-slot:prepend>
          <q-icon name="search" />
        </template>
      </q-input>

      <div class="search-box q-ma-md q-mt-lg">
        <div class="trend-topic-box">
          <span>
            <strong class="trends-text">Trends For You</strong>
          </span>
          <div class="trend-topic-subtitle">
            <div class="trend-topic-subtitlee">
              <q-item-label overline class="first-trend text-grey-8 q-ma-md"
                >Trending</q-item-label
              >
              <strong class="first-title q-ma-md">VueJS</strong>
              <q-item-label overline class="first-tweet text-grey-8 q-ma-md"
                >10.3k Tweets</q-item-label
              >
            </div>
          </div>
          <div class="trend-topic-subtitle">
            <div class="trend-topic-subtitlee">
              <q-item-label overline class="first-trend text-grey-8 q-ma-md"
                >Trending</q-item-label
              >
              <strong class="first-title q-ma-md">ReactJS</strong>
              <q-item-label overline class="first-tweet text-grey-8 q-ma-md"
                >10.3k Tweets</q-item-label
              >
            </div>
          </div>
          <div class="trend-topic-subtitle">
            <div class="trend-topic-subtitlee">
              <q-item-label overline class="first-trend text-grey-8 q-ma-md"
                >Trending</q-item-label
              >
              <strong class="first-title q-ma-md">Redux</strong>
              <q-item-label overline class="first-tweet text-grey-8 q-ma-md"
                >10.3k Tweets</q-item-label
              >
            </div>
          </div>
          <div class="trend-topic-subtitle">
            <div class="trend-topic-subtitlee">
              <q-item-label overline class="first-trend text-grey-8 q-ma-md"
                >Trending</q-item-label
              >
              <strong class="first-title q-ma-md">Bootstrap</strong>
              <q-item-label overline class="first-tweet text-grey-8 q-ma-md"
                >10.3k Tweets</q-item-label
              >
            </div>
          </div>
          <div class="trend-topic-subtitle">
            <div class="trend-topic-subtitlee">
              <q-item-label overline class="first-trend text-grey-8 q-ma-md"
                >Trending</q-item-label
              >
              <strong class="first-title q-ma-md">Front-end</strong>
              <q-item-label overline class="first-tweet text-grey-8 q-ma-md"
                >10.3k Tweets</q-item-label
              >
            </div>
          </div>
          <div class="trend-topic-subtitle">
            <div class="trend-topic-subtitlee">
              <q-item-label overline class="first-trend text-grey-8 q-ma-md"
                >Trending</q-item-label
              >
              <strong class="first-title q-ma-md">Back-end</strong>
              <q-item-label overline class="first-tweet text-grey-8 q-ma-md"
                >10.3k Tweets</q-item-label
              >
            </div>
          </div>
        </div>
      </div>

      <q-list separator padding>
        <q-item class="q-pa-md">
          <q-item-section>
            <q-item-label overline class="text-grey">Education</q-item-label>
            <q-item-label class="text-weight-bold"
              >Something amazing happened!</q-item-label
            >
            <q-item-label caption
              >Secondary line text. Lorem ipsum dolor sit amet, consectetur
              adipiscit elit.</q-item-label
            >
          </q-item-section>

          <q-item-section side top>
            <q-item-label caption>5 min ago</q-item-label>
          </q-item-section>
        </q-item>

        <q-item class="q-pa-md">
          <q-item-section>
            <q-item-label overline class="text-grey">Education</q-item-label>
            <q-item-label class="text-weight-bold"
              >Something amazing happened!</q-item-label
            >
            <q-item-label caption
              >Secondary line text. Lorem ipsum dolor sit amet, consectetur
              adipiscit elit.</q-item-label
            >
          </q-item-section>

          <q-item-section side top>
            <q-item-label caption>5 min ago</q-item-label>
          </q-item-section>
        </q-item>

        <q-item class="q-pa-md">
          <q-item-section>
            <q-item-label overline class="text-grey">Education</q-item-label>
            <q-item-label class="text-weight-bold"
              >Something amazing happened!</q-item-label
            >
            <q-item-label caption
              >Secondary line text. Lorem ipsum dolor sit amet, consectetur
              adipiscit elit.</q-item-label
            >
          </q-item-section>

          <q-item-section side top>
            <q-item-label caption>5 min ago</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const leftDrawerOpen = ref(false);
    const rightDrawerOpen = ref(false);

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },

      rightDrawerOpen,
      toggleRightDrawer() {
        rightDrawerOpen.value = !rightDrawerOpen.value;
      },
    };
  },
};
</script>

<style lang="sass">
.header-icon
  position: absolute
  bottom: 0
  left: 50%
  transform: translateX(-50%)
.name-and-photo
  display: flex
  gap: 1rem
.profile-name
  display: grid
.search-input
  background-color : #F5F8FA
  border-radius: 25px
.search-box
  height: 620px
  border-radius: 25px
  background-color: #F5F8FA
.trend-topic-subtitle
  line-height: .2 !important
  display: flex
  justify-content: space-between
.trends-text
  padding: 15px
  font-size: 20px
.first-trend
  font-size: 12px
.first-title
  font-size: 18px
</style>
