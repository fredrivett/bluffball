<template>
  <div class="o_block container">
    <QuoteBlock
      quote="Dier was awful when he came on, but showed great composure for his penalty"
      team1="colombia"
      score="1-1"
      team2="england"
      byUsername="pacee"
      byTweet="https://twitter.com/TheKendallEnd/status/1014476653999869952"
      timestamp="1530735123"
    />

    <QuoteBlock
      quote="Colombia's antics were shocking"
      team1="colombia"
      score="1-1"
      team2="england"
      byUsername="pacee"
      byTweet="https://twitter.com/TheKendallEnd/status/1014476653999869952"
      timestamp="1530705123"
    />

    <QuoteBlock
      quote="England have just got to be better in the final third"
      team1="colombia"
      score="1-1"
      team2="england"
      byUsername="pacee"
      byTweet="https://twitter.com/TheKendallEnd/status/1014476653999869952"
      timestamp="1530635123"
    />
  </div>
</template>

<script>
  import QuoteBlock from '@/components/QuoteBlock';

  export default {
    name: 'Home',

    components: { QuoteBlock },
  }
</script>
