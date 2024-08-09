<template>
  <div class="employee-list-container">
    <h2 class="employee-list-title">LISTE DES EMPLOYES</h2>
    <ol class="employee-list">
      <li
        v-for="employee in employees"
        :key="employee.id"
        @mouseover="hoveredEmployeeId = employee.id"
        @mouseleave="hoveredEmployeeId = null"
        :class="{ hover: hoveredEmployeeId === employee.id }"
      >
        {{ employee.name }}
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  data() {
    return {
      employees: [
        { id: 1, name: 'Harouna Traoré' },
        { id: 2, name: 'Mouhamed Bankolé' },
        { id: 3, name: 'Abdu rahman Thimbo' },
        { id: 4, name: 'Oumar ndiaye' }
      ],
      hoveredEmployeeId: null
    };
  }
};
</script>

<style scoped>
.employee-list-container {
  width: 400px;
  margin: 50px auto;
  text-align: center;
}

.employee-list-title {
  font-size: 30px;
  margin-bottom: 20px;
  color:blue;
  font-weight: bold;
}
.employee-list {
  list-style-type: decimal;
  padding: 0;
  margin: 0;
}

.employee-list li {
  padding: 10px;
  margin: 5px 0;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #fff;
  text-align: center;
  transition: background-color 0.3s ease;
}

.employee-list li.hover {
  background-color:rgb(199, 199, 235);
}
</style>
