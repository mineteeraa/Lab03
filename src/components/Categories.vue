<template>
  <div class="category-card">
    <h5>@{{ category.category }} on {{ category.organizer }}</h5>
  </div>
</template>

<script>
export default {
  name: 'Categories',
  props: {
    category: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.category-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
  text-align: right;
}

.category-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>