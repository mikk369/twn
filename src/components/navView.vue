<template>
  <nav class="navbar">
    <div class="navbar-toggle" id="mobile-menu">
      <span class="bar">--</span>
      <span class="bar">--</span>
      <span class="bar">--</span>
    </div>
  </nav>
</template>
<style>
/*  NAV STYLES */
nav {
  display: none;
}
@media (max-width: 960px) {
  nav {
    display: block;
    grid-column: 1 / 3;
  }
}
.bar {
  color: #3a3d57;
}
</style>
