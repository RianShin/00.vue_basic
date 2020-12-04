<template>
  <div>
<!--    <v-list-item v-for="item in items" :key="item.title" :to="item.to">-->
<!--      <v-list-item-content>-->
<!--        {{ item.title }}-->
<!--      </v-list-item-content>-->
<!--    </v-list-item>-->
    <v-list>
      <v-list-group
        v-for="(item, i) in items"
        :key="i"
        v-model="item.active"
        :prepend-icon="item.icon"
        no-action
      >
        <template v-slot:activator>
          <v-list-item-content>
            <v-list-item-title v-text="item.title"></v-list-item-title>
          </v-list-item-content>
        </template>

        <v-list-item
          v-for="subItems in item.subItems"
          :key="subItems.title"
          :to="subItems.to"
        >
          <v-list-item-content>
            <v-list-item-title v-text="subItems.title"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-group>
    </v-list>
  </div>
</template>

<script>
export default {
  props: ['footer'],
  data () {
    return {
      items: [
        {
          title: 'home',
          icon: 'mdi-home',
          subItems: [
            {
              title: 'dashboard',
              to: '/'
            },
            {
              title: 'about',
              to: '/about'
            }
          ]
        },
        {
          title: 'about',
          active: true,
          icon: 'mdi-account',
          subItems: [
            {
              title: 'dashboard',
              to: '/'
            },
            {
              title: 'about',
              to: '/about'
            }
          ]

        },
        {
          title: 'main',
          to: '/main/main'
        }
      ]
    }
  }
}
</script>
