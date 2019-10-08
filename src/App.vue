<template>
  <div id="app" class="container">
    <header class="header">
      <h1 class="header__logo">
        Clark
        <br>Design
        <br>System
      </h1>
      <h2 class="header__subtitle">{{this.$route.name}}</h2>
    </header>
    <nav class="navigation">
      <router-link class="link" to="/">Introduction</router-link>
      <router-link class="link" to="/nuancier">Nuancier</router-link>
      <router-link class="link" to="/typographie">Typographie</router-link>
      <router-link class="link" to="/iconographie">Iconographie</router-link>
      <button @click="dropDown" :class="menu ? 'dropdown--open' : ''" class="dropdown">Composants</button>
      <router-link
        :class="menu ? 'link--show' : ''"
        class="link link--hide"
        to="/formulaires"
      >Formulaires</router-link>
      <router-link :class="menu ? 'link--show' : ''" class="link link--hide" to="/boutons">Boutons</router-link>
      <router-link :class="menu ? 'link--show' : ''" class="link link--hide" to="/liens">Liens</router-link>
      <router-link :class="menu ? 'link--show' : ''" class="link link--hide" to="/fiches">Fiches</router-link>
      <router-link
        :class="menu ? 'link--show' : ''"
        class="link link--hide"
        to="/slideshows"
      >Slideshows</router-link>
    </nav>
    <main class="content">
      <transition name="fade" mode="out-in">
        <router-view></router-view>
      </transition>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "",
      menu: false
    };
  },
  methods: {
    dropDown: function() {
      this.menu = this.menu === false ? true : false;
    }
  }
};
</script>

<style lang="scss">
@import "assets/scss/app.scss";

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.dropdown {
  font-family: "IBM Plex Mono", "Courier New", Courier, monospace;
  color: $c-primary-middleOrange;
  background-color: transparent;
  border: 0;
  font-size: 1em;
  cursor: pointer;
  margin-left: rythm-unit(3);
  text-align: left;
  padding: 0;
  display: inline-flex;
  align-items: center;
  transition: color 250ms;
  margin-top: rythm-unit(1);
  margin-bottom: rythm-unit(1);
  outline: 0;
  &--acive {
    outline: 0;
  }

  &:focus {
    outline: 1px dashed $c-accent-darkPurple;
    border: 0;
    width: fit-content;
  }

  &::after {
    content: "";
    display: block;
    height: 12px;
    width: 12px;
    background-repeat: no-repeat;
    background-size: 9px;
    background-position: center;
    background-image: url(assets/icons/chevron-right.svg);
    margin-left: 0.707rem;
    transition: 250ms;
  }

  &:hover {
    color: $c-primary-brown;

    &::after {
      margin-left: 1rem;
      background-image: url(assets/icons/chevron-right-hover.svg);
    }
  }

  &--open {
    color: $c-primary-brown;
    &::after {
      transform: rotate(90deg);
      margin-left: 1rem;
      background-image: url(assets/icons/chevron-right-hover.svg);
    }
  }
}

.lineBreak {
  display: block;
}
.link--hide {
  opacity: 0;
  visibility: hidden;
  margin-left: rythm-unit(4);
  transition: opacity 250ms, visibility 250ms;
}
.link--show {
  opacity: 1;
  visibility: visible;
}
</style>
