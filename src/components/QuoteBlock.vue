<template>
  <div class="c_quote-block">
    <div class="section o_block c_quote-block__inner">
      <div class="columns is-centered">
        <div class="o_block o_block--small o_block--top">
          <div class="column o_block o_block--bottom is-size-4">
            <p>&quot;{{ quote }}&quot;</p>
          </div>
        </div>
      </div>
      <div class="columns c_quote-block__footer">
        <div class="column is-size-6 c_quote-block__score has-text-left-tablet has-text-left-desktop is-paddingless is-narrow-mobile is-narrow-tablet-only">
          <span class="has-space-tiny c_score">
            <img :src="team1Image" class="c_flag c_score__flag is-block" v-if="team1Image">
            <span class="c_score__result">{{ score }}</span>
            <img :src="team2Image" class="c_flag c_score__flag is-block">
          </span>
        </div>
        <div class="column is-size-6 is-paddingless c_quote-block__ctas">
          <a :href="'https://twitter.com/intent/tweet?text=' + quote + '&source=webclient'" target="_blank" class="has-bg-twitter has-space-7 is-inline-block">
            tweet this bluff
          </a>
        </div>
        <div class="column is-size-6 c_quote-block__meta has-text-left-tablet has-text-right-desktop is-paddingless is-narrow-mobile is-narrow-tablet-only">
          <span class="has-bg-grey has-space-7 is-inline-block" v-if="!byTweet && byUsername">
            submitted by: @{{ byUsername }}
          </span>
          <a :href="byTweet" target="_blank" class="has-bg-grey has-space-7 is-inline-block" v-else-if="byUsername">
            submitted by: @{{ byUsername }}
          </a>
          <span class="has-bg-grey has-space-7 is-inline-block" v-if="timestamp">
            {{ timeago(timestamp) }}
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'QuoteBlock',

    data() {
      return {
        team1Image: require('../assets/flags/' + this.team1 + '.png'),
        team2Image: require('../assets/flags/' + this.team2 + '.png'),
      }
    },

    props: [
      'quote',
      'team1',
      'score',
      'team2',
      'byUsername',
      'byTweet',
      'timestamp',
    ],

    methods: {
      timeago(timestamp) {
        return moment.unix(timestamp).fromNow();
      },
    }
  }
</script>
