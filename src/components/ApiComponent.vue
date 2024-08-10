<template>
    <div>
      <h1>Client Data</h1>
      
      <!-- Display Data in a Table -->
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Email</th>
            <th>Actions</th> <!-- New column for actions -->
          </tr>
        </thead>
        <tbody>
          <tr v-for="client in dataVue" :key="client.id">
            <td>{{ client.client_id }}</td>
            <td>{{ client.name }}</td>
            <td>{{ client.email }}</td>
            <td>
              <!-- Edit and Delete Buttons -->
              <button @click="editClient(client)">Edit</button>
              <button @click="deleteClient(client.client_id)">Delete</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
 export default {
  name: 'API',
  data() {
    return {
      dataVue: [], // Array to store data from the API
    };
  },
  created() {
    this.fetchData(); // Call the fetchData method on component creation
  },
  methods: {
    fetchData() {
      // Fetch data from the API
      fetch('http://localhost:9090/clients/findAll')
        .then(response => response.json()) // Convert the response to JSON
        .then(data => {
          this.dataVue = data; // Assign the fetched data to dataVue
        })
        .catch(error => console.error('Error fetching data:', error)); // Handle any errors
    },
    affiche() {
      console.log(this.dataVue); // Display the data in the console
    },
    editClient(client) {
      // Handle the edit action
      console.log('Edit client:', client);
      alert(`Edit client: ${client.name}`);
    },
    deleteClient(clientId) {
      // Handle the delete action
      fetch(`http://localhost:9090/clients/delete/${clientId}`, {
        method: 'DELETE',
      })
        .then(response => {
          if (response.ok) {
            this.fetchData(); // Fetch the updated data after deletion
          } else {
            console.error('Error deleting client');
          }
        })
        .catch(error => console.error('Error:', error));
    },
  },
};

  </script>
  
  <style>
  /* Optional styling for the table */
  table {
    width: 100%;
    border-collapse: collapse;
  }
  
  th, td {
    border: 1px solid #ddd;
    padding: 8px;
  }
  
  th {
    background-color: #f2f2f2;
    text-align: left;
  }
  
  button {
    margin-right: 5px;
    padding: 5px 10px;
    border: none;
    background-color: #007BFF;
    color: white;
    cursor: pointer;
  }
  
  button:last-child {
    background-color: #DC3545;
  }
  
  button:hover {
    opacity: 0.8;
  }
  </style>
  