<template>
  <v-toolbar-title>
    {{title}}
    <v-btn icon>
      <v-icon>mdi-magnify</v-icon>
    </v-btn>
  </v-toolbar-title>
</template>
<script>
export default {
  props: ['title']
}
</script>
