<template>
  <v-card class="elevation-24" style="border-radius: 30px;">
    <v-carousel hide-controls hide-delimiters interval="3000">
      <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src">
      </v-carousel-item>
    </v-carousel>
  </v-card>
</template>

<script>
export default {
  name: 'Carousel',
  data() {
    return {
      items: [
        {
          src:
            'https://images.unsplash.com/photo-1454496406107-dc34337da8d6?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1163&q=80'
        },
        {
          src:
            'https://images.unsplash.com/photo-1548834925-e48f8a27ae6f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=967&q=80'
        },
        {
          src:
            'https://images.unsplash.com/photo-1486049252259-45184399c5b2?ixlib=rb-1.2.1&auto=format&fit=crop&w=1050&q=80'
        }
      ]
    }
  }
}
</script>
