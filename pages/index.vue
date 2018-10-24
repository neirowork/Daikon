<template>
  <div class="container">
    <app-card
      v-for="(data, index) in column"
      :key="index"
      :data="data"/>
  </div>
</template>

<script>
import AppCard from '~/components/AppCard'
import axios from 'axios'
import _lines from '~/assets/lines.json'

export default {
  components: { AppCard },
  data() {
    return {
      column: [],
    }
  },
  created() {
    this.lines = require('~/assets/lines.json')
  },
  mounted() {
    const lines = Object.assign({}, this.lines)

    axios
      .get('/fhc/api/train_tetsudo/delay.json',
      {
        mode: 'no-cors',
        headers: {
          'Access-Control-Allow-Origin': '*',
          'Content-Type': 'application/json',
        },
      })
      .then(res => {
        
        const delays = res.data

        Object.keys(lines).forEach(company => {
          lines[company].forEach(line => {

            delays.forEach(delay => {

              if(delay.company == company && delay.name == line) {
                
                this.column.push({
                  company: company,
                  name: line,
                  status: 'ng'
                })

              }

            })

          })
        })

        if(this.column.length === 0) {
          this.column.push({
            name: '遅延情報はありません',
            status: 'ok'
          })
        }

      })
    
  }
}
</script>

<style scoped>
.container {
  margin: 5% 5%;
}
.row {
  font-size: 0;
}

@media screen and (max-width: 800px) {

  .column {
    width: 100%;
    display: block;
    font-size: 1rem;
  }

}
</style>
