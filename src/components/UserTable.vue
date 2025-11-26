<template>
  <section class="table-section">
    <h2 class="table-title">Liste des Utilisateurs</h2>

    <div class="table-wrapper">
      <table class="user-table">
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
            <td class="actions-cell">
              <button class="btn btn-edit" @click="editUser(user.id)">Modifier</button>
              <button class="btn btn-delete" @click="deleteUser(user.id)">Supprimer</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const users = ref([
  { id: 1, name: 'Alice Martin', email: 'alice@example.com', role: 'Admin' },
  { id: 2, name: 'Bob Dupont', email: 'bob@example.com', role: 'User' },
  { id: 3, name: 'Charlie Moreau', email: 'charlie@example.com', role: 'User' },
  { id: 4, name: 'Diana Bernard', email: 'diana@example.com', role: 'Manager' },
  { id: 5, name: 'Eric Petit', email: 'eric@example.com', role: 'User' },
])

const editUser = (id: number) => {
  console.log('Modifier utilisateur:', id)
}

const deleteUser = (id: number) => {
  console.log('Supprimer utilisateur:', id)
}
</script>

<style scoped>
.table-section {
  margin-top: 2rem;
}

.table-title {
  color: #42b883;
  margin-bottom: 1rem;
}

.table-wrapper {
  width: 100%;
  overflow-x: auto;
}

.user-table {
  width: 100%;
  border-collapse: collapse;
  background: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

thead {
  background: #42b883;
  color: white;
}

th,
td {
  padding: 1rem;
  text-align: left;
  font-size: 0.95rem;
}

tbody tr:nth-child(even) {
  background: #f8f9fa;
}

tbody tr:hover {
  background: #eefaf4;
}

.actions-cell {
  white-space: nowrap;
}

.btn {
  padding: 0.45rem 0.9rem;
  margin-right: 0.4rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 0.85rem;
  font-weight: 500;
  transition: all 0.2s ease;
}

.btn-edit {
  background: #42b883;
  color: white;
}

.btn-edit:hover {
  background: #37966d;
}

.btn-delete {
  background: #e74c3c;
  color: white;
}

.btn-delete:hover {
  background: #c0392b;
}
</style>
