<template>
  <section class="section">
    <h3 class="title">champs de texte</h3>
    <span>Normal</span>
    <input class="input" type="text" placeholder="Votre texte">
    <span>Erreur</span>
    <input class="input input--error" type="text" placeholder="Votre texte">
    <span>Désactivé</span>
    <input disabled class="input input--disabled" type="text" placeholder="Votre texte">
    <h3 class="title">Notifications</h3>
    <ul class="notifications">
      <li class="notifications__item">
        <div class="notifications__icon"></div>
        <strong class="notifications__text">Validé&thinsp;! Votre e-mail a bien été...</strong>
        <button class="notifications__close">Fermer</button>
      </li>
      <li class="notifications__item notifications__item--yellow">
        <div class="notifications__icon notifications__icon--warning"></div>
        <strong class="notifications__text">Attention&thinsp;! Il se peut que...</strong>
        <button class="notifications__close">Fermer</button>
      </li>
      <li class="notifications__item notifications__item--red">
        <div class="notifications__icon notifications__icon--error"></div>
        <strong class="notifications__text">Erreur&thinsp;! Un problème est survenu...</strong>
        <button class="notifications__close">Fermer</button>
      </li>
      <li class="notifications__item notifications__item--blue">
        <div class="notifications__icon notifications__icon--info"></div>
        <strong class="notifications__text">Info&thinsp;! Depuis le 4 avril 2017...</strong>
        <button class="notifications__close">Fermer</button>
      </li>
    </ul>
    <small>
      Les notifications sont utilisés pour informer les utilisateurs après avoir cliquer sur le bouton de confirmation.
      Ces composants sont uniquemenet utilisés dans ces cas là.
    </small>
  </section>
</template>
<script>
export default {
  data() {
    return {
      name: "Formulaires"
    };
  },
  created() {
    this.$parent.menu = true;
  }
};
</script>
<style lang="scss" scoped>
@import "../assets/scss/app.scss";

span {
  display: block;
}

.title {
  margin-bottom: rythm-unit(1);
  :last-of-type {
    margin-top: rythm-unit(3);
  }
}
.notifications {
  display: flex;
  flex-wrap: wrap;
  max-width: 80%;
  &__icon {
    background-image: url(../assets/icons/valid.svg);
    background-size: 100%;
    background-position: center;
    background-repeat: no-repeat;
    margin-right: rythm-unit(1);
    height: 40px;
    width: 40px;
    &--warning {
      background-image: url(../assets/icons/warning.svg);
    }
    &--info {
      background-image: url(../assets/icons/info.svg);
    }
    &--error {
      background-image: url(../assets/icons/error.svg);
    }
  }
  &__close {
    background-image: url(../assets/icons/close.svg);
    border: 0;
    padding: 0;
    margin: 0;
    outline: 0;
    background-color: transparent;
    height: 13px;
    width: 13px;
    background-size: 100%;
    text-indent: 100%;
    white-space: nowrap;
    overflow: hidden;
    cursor: pointer;
    position: absolute;
    top: rythm-unit(0.5);
    right: rythm-unit(0.5);
  }
  &__item {
    padding: rythm-unit(0.5) rythm-unit(1);
    background-color: $c-notif-green;
    border-radius: 5px;
    margin-right: rythm-unit(2);
    margin-bottom: rythm-unit(1);
    color: #fff;
    display: flex;
    align-items: center;
    position: relative;
    &--yellow {
      background-color: $c-notif-yellow;
      color: $c-neutral-black;
      .notifications__close {
        background-image: url(../assets/icons/close-black.svg);
      }
    }
    &--red {
      background-color: $c-notif-red;
    }
    &--blue {
      background-color: $c-notif-blue;
    }
  }
  &__text {
    font-weight: 400;
    margin-right: rythm-unit(3);
  }
}

.input {
  border-radius: 5px;
  background-color: $c-neutral-grey;
  outline: 0;
  border: 0;
  margin-top: rythm-unit(1);
  padding: rythm-unit(0.5) rythm-unit(4) rythm-unit(0.5) rythm-unit(1);
  box-sizing: border-box;
  border: 1px solid $c-neutral-grey;
  margin-bottom: rythm-unit(1);
  &:last-of-type {
    margin-bottom: rythm-unit(3);
  }
  &::placeholder {
    color: $c-neutral-darkGrey;
  }
  &:focus {
    border: 1px solid $c-neutral-darkGrey;
  }
  &--error {
    border-color: $c-notif-red;
    &:focus {
      border-color: $c-notif-red;
    }
  }
  &--disabled {
    cursor: not-allowed;
    &:focus {
      border: 1px solid $c-neutral-grey;
    }
  }
}
</style>

