<template>
  <div class="form">
    <input type="text" name="name" placeholder="Имя" v-model="name">
    <input type="text" name="phone" placeholder="Телефон" v-model="phone">
    <button @click="saveContact">Сохранить</button>
  </div>
</template>

<script>
export default {
  name: 'ContactsForm',
  data(){
    return{
      name: '',
      phone: '',
    }
  },
  methods: {
    saveContact(){
      this.$emit('save-contact', {name: this.name, phone: this.phone})
    }
  },
}
</script>

<style scoped>
  .form{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 10px;
  }
</style>
