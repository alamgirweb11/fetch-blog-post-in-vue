<template>
  <div>
  <b-navbar toggleable="lg" type="dark" variant="dark" class="px-3">
    <b-navbar-brand href="#">Blog</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item :to="{name: 'home'}">Home</b-nav-item>
        <b-nav-item :to="{name: 'about'}">About</b-nav-item>
      </b-navbar-nav>
      <!-- Right aligned nav items -->
    </b-collapse>
  </b-navbar>
</div>
</template>

<script>
export default {
  name: 'NavBar'
}
</script>
