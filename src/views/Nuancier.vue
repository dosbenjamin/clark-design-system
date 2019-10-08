<template>
  <section class="section">
    <p>L'objectif du nuancier est de faire penser à une aventure dans le désert, un ajout de couleurs dérivées plus contrastantes et colorées évitent un nuancier trop pâle.</p>
    <div class="colors sideBySide">
      <div>
        <h3 class="title">Principales</h3>
        <ul class="colors__box">
          <li @click="copy" class="colors__item colors__item--orange"></li>
          <li class="colors__item colors__item--middleOrange"></li>
          <li class="colors__item colors__item--brown"></li>
        </ul>
      </div>
      <div>
        <h3 class="title">Accents</h3>
        <ul class="colors__box">
          <li class="colors__item colors__item--purple"></li>
          <li class="colors__item colors__item--darkPurple"></li>
        </ul>
      </div>
    </div>
    <small>Les couleurs principales et d'accentuations sont celles à utilisés dans la plupart des cas, ceux sont celles qui traduisent le mieux l'ambiance générale du site.</small>
    <div class="colors">
      <h3 class="title">Neutres</h3>
      <ul class="colors__box">
        <li class="colors__item colors__item--white"></li>
        <li class="colors__item colors__item--grey"></li>
        <li class="colors__item colors__item--darkGrey"></li>
        <li class="colors__item colors__item--black"></li>
      </ul>
    </div>
    <small>Les couleurs neutres sont utilisées pour du texte ou bien pour mettre en avant les couleurs principales et d'accentutations.</small>
    <div class="colors">
      <h3 class="title">Notifications</h3>
      <ul class="colors__box">
        <li class="colors__item colors__item--yellow"></li>
        <li class="colors__item colors__item--blue"></li>
        <li class="colors__item colors__item--green"></li>
        <li class="colors__item colors__item--red"></li>
      </ul>
    </div>
    <small>Les couleurs de notifications sont exclusivement réservées à une utilisation dans un formulaire.</small>
  </section>
</template>

<script>
export default {
  methods: {
    copy: function(e) {
      const item = e.target;
      const style = getComputedStyle(item);
      const color = style.backgroundColor;
      console.log(color);
      item.select();
      document.execCommand("copy");
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/app.scss";
p {
  margin-bottom: rythm-unit(2);
}
small {
  margin-top: rythm-unit(1);
  margin-bottom: rythm-unit(3);
}
.variables {
  background-color: $c-neutral-grey;
  padding: rythm-unit(1);
  width: 20%;
}
.colors {
  &:last-child {
    margin-top: rythm-unit(3);
  }
  &__box {
    margin-top: rythm-unit(1);
    display: flex;
  }
  &__item {
    height: rythm-unit(2);
    width: rythm-unit(2);
    &--orange {
      background-color: $c-primary-orange;
    }
    &--middleOrange {
      background-color: $c-primary-middleOrange;
    }
    &--brown {
      background-color: $c-primary-brown;
    }
    &--purple {
      background-color: $c-accent-purple;
    }
    &--darkPurple {
      background-color: $c-accent-darkPurple;
    }
    &--white {
      border: 1px solid $c-neutral-black;
    }
    &--grey {
      background-color: $c-neutral-grey;
    }
    &--darkGrey {
      background-color: $c-neutral-darkGrey;
    }
    &--black {
      background-color: $c-neutral-black;
    }
    &--yellow {
      background-color: $c-notif-yellow;
    }
    &--blue {
      background-color: $c-notif-blue;
    }
    &--green {
      background-color: $c-notif-green;
    }
    &--red {
      background-color: $c-notif-red;
    }
    &:first-of-type {
      border-radius: 5px 0 0 5px;
    }
    &:last-of-type {
      border-radius: 0 5px 5px 0;
    }
  }
}
</style>
