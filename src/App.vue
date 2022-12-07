<template>
  <div class="container">
    <h3>У вас {{contactsLength}} контактов</h3>
    <ContactsList @delete-contact="deleteContact" :contacts=contacts />
    <ContactsForm @save-contact="addContact" />
  </div>
</template>

<script>
import ContactsForm from '@/components/ContactsForm.vue'
import ContactsList from '@/components/ContactsList.vue'

export default {
  name: 'App',
  components: {
    ContactsForm,
    ContactsList
  },
  data(){
    return{
      contacts: [],
    }
  },
  methods: {
    addContact(contact){
      this.contacts.push(contact);
    },
    deleteContact(index){
      this.contacts.splice(index, 1);
    }
  },
  computed:{
    contactsLength(){
      return this.contacts.length
    }
  },
}
</script>

<style>
body{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
}
</style>
