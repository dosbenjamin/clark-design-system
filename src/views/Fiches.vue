<template>
  <section class="section">
    <div @click="cardOpen" :class="this.isOpen === true ? 'card--open' : ''" class="card">
      <div class="card__image"></div>
      <div class="card__container">
        <span class="card__title">Titre</span>
        <button class="card__button">Ouvrir</button>
        <p>Lorem ipsum dolor sit amet.</p>
        <button class="button">Bouton</button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    };
  },
  methods: {
    cardOpen: function() {
      this.isOpen = this.isOpen === false ? true : false;
      console.log(this.isOpen);
    }
  }
};
</script>

<style lang="scss" scope>
@import "../assets/scss/app.scss";

.card {
  border-radius: 5px;
  background-color: $c-primary-orange;
  display: inline-flex;
  align-items: center;
  cursor: pointer;
  &__image {
    height: rythm-unit(3);
    width: rythm-unit(3);
    border-radius: 5px 0 0 5px;
    background-color: $c-neutral-grey;
    margin-right: rythm-unit(2);
  }
  &__title {
    color: $c-primary-middleOrange;
    margin-right: rythm-unit(1);
    margin-top: rythm-unit(1);
    margin-bottom: rythm-unit(1);
    transition: color 250ms;
  }
  &__button {
    background-image: url(../assets/icons/chevron-right.svg);
    background-repeat: no-repeat;
    background-position: center;
    background-size: 9px;
    outline: 0;
    border: 0;
    background-color: transparent;
    height: 12px;
    width: 12px;
    overflow: hidden;
    white-space: nowrap;
    text-indent: 9999px;
    margin-right: rythm-unit(2);
    transition: 250ms;
  }
  &:hover {
    .card__title {
      color: $c-primary-brown;
    }
    .card__button {
      transform: translateX(rythm-unit(0.5));
      background-image: url(../assets/icons/chevron-right-hover.svg);
    }
  }
  .button {
    display: none;
  }
  p {
    display: none;
  }
  &--open {
    flex-direction: column;
    position: relative;
    .card__image {
      width: rythm-unit(12);
      height: rythm-unit(7);
      margin: 0;
    }
    .card__title {
      text-transform: uppercase;
      color: $c-neutral-black;
      font-weight: 700;
      letter-spacing: 1px;
    }
    .card__button {
      position: absolute;
      top: 0;
      right: 0;
      z-index: 2;
      margin: 0;
    }
    .button {
      display: block;
    }
    p {
      display: block;
    }
  }
}
</style>
