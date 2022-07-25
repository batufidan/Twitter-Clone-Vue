<template>
  <q-page class="relative-position">
    <q-scroll-area class="absolute fullscreen">
      <div class="q-py-lg q-px-md row items-end q-col-gutter-md">
        <div class="col"></div>
        <div class="col"></div>

        <q-input
          v-model="newQweetContent"
          class="new-qweet"
          placeholder="What's happening?"
          maxlength="280"
          bottom-slots
          counter
          autogrow
        >
          <template v-slot:before>
            <q-avatar size="xl">
              <img src="https://avatars.githubusercontent.com/u/98849270?v=4" />
            </q-avatar>
          </template>
        </q-input>
      </div>
      <div class="col col-shrink">
        <q-btn
          @click="addNewTweet"
          :disable="!newTwitterContent"
          class="q-mb-lg"
          unelevated
          rounded
          color="primary"
          label="Tweet"
          no-caps
        />
      </div>
      <q-separator class="divider" size="10px" color="grey-2" />

      <q-list separator>
        <transition-group
          appear
          enter-active-class="animated fadeIn slow"
          leave-active-class="animated fadeOut slow"
        >
          <q-item v-for="tweet in tweets" :key="tweet.date" class="q-py-md">
            <q-item-section avatar top>
              <q-avatar size="xl">
                <img
                  src="https://avatars.githubusercontent.com/u/98849270?v=4"
                />
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label class="text-subtitle1">
                <strong>Batuhan Fidan</strong>
                <span class="text-grey-7"
                  >@batuhanfidan0 <br class="lt-md" />&bull; {{ tweet.date }}
                </span>
              </q-item-label>
              <q-item-label class="tweet-content text-body1"
                >{{ tweet.content }}
              </q-item-label>
              <div class="tweet-icons row justify-between q-mt-sm">
                <q-btn
                  color="grey"
                  icon="far fa-comment"
                  size="sm"
                  flat
                  round
                />
                <q-btn
                  color="grey"
                  icon="fas fa-retweet"
                  size="sm"
                  flat
                  round
                />
                <q-btn color="grey" icon="far fa-heart" size="sm" flat round />
                <q-btn
                  @click="deleteTweet(tweet)"
                  color="grey"
                  icon="fas fa-trash"
                  size="sm"
                  flat
                  round
                />
              </div>
            </q-item-section>

            <q-item-section side top>
              {{ tweet.date }}
            </q-item-section>
          </q-item>
        </transition-group>
      </q-list>
    </q-scroll-area>
  </q-page>
</template>

<script>
import { formatDistance, subDays } from "date-fns";

export default {
  name: "PageHome",
  data() {
    return {
      newTwitterContent: "",
      tweets: [
        {
          content:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatum inventore quod labore provident facere laudantium tempore impedit repellendus recusandae beatae excepturi tenetur necessitatibus quasi in numquam qui quis natus?",
          date: 1658756118119,
        },
        {
          content:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatum inventore quod labore provident facere laudantium tempore impedit repellendus recusandae beatae excepturi tenetur necessitatibus quasi in numquam qui quis natus?",
          date: 1658756166953,
        },
      ],
    };
  },
  methods: {
    addNewTweet() {
      let newTweet = {
        content: this.newTweetContent,
        date: Date.now(),
      };
      this.tweets.unshift(newTweet);
      this.newTweetContent = "";
    },
    deleteTweet(tweet) {
      let dateToDelete = tweet.date;
      let index = this.tweets.findIndex((tweet) => tweet.date === dateToDelete);
      console.log("index", index);
      this.tweets.splice(index, 1);
    },
  },
  filters: {
    relativeDate(value) {
      return formatDistance(subDays(new Date(), 3), new Date(), {
        addSuffix: true,
      });
    },
  },
};
</script>

<style lang="sass">
.new-tweet
  textarea
    font-size: 19px
    line-height: 1.4 !important
.divider
  border-top: 1px solid
  border-bottom: 1px solid
  border-color: $grey-4
.tweet:not(:first-child)
  border-top: 1px solid rgba(0, 0, 0, 0.12)
.tweet-content
  white-space: pre-line
.tweet-icons
  margin-left: -5px
</style>
