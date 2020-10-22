<template>
  <div>
    <DashboardLayout>
      <div class="dashboardcon">
        <div class="dashboardlink">
          <router-link to="/tsp/dashboard">Dashboard</router-link> >
          <router-link to="/tsp/soldtickets">View Sold ticket</router-link>
        </div>
        <div>
          <b-form-datepicker
          id="datepicker"
          today-button
          reset-button
          close-button
          placeholder="All Date"
          v-model="value"
          class="mb-1 date"
          :date-format-options="{
            year:'numeric',
            month:'numeric',
            day:'numeric'
            }"
          ></b-form-datepicker>
                <b-form-select
                  class="schedule"
                  v-model="selected"
                  :options="schedule"
                ></b-form-select>
        </div>
        <div class="table">
          <b-table striped hover :items="items"></b-table>
        </div>
      </div>
    </DashboardLayout>
  </div>
</template>

<script>
import DashboardLayout from '../layout/DashboardLayout.vue'
export default {
  name: 'TicketsSold',
  components: {
    DashboardLayout
  },
  data () {
    return {
      items: [
        {
          ticket_number: '191020C354001',
          from: 'Rigassa station, Kaduna',
          to: 'Abuja Station',
          departur_time: '7:30 AM',
          arrival_time: '8:30 AM',
          carrier: 'C 354',
          cost: 'N2500'
        }
      ],
      schedule: [
        { value: null, text: 'All schedule' },
        { value: 'id', text: '7:00 pm' },
        { value: 'id', text: '2:00 pm' },
        { value: 'id', text: '7:00 pm' }
      ],
      form: {
        email: '',
        name: ''
      }
    }
  },
  methods: {
    onSubmit (evt) {
      evt.preventDefault()
      alert(JSON.stringify(this.form))
    },
    onReset (evt) {
      evt.preventDefault()
      // Reset our form values
      this.form.email = ''
      this.form.password = ''

      // Trick to reset/clear native browser form validation state
    }
  }
}
</script>
