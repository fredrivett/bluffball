<template>
  <div id="app">
    <a href="https://twitter.com/intent/tweet?text=%20%23bluffball&source=webclient" target="_blank" class="c_bar">
      <p><strong>Already an armchair football pundit?</strong> Donate your twitter punditry by adding '#bluffball', we'll publish &amp; link to the best here</p>
    </a>
    <header class="section c_header">
      <div class="o_block o_block--large container">
        <div class="columns is-centered is-vcentered">
          <div class="section column o_block c_header__main">
            <div class="o_block o_block--small o_block--bottom">
              <h1 class="is-size-1 is-uppercase">Bluffball<span class="is-size-3">.io</span></h1>
            </div>
            <div class="o_block o_block--small o_block--bottom">
              <p class="is-size-5">Transform yourself into the armchair football<br class="is-hidden-mobile is-hidden-tablet-only"> pundit your friends seem to think they are</p>
            </div>
            <a href="https://www.youtube.com/watch?v=msN7HNncHik&feature=youtu.be&t=2m13s" target="_blank" class="is-size-5"><strong>What's Bluffball?</strong></a>
          </div>
          <div class="column is-hidden-mobile is-one-third-tablet is-one-quarter-desktop" style="padding-left: 60px;">
            <img src="./assets/bluffball.png" class="c_bluffball">
          </div>
        </div>
      </div>
    </header>

    <router-view/>

    <footer class="section">
      <div class="o_block o_block--large container c_footer">
        <div class="columns is-centered is-vcentered">
          <ul class="section column o_block c_header__main o_border-list">
            <li><a href="https://www.youtube.com/watch?v=msN7HNncHik&feature=youtu.be&t=2m13s" target="_blank">'Inspired' by some IT folks</a></li>
            <li><a href="https://www.flaticon.com/authors/freepik" target="_blank" rel="nofollow">Icons thanks to Freepik</a></li>
            <li><a href="https://www.producthunt.com/upcoming/the-dot" target="_blank" rel="nofollow">Brought to you by The Dot</a></li>
          </ul>
          <div class="column is-one-fifth-tablet is-one-sixth-desktop is-hidden-mobile" style="padding-left: 60px; max-width: 190px;">
            <a href="https://www.producthunt.com/upcoming/the-dot" class="c_thedot">
              <img src="./assets/thedot.png">
            </a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>


<style lang="scss">

$size-1: 5rem;

@import "../node_modules/bulma/bulma";


$white: #fefefe;
$grey: #eee;
$dark-grey: #333;

$green: #2ecc71;
$green-dark: #27ae60;
$green-darker: #288E51;

$twitter: #1da1f2;
$twitter-dark: #0079c3;
$facebook: #3b5998;



$font-mono: 'Nanum Gothic Coding', monospace;









/**
 * last-mb-0 mixin
 *
 * Remove the margin bottom from last children
 * 1) In some cases our children have specific margin-bottom (like .o_spacer)
 * so we only remove margin-bottom if *--mb-default is not applied (e.g.
 * o_block--mb-default).
 * 1a) Remove the margin-bottom from all of the last children
 * 1b) ...and remove margin-bottom from all last children inside of the last
 * column inside a row.
 */

@mixin last-mb-0 {
  &:not([class*="--mb-default"]) { /* [1] */
    & > *:last-child, /* [1a] */
    & > .columns:last-child > .column:last-child > *:last-child, /* [1b] */
    & > .container:last-child > .columns:last-child > .column:last-child > *:last-child { /* [1b] */
      margin-bottom: 0;
    }
  }
}









body {
  background-color: $green;
  min-height: 100vh;
  font-family: $font-mono;

  @include desktop {
    padding-top: 64px;
  }
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  overflow: hidden;
}





.container {
  @include tablet {
    padding-left: 40px;
    padding-right: 40px;
  }

  @include desktop {
    padding-left: 0;
    padding-right: 0;
  }
}





a {
  color: inherit;
  background-image: linear-gradient(to right, rgba($dark, 0.25) 0%, rgba($dark, 0.25) 100%);
  background-repeat: repeat-x; // make it horizontal
  background-position: 0 100%; // change the second value to adjust how far from the top the underline should be
  background-size: 100% 0.15em; // change the second value to the desired height of the underline
  text-decoration: none;

  &:hover, &:focus, &:active {
    text-decoration: none;
    background-image: linear-gradient(to right, rgba($dark, 0.5) 0%, rgba($dark, 0.5) 100%);
  }
}





.section {
  padding-top: 0;
  padding-bottom: 0;
}


.columns {
  margin-top: 0;
}





/**
 * Styling for layout object blocks
 */

.o_block {
  @include last-mb-0;
     padding-top: $size-4;
  padding-bottom: $size-4;

  @include tablet {
       padding-top: $size-3;
    padding-bottom: $size-3;
  }
}

.o_block--small {
     padding-top: $size-7;
  padding-bottom: $size-7;

  @include tablet {
       padding-top: $size-6;
    padding-bottom: $size-6;
  }
}

.o_block--large {
     padding-top: $size-2;
  padding-bottom: $size-2;

  @include tablet {
       padding-top: $size-1;
    padding-bottom: $size-1;
  }
}

.o_block--spacious {
     padding-top: $size-1 * 1.5;
  padding-bottom: $size-1 * 1.5;

  @include tablet {
       padding-top: $size-1 * 3;
    padding-bottom: $size-1 * 3;
  }
}

.o_block--top { padding-bottom: 0; }
.o_block--bottom { padding-top: 0; }















.o_border-list {
  & > * {
    display: inline-block;

    &:nth-last-child(n+2) {
      border-right: 1px solid currentColor;
      padding-right: 0.7em;
    }
  }
}









.c_bar {
  display: block;
  background: none;
  background-color: $green-dark;
  padding: 20px;
  color: $white;
  box-shadow: 5px 5px 0px 0px $green-darker;

  @at-root a#{&} {
    &:hover {
      background: none;
      background-color: $green-darker;
      color: $white;
    }
  }

  @include desktop {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 100;
  }
}


.c_footer {
  @include mobile {
    padding-right: 40px;
  }
}


.c_header {
  @include mobile {
    padding-right: 70px;
  }
}

  .c_header__main {
    position: relative;
    background-color: $green-dark;
    color: white;

    &, &::after {
      box-shadow: 10px 10px 0px 0px $green-darker;
    }

    &::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 100%;
      height: 30px;
      width: 30px;
      background-color: $green-dark;
    }
  }



.c_quote-block {
  position: relative;
  z-index: 0; // set context

  & > * {
    position: relative;
    z-index: 10;
  }

  &:nth-last-child(n+2) {
    margin-bottom: $size-2;
  }

  &, &::after {
    box-shadow: 10px 10px 0px 0px $green-darker;
  }

  &::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 100%;
    height: 30px;
    width: 30px;
    background-color: $white;
  }

  &:nth-child(even) {

    &::after {
      left: auto;
      right: 100%;
      z-index: -1;
    }
  }
}


.c_quote-block__inner {
  background-color: $white;
  padding-left: 40px;
  padding-right: 40px;
}

.c_quote-block__footer {
  display: flex;
  flex-direction: column;

  @include tablet {
    flex-direction: row;
  }
}

.c_quote-block__ctas,
.c_quote-block__meta {
  @include mobile {
    margin-bottom: $size-5;
  }
}

.c_quote-block__score {
  @include mobile {
    order: 4;
  }
}










.c_bluffball {}


.c_thedot {
  display: block;
  background: none;

  img {
    transition: all 0.25s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  }

  &:hover {
    background: none;

    img {
      transform: scale(1.2) rotate(-10deg);
      opacity: 0.9;
    }
  }
}



.c_flag {
  max-height: 30px;
  //box-shadow: 3px 3px 0px 0px rgba(0,0,0,0.25);
  //border: 1px solid rgba(0,0,0,0.1);
}



.c_score {
  display: inline-flex;
  align-items: center;

  & > *:nth-last-child(n+2) {
    margin-right: $size-7;
  }
}


  .c_score__result {
    font-weight: bold;
  }









.is-size-1 {
  line-height: 1;

  @include mobile {
    font-size: 2rem !important;
  }
}

@media screen and (min-width: 1088px) {
  .column.is-one-sixth-desktop {
    flex: none;
    width: 16.667%;
    }
}

@media screen and (min-width: 769px) and (max-width: 1279px) {
  .column.is-narrow-tablet-only {
    flex: none;
  }
}



.has-bg-grey {
  background-color: $grey !important;

  @at-root a#{&} {
    &:hover {
      background-color: $dark-grey !important;
      color: $white;
    }
  }
}


.has-bg-green-dark {
  background-color: $green-dark !important;
}


.has-bg-twitter {
  background-color: $twitter !important;
  color: white;

  &:hover {
    color: white;
    background-color: $twitter-dark !important;
  }
}


.has-bg-facebook {
  background-color: $facebook !important;
  color: white;

  &:hover {
    color: white;
    box-shadow: 3px 3px 0px 0px $dark-grey;
  }
}


.has-space-7 {
  padding: $size-7;
}

.has-space-tiny {
  padding: $size-7 / 1.5;
}

</style>
