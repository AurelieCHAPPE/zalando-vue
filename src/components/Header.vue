<script setup>
const props = defineProps({
  cart: {
    type: Array,
    required: true,
  },
})
</script>

<template>
  <header>
    <div class="header-top">
      <div class="container">
        <p>Essayer d'abord, <span>payez après</span></p>
        <p>LIVRAISON & <span>RETOUR GRATUITS *</span></p>
        <p>Retour et <span>remboursement</span></p>
      </div>
    </div>

    <div class="header-bottom">
      <div class="container">
        <nav>
          <a href="#">Femme</a>
          <a href="#">Homme</a>
          <a href="#">Enfant</a>
        </nav>
        <img src="../assets/img/logo.svg" alt="Logo zalando" />
        <nav>
          <p><font-awesome-icon :icon="['far', 'user']" /></p>
          <p><font-awesome-icon :icon="['far', 'heart']" /></p>
          <p><font-awesome-icon :icon="['fas', 'shopping-bag']" /></p>
          <p class="numOfProduct" v-if="cart.length > 0">{{ cart.length }}</p>
        </nav>
      </div>
    </div>
  </header>
</template>

<style scoped>
/* Header TOP */

.header-top {
  background-color: var(--light-grey);
}

.header-top .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: var(--header-top-height);
  font-size: 12px;
  color: var(--dark-grey);
}

span {
  color: var(--main-orange);
}

/* Header BOTTOM */

.header-bottom .container {
  height: var(--header-bottom-height);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav {
  display: flex;
  gap: 20px;
  flex: 1;
}

nav a {
  color: var(--main-black);
  gap: 10px;
  font-weight: bold;
  padding: 10px 15px;
}

nav a:first-child {
  color: white;
  background-color: var(--main-black);
}

nav:last-of-type {
  justify-content: flex-end;
  position: relative;
}

img {
  width: 155px;
  cursor: pointer;
}

svg {
  color: var(--main-black);
  padding: 10px;
  border: 2px solid white;
  cursor: pointer;
}

svg:hover {
  border-color: var(--main-black);
}

.numOfProduct {
  position: absolute;
  top: -2px;
  right: -2px;
  background-color: var(--main-orange);
  height: 20px;
  width: 20px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 14px;
}
</style>
