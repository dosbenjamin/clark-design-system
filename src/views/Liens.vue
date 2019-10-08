<template>
  <section class="section">
    <p>Les liens permettent la navigation entre les différentes pages du site mais aussi pour se rendre sur des pages externes.</p>
    <h3 class="title">liens classiques</h3>
    <a class="link">Je suis un lien</a>
    <small>Les liens classiques sont à priviliégiés pour la navigation.</small>
    <h3 class="title">dropdown menu</h3>
    <bouton
      @click="dropdownMenuOpen"
      :class="menu ? 'dropdown--open' : ''"
      class="dropdown"
    >Dropdown menu</bouton>
    <ul :class="menu ? 'dropdownMenu--open' : ''" class="dropdownMenu">
      <li>
        <a class="link">Premier lien</a>
      </li>
      <li>
        <a class="link">Deuxième lien</a>
      </li>
      <li>
        <a class="link">Troisième lien</a>
      </li>
    </ul>
    <small>Le dropdown menu est utilisé dans les cas de navigation où plusieurs pages traitents du même aspect général et divisé en sous catégories.</small>
  </section>
</template>
<script>
export default {
  data() {
    return {
      menu: false
    };
  },
  methods: {
    dropdownMenuOpen: function() {
      this.menu = this.menu === false ? true : false;
    }
  }
};
</script>
<style lang="scss" scoped>
@import "../assets/scss/app.scss";
.link {
  display: inline-block;
  margin: rythm-unit(1) 0;
  cursor: pointer;
  &::after {
    width: 30%;
  }
}
p {
  margin-bottom: rythm-unit(2);
}
small {
  margin-bottom: rythm-unit(3);
  display: block;
}
small:last-child {
  margin-top: rythm-unit(1);
}
.dropdown {
  margin-left: 0;
}
.dropdownMenu {
  background-color: $c-neutral-grey;
  visibility: hidden;
  opacity: 0;
  width: fit-content;
  border-radius: 5px;
  padding: rythm-unit(2) rythm-unit(1.5) rythm-unit(1);
  margin-left: rythm-unit(1);
  transition: 250ms;
  &--open {
    opacity: 1;
    visibility: visible;
  }
  .link {
    margin-top: 0;
  }
}
</style>
