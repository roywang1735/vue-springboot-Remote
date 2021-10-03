<template>
    <div class="list row">
        <div>
            <ul>
                <li v-for="(customer, index) in customers" :key="index">
                    <router-link :to="{name:'customer-details',params:{customer:customer,id:customer.id}}"><!-- router>>/customer-->
                            {{customer.name}} {{customer.age}}  {{customer.active}}
                    </router-link>                                                       
                </li>
            </ul>
        </div>
        <div>
            <router-view @refreshData="refreshList"></router-view>
        </div>
    </div>
</template>

<script>
import http from "../http-common";

export default {
  //name: "customers-list",
  data() {
    return {
      customers: []
    };
  },
  methods: {
    /* eslint-disable no-console */
    retrieveCustomers() {
      http
        .get("/customers")
        .then(response => {
          this.customers = response.data; // JSON are parsed automatically.
          console.log(response.data);
        })
        .catch(e => {
          console.log(e);
        });
    },
  
  
    refreshList() {
      this.retrieveCustomers();
    }

    /* eslint-enable no-console */
  },
  mounted() {
    this.retrieveCustomers();
  }
};
</script>

<style>
.list {
  text-align: left;
  max-width: 450px;
  margin: auto;
}
</style>
