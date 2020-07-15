<template>
  <crud-form :headers="headers" :items="items" :schema="schema" :options="options"></crud-form>
</template>

<script>
import { customer } from "~/static/customer.js";

export default {
  data: () => ({
    items: customer,
    headers: [
      {
        text: "Customer Id",
        align: "start",
        sortable: false,
        value: "id"
      },
      { text: "Customer Name", value: "name" },
      { text: "OEM Group", value: "oemGroup" },
      { text: "Customer Group", value: "customerGroup" },
      { text: "Active", value: "active"},
      { text: "Actions", value: "actions", sortable: false } //should be in componente i guess
    ],
    options: {},
    schema: {
      type: "object",
      properties: {
        id: {
          type: "number",
          title: "customer id"
        },
        name: {
          type: "string",
          title: "Customer Name",
          description: "enter customer name."
        },
         oemGroup: {
          type: "string",
          title: "OEM Group",
          enum:[
            "BMW Group","Daimler Group","Volkswagen Group"
          ],
          description: "This is the customer name."
        },
         customerGroup: {
          type: "string",
          title: "Customer Group",
            enum:[
            "G CBG","A CBG","C CBG"
          ],
          description: "Customer Group"
        },

        description: {
          type: "string",
          title: "Enter customer description",
          "x-display": "textarea"
        },
     
        active: {
          type: "boolean",
          title: "Active"
        },
      }
    }
  })
};
</script>

<style>
</style>
