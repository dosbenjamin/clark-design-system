<template>
  <section class="section">
    <p>Les boutons sont utilisés pour effectuer une action, ils sont utiles pour appeller l'utilisateur à effectuer des intéractions autres que pour la navigation.</p>
    <div class="buttons">
      <h3 class="title">Type 1</h3>
      <button class="button">Bouton</button>
      <button class="button button--disabled">Désactivé</button>
      <small>Les boutons de type 1 sont utilisés lorsqu'ils s'agit d'une action principale du site.</small>
    </div>
    <h3 class="title">Type 2</h3>
    <button class="button button--small">Bouton</button>
    <button class="button button--small button--disabled">Désactivé</button>
    <small>Les boutons de type 2 sont utilisés pour des actions secondaires et dans des zones restreintes.</small>
  </section>
</template>

<style lang="scss" scoped>
@import "../assets/scss/app.scss";

p {
  margin-top: 0;
  margin-bottom: rythm-unit(2);
}

small {
  margin-top: rythm-unit(1);
  display: block;
}

.title {
  margin-bottom: rythm-unit(1);
}
.buttons {
  margin-bottom: rythm-unit(3);
}
.button {
  height: rythm-unit(2);
  color: #fff;
  background-color: $c-accent-purple;
  padding: 0 rythm-unit(1);
  border: 0;
  border-radius: 5px;
  cursor: pointer;
  transition: 250ms;
  &:hover {
    background-color: $c-accent-darkPurple;
  }
  &:focus {
    outline: 2px dashed $c-accent-purple;
    border-radius: 5px;
  }
  &:active  {
    outline: 2px dashed $c-accent-purple;
    border-radius: 5px;
  }
  &--disabled {
    background-color: $c-neutral-darkGrey;
    margin-left: rythm-unit(2);
    cursor: not-allowed;
    &:hover {
      background-color: $c-neutral-darkGrey;
    }
  }
  &--small {
    height: rythm-unit(1);
    font-size: 0.707em;
  }
}
</style>

