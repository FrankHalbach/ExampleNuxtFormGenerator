<template>
  <crud-form :headers="headers" :items="items" :schema="schema" :options="options"></crud-form>
</template>

<script>
//in reality we will pull data from api
import { plants } from "~/static/plants.js";

export default {
  data: () => ({
    items: plants,
    headers: [
      {
        text: "Plant Id",
        align: "start",
        sortable: false,
        value: "id"
      },
      { text: "Plant Name", value: "nameShort" },
      { text: "Currency", value: "currency" },
      { text: "Actions", value: "actions", sortable: false } //should be in componente i guess
    ],
    options: {},
    schema: {
      type: "object",
      properties: {
        id: {
          type: "number",
          title: "Plant id"
        },
        nameShort: {
          type: "string",
          title: "Plant Name Short",
          description: "enter plant name."
        },
        nameLong: {
          type: "string",
          title: "Plant Name Long",
          description: "Long Plant Name"
        },
        country: {
          type: "string",
          title: "Country",
          enum: ["USA", "Germany", "Slovakia", "Portugal"],
          description: "Select Country"
        },
        currency: {
          tpye: "string",
          title: "Currency",
          enum: ["USD", "EUR"],
          description: "Select Plant Currency"
        },
        description: {
          type: "string",
          title: "Enter plant description",
          "x-display": "textarea"
        },

        active: {
          type: "boolean",
          title: "Active"
        }
      }
    }
  })
};
</script>

<style>
</style>