<template>
  <ul class="Menu">
    <li class="Menu__Item">
      <nuxt-link class="Menu__Item__Link" to="/guide">
        {{ $store.state.lang.links.guide }}
      </nuxt-link>
    </li>
    <li class="Menu__Item">
      <nuxt-link class="Menu__Item__Link" to="/api">
        {{ $store.state.lang.links.api }}
      </nuxt-link>
    </li>
    <li class="Menu__Item">
      <nuxt-link class="Menu__Item__Link" to="/examples">
        {{ $store.state.lang.links.examples }}
      </nuxt-link>
    </li>
    <li class="Menu__Item">
      <nuxt-link class="Menu__Item__Link" to="/faq">
        {{ $store.state.lang.links.faq }}
      </nuxt-link>
    </li>
    <li class="Menu__Item">
      <nuxt-header-nav-menu-dropdown :dropdownList="dropdownList" :dropdownLabel="$store.state.lang.links.ecosystem" />
    </li>
  </ul>
  </nav>
</template>

<script>
import NuxtHeaderNavMenuDropdown from '~/components/HeaderNavMenuDropdown.vue'

export default {
  components: {
    NuxtHeaderNavMenuDropdown
  },
  data() {
    return {
      dropdownList: [
        {
          name: this.$store.state.lang.links.github,
          path: 'https://github.com/nuxt',
          target: '_blank'
        },
        {
          name: this.$store.state.lang.links.twitter,
          path: 'https://twitter.com/nuxt_js',
          target: '_blank'
        },
        {
          name: this.$store.state.lang.links.chat,
          path: 'https://discord.gg/VApZF5W',
          target: '_blank'
        },
        {
          name: this.$store.state.lang.links.vuejs,
          path: 'https://vuejs.org',
          target: '_blank'
        },
        {
          name: this.$store.state.lang.links.vue_jobs,
          path: 'https://vuejobs.com/?ref=nuxtjs',
          target: '_blank'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.Menu {
  width: 100%;
  margin: 0;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  list-style: none;
  justify-content: space-between;
  @media (min-width: 991px) {
    flex: 1;
    flex-wrap: nowrap;
    padding-left: 15px;
  }
  &__Item {
    width: 100%;
    display: flex;
    border-bottom: 1px solid #dbdfe1;
    @media (min-width: 991px) {
      border-bottom: none;
    }
    &:last-child {
      border-bottom: none;
    }
    &__Link {
      height: 60px;
      display: flex;
      width: 100%;
      align-items: center;
      justify-content: center;
      color: #35495e;
      font-size: 16px;
      text-decoration: none;
      letter-spacing: 0.5px;
      &:hover {
        color: #41b883;
      }
      @media (min-width: 991px) {
        height: 79px;
      }
    }
    .nuxt-link-active,
    .nuxt-link-active:hover {
      color: #41b883;
    }
  }
}
</style>
