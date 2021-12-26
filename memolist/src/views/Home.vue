<template>
  <div class="home">
    <Title>My Memos</Title>
    <ul v-for="memo in newest" :key="memo.id">
      <li>
        <router-link :to="{name: 'Edit', params: { id: memo.id }}">
          {{ memo.body }}
        </router-link>
      </li>
      
    </ul>
  </div>
</template>

<script>
import Title from "@/components/Title.vue"

export default {
  name: "home",
  components: {
    Title
  },
  computed:{
    newest: function() {
      return this.$store.state.memos;
    }
  }
}
</script>
