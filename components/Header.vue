<template lang="html">
    <nav class="navbar has-shadow" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <nuxt-link  class="navbar-item" to="/">
          <img src="https://bulma.io/images/bulma-logo.png" alt="Bulma: a modern CSS framework based on Flexbox" width="112" height="28">
        </nuxt-link>

        <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" :class="{'is-active': menuIsActive}" @click="$store.commit('toggleMenuState')">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>
        <div class="nav-right nav-menu" :class="{'is-active': menuIsActive}">
          <div class="nav-item">
              <nuxt-link to="/posts">
                Go to Posts
              </nuxt-link>            
              </p>
            </div>
          </div>
        </div>
    </nav>
</template>

<script>

import { mapState } from 'vuex'

export default {
  computed: mapState([
    'menuIsActive'
  ]),
  methods: {
    testState () {
      this.$store.commit('toggleMenuState')
    }
  }
}
</script>

<style lang="css">
.siteTitle {
  font-weight: 700;
  font-size: 1.75em;
}

.slide-enter-active,
.slide-leave-active {
  transition: opacity 0.35s;
}

.slide-enter,
.slide-leave-active {
  opacity: 0;
}

.nav {
  max-width: 1440px;
  margin-left: auto;
  margin-right: auto;
}

.nav-menu.is-active {
  display: block;
}

.nav-menu{
  display: none;
}

.nav-item {
      border-top: 1px solid hsla(0,0%,86%,.5);
    padding: .75rem;
}

</style>
