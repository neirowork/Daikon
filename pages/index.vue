<template>
  <div class="container">
    <div class="row">
      <div class="column">
        <div class="card">
          <div class="card-status"><span class="status-circle ok"/>宇都宮線</div>
        </div>
        <div class="card">
          <div class="card-status"><span class="status-circle ok"/>宇都宮線</div>
        </div>
      </div>
      <div class="column">
        <div class="card">
          <div class="card-status"><span class="status-circle ng"/>aA</div>
        </div>
        <div class="card">
          <div class="card-status"><span class="status-circle ok"/>宇都宮線</div>
        </div>
      </div>
      <div class="column">
        <div class="card">
          <div class="card-status"><span class="status-circle ok"/>宇都宮線</div>
        </div>
        <div class="card">
          <div class="card-status"><span class="status-circle ok"/>宇都宮線</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  
}
</script>

<style scoped>
.container {
  margin: 50px 5%;
}
.row {
  font-size: 0;
}

.column {
  width: 33.3%;
  display: inline-block;
  font-size: 1rem;
  vertical-align: top;
}

@media screen and (max-width: 800px) {

  .column {
    width: 100%;
    display: block;
    font-size: 1rem;
  }

}

.card {
  margin: 5px;
  padding: 10px;
  background-color: #ffffff;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
  color: #666666;
  font-size: 2em;
  font-weight: bold;
  text-align: center;
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
.status-circle.ng::before { background-color: #c00b0b; }
</style>
