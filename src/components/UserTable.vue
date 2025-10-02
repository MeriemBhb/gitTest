<template>
  <div class="table-container">
    <h2>Liste des Utilisateurs</h2>

    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>Nom</th>
          <th>Email</th>
          <th>Rôle</th>
          <th>Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <td>{{ user.id }}</td>
          <td>{{ user.name }}</td>
          <td>{{ user.email }}</td>
          <td>{{ user.role }}</td>
          <td>
            <button @click="editUser(user.id)">Modifier</button>
            <button @click="deleteUser(user.id)">Supprimer</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const users = ref([
  { id: 1, name: 'Alice Martin', email: 'alice@example.com', role: 'Admin' },
  { id: 2, name: 'Bob Dupont', email: 'bob@example.com', role: 'User' },
  { id: 3, name: 'Charlie Moreau', email: 'charlie@example.com', role: 'User' },
  { id: 4, name: 'Diana Bernard', email: 'diana@example.com', role: 'Manager' },
  { id: 5, name: 'Eric Petit', email: 'eric@example.com', role: 'User' },
])

const editUser = (id) => {
  console.log('Modifier utilisateur:', id)
}

const deleteUser = (id) => {
  console.log('Supprimer utilisateur:', id)
}
</script>

<style scoped>
.table-container {
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

h2 {
  color: #42b883;
  margin-bottom: 1.5rem;
}

table {
  width: 100%;
  border-collapse: collapse;
  background: white;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
  overflow: hidden;
}

thead {
  background: #42b883;
  color: white;
}

th {
  padding: 1rem;
  text-align: left;
  font-weight: 600;
}

td {
  padding: 1rem;
  border-bottom: 1px solid #e0e0e0;
}

tbody tr:hover {
  background: #f5f5f5;
}

tbody tr:last-child td {
  border-bottom: none;
}

button {
  padding: 0.5rem 1rem;
  margin-right: 0.5rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 0.875rem;
  transition: all 0.3s;
}

button:first-child {
  background: #42b883;
  color: white;
}

button:first-child:hover {
  background: #35a372;
}

button:last-child {
  background: #e74c3c;
  color: white;
}

button:last-child:hover {
  background: #c0392b;
}
</style>
