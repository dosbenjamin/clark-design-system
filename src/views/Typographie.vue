<template>
  <section class="section">
    <div class="typography">
      <h3 class="title">mobile</h3>
      <ul class="typography__row">
        <li class="typography__item">
          <span class="typography__title typography__title1 typography__title1--mobile">Titre 1</span>
          <small>Inknut Antiqua - Regular/400 - 45,23 Pixels - 120%</small>
        </li>
        <li class="typography__item">
          <span class="typography__title typography__title2 typography__title2--mobile">Titre 2</span>
          <small>Inknut Antiqua - Regular/400 - 31,99 Pixels - 120%</small>
        </li>
        <li class="typography__item">
          <span class="typography__title typography__title3 typography__title3--mobile">Titre 3</span>
          <small>IBM Plex Mono - Bold/500 - 16 Pixels - 120%</small>
        </li>
        <li class="typography__item">
          <span class="typography__body">Corps</span>
          <small>IBM Plex Mono - Regular/400 - 16 Pixels - 150%</small>
        </li>
        <li class="typography__item">
          <span class="typography__small">Small</span>
          <small>IBM Plex Mono - Regular/400 - 11,32 Pixels - 136%</small>
        </li>
      </ul>
    </div>
    <div class="typography">
      <h3 class="title">tablette</h3>
      <ul class="typography__row">
        <li class="typography__item">
          <span class="typography__title typography__title1 typography__title1--tablette">Titre 1</span>
          <small>Inknut Antiqua - Regular/400 - 63,96 Pixels - 120%</small>
        </li>
        <li class="typography__item">
          <span class="typography__title typography__title2 typography__title2--mobile">Titre 2</span>
          <small>Inknut Antiqua - Regular/400 - 31,99 Pixels - 120%</small>
        </li>
        <li class="typography__item">
          <span class="typography__title typography__title3 typography__title3--mobile">Titre 3</span>
          <small>IBM Plex Mono - Bold/500 - 16 Pixels - 120%</small>
        </li>
        <li class="typography__item">
          <span class="typography__body">Corps</span>
          <small>IBM Plex Mono - Regular/400 - 16 Pixels - 150%</small>
        </li>
        <li class="typography__item">
          <span class="typography__small">Small</span>
          <small>IBM Plex Mono - Regular/400 - 11,32 Pixels - 136%</small>
        </li>
      </ul>
    </div>
    <div class="typography">
      <h3 class="title">desktop</h3>
      <ul class="typography__row">
        <li class="typography__item">
          <span class="typography__title typography__title1 typography__title1--desktop">Titre 1</span>
          <small>Inknut Antiqua - Regular/400 - 71,96 Pixels - 120%</small>
        </li>
        <li class="typography__item">
          <span class="typography__title typography__title2 typography__title2--desktop">Titre 2</span>
          <small>Inknut Antiqua - Regular/400 - 35,99 Pixels - 120%</small>
        </li>
        <li class="typography__item">
          <span class="typography__title typography__title3 typography__title3--desktop">Titre 3</span>
          <small>IBM Plex Mono - Bold/500 - 18 Pixels - 120%</small>
        </li>
        <li class="typography__item">
          <span>Corps</span>
          <small>IBM Plex Mono - Regular/400 - 18 Pixels - 150%</small>
        </li>
        <li class="typography__item">
          <small>Small</small>
          <small>IBM Plex Mono - Regular/400 - 12,73 Pixels - 136%</small>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  created() {
    this.$parent.menu = false;
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/app.scss";
.typography {
  margin-bottom: rythm-unit(3);
  &__row {
    margin-top: rythm-unit(1);
  }
  &__item {
    margin-bottom: rythm-unit(1);
  }
  &__title {
    font-family: "Inknut Antiqua", "Times New Roman", Times, serif;
    line-height: 1.2;
    &1--mobile {
      font-size: 45.23px;
    }
    &1--tablette {
      font-size: 63.96px;
    }
    &2--mobile {
      font-size: 31.99px;
    }
    &2--desktop {
      font-size: 35.99px;
    }
    &1--desktop {
      font-size: 71.96px;
    }
    &3 {
      font-family: "IBM Plex Mono", "Courier New", Courier, monospace;
      text-transform: uppercase;
      letter-spacing: 1px;
      font-weight: 700;
      &--mobile {
        font-size: 16px;
      }
    }
  }
  &__body {
    font-size: 16px;
  }
  &__small {
    font-size: 11.32px;
    line-height: 1.36;
  }
}
</style>

