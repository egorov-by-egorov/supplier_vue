<template>
  <ul class="sidenav app-sidenav" :class="{open: value}">
      <router-link
        v-for="link in links"
        :key="link.url"
        :to="link.url"
        :exact="link.exact"
        custom
        v-slot="{href, route, navigate, isActive, isExactActive}"
      >
        <li :class="isActive && 'active'">
          <a class="waves-effect waves-orange pointer" :href="href" @click="navigate">{{ link.title }}</a>
        </li>
      </router-link>
    </ul>
</template>

<script>
export default {
  name: "Sidebar",
  props: ['value'],
  data: () => ({
    links: [
      {title: 'Счет', url: '/', exact: true},
      {title: 'История', url: '/history'},
      {title: 'Планирование', url: '/planning'},
      {title: 'Новая запись', url: '/record'},
      {title: 'Категории', url: '/categories'}
    ]
  })
}
</script>

<style scoped>

</style>
