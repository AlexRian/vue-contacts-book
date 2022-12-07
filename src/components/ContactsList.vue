<template>
  <div class="list">
    <h1>{{title}}</h1>
    <h3 v-for="(contact, index) in contacts" :key='index'>
      {{index}} - {{contact.name}} {{contact.phone}}
      <button @click="deleteContact">Удалить</button>
    </h3>
  </div>
</template>

<script>
export default {
  name: 'ContactsList',
  props:{
    contacts: Array,
    title: String,
  },
  methods:{
    deleteContact(index){
      this.$emit('delete-contact', index)
    }
  },
}
</script>

<style scoped>
</style>
