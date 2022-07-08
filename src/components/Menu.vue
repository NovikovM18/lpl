<template>
  <div class="menu">
    <ul class="menu__list">
      <a href="/" class="menu__item">
        <li>home</li>
      </a>
      <a href="/partners" class="menu__item">
        <li>our partners</li>
      </a>
      <a href="/team" class="menu__item">
        <li>our team</li>
      </a>
      <a href="/contacts" class="menu__item">
        <li>contact us</li>
      </a>
    </ul>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
  .menu {
    &__list {
      display: flex;
      list-style: none;
      gap: 10px;
      @media (max-width: 768px) {
        flex-direction: column;
      }
    }
    &__item {
      padding: 10px;
      text-decoration: none;
      font-weight: 400;
      font-size: 16px;
      line-height: 18px;
      text-transform: uppercase;
      color: #FFF;
      &:hover {
        text-decoration-line: underline;
      }
      @media (max-width: 768px) {
        font-weight: 700;
        font-size: 24px;
        line-height: 28px;
      }
    }
  }
</style>