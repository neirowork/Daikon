<template>
  <div class="column">
    <div class="card">
      <div v-if="data.company" class="company">{{ data.company }}</div>
      <div class="card-status"><span class="status-circle" :class="data.status"/>{{ data.name }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['data'],
  data() {
    return {
      data: ''
    }
  }
}
</script>

<style scoped>
.column {
  width: 33.3%;
  display: inline-block;
  font-size: 1rem;
  vertical-align: top;
}

.card {
  margin: 5px;
  padding: 10px;
  background-color: #ffffff;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
  color: #666666;
  font-weight: bold;
  text-align: center;
}

.company {
  margin: 0; 
  font-size: 0.95rem;
  background-color: #333333;
  color: #ffffff;
}

.card-status {
  font-size: 1.5em;
}
.status-circle::before {
  display: inline-block;
  position: relative;
  vertical-align: middle;
  content: '';
  width: 20px;
  height: 20px;
  margin: 10px;
  top: -0.1em;
  border-radius: 50%;
  background-color: #222222;
}

.status-circle.ok::before { background-color: #0bc01a; }
.status-circle.ng::before { background-color: #ff3300; }
</style>
