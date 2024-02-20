
  <template>
    <div class="container">
      <form class="form" @submit.prevent="addGuest">
        <h2>Add Guest Name</h2>
        <label for="name">Guest Name:</label>
        <input type="text" id="name" name="name" placeholder="Enter Guest Name" v-model="newName">
        <label for="phone">Phone Number:</label>
        <input type="text" id="phone" name="phone" placeholder="Enter Phone Number" v-model="newPhoneNumber">
        <button>Add Guest</button>
      </form>
      <div class="data" id="formData">
        <h2>Guest list</h2>
        <ul>
          <li v-for="guest in guests" :key="guest.id">
            Name: {{ guest.name }} - Phone: {{ guest.phone }}
          </li>
        </ul>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const guests = ref([]);
  const newName = ref('');
  const newPhoneNumber = ref('');
  
  const addGuest = () => {
    if (newName.value.trim() !== '' && newPhoneNumber.value.trim() !== '') {
      guests.value.push({
        name: newName.value,
        phone: newPhoneNumber.value
      });
      newName.value = '';
      newPhoneNumber.value = '';
    }
  };
  </script>

  
  
  <style scoped>
    body {
        font-family: Arial, sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
        
    }
    .container {
        display: flex;
        width: 100%;
        height: 100%;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        margin-left: 350px;
    }
    .form {
        flex: 1;
        padding: 20px;
        background-color: #f9f9f9;
    }
    .data {
        flex: 1;
        padding: 20px;
        background-color: #e9e9e9;
        overflow-y: auto;
    }
    label {
        display: block;
        margin-bottom: 5px;
    }
    input {
        width: 100%;
        padding: 8px;
        margin-bottom: 10px;
        box-sizing: border-box;
    }
    button {
        padding: 8px 12px;
        background-color: #007bff;
        color: white;
        border: none;
        cursor: pointer;
    }
    button:hover {
        background-color: #0056b3;
    }
  
  </style>