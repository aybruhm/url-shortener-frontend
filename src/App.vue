<template>
  <router-view />
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');

* {
  margin: 0px;
  padding: 0px;
}

html,
body {
  font-family: 'Poppins', sans-serif;
}

h4.main-subtitle {
  font-style: normal;
  font-weight: 500;
  font-size: 24px;
  margin-top: 0%;
  padding-top: 0%;
  line-height: 40px;
  letter-spacing: 0.065em;
  color: #000000;
}

@media screen and (max-width: 489px) {
  h4.main-subtitle {
    font-size: 18px;
  }
}
</style>
