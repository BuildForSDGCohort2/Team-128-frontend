<template>
<div>
  <DashboardLayout>
    <b-container fluid id="lay" >
      <b-row>
          <b-col cols="4">
            <router-link to="/user/schedule">
              <b-card class="mb-2 text-center card cad">
                <b-card-header>Schedules</b-card-header>
                <b-card-text>
                  <b-badge variant="danger">9 </b-badge>
                </b-card-text>
              </b-card>
            </router-link>
          </b-col>
          <b-col cols="4">
            <router-link to="" class="cad">
              <b-card class="mb-2 text-center card cad">
                <b-card-header>Reservations</b-card-header>
                <b-card-text>
                  <b-badge variant="danger">9 </b-badge>
                </b-card-text>
              </b-card>
            </router-link>
          </b-col>
          <b-col cols="4">
            <router-link to="" class="cad">
              <b-card class="mb-2 text-center card cad">
                <b-card-header>Wallet</b-card-header>
                <b-card-text>
                  <b-badge variant="danger">9 </b-badge>
                </b-card-text>
              </b-card>
            </router-link>
          </b-col>
      </b-row>
    </b-container>
  </DashboardLayout>
  </div>
</template>
<script>
import DashboardLayout from '../layout/DashboardLayout.vue'
export default {
  name: 'PassengerDashboard',
  components: {
    DashboardLayout
  }
}
</script>
