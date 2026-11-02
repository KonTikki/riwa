<template>
  <q-page padding>
    <div class="q-pa-md">
      <q-table title="Treats" :rows="rows" :columns="columns" row-key="name" />
    </div>
  </q-page>
</template>

<script setup>
const columns = [
  {
    name: 'name',
    required: true,
    label: 'ID',
    align: 'left',
    field: row => row.name,
    format: val => `${val}`,
    sortable: true
  },
  { name: 'Naslov', align: 'left', label: 'Naslov', field: 'Naslov', sortable: true},
  { name: 'Autor', label: 'Autor', field: 'Autor', sortable: true },
  { name: 'Godina', label: 'Godina', field: 'Godina' },
  { name: 'Žanr', label: 'Žanr', field: 'Žanr' },
]

const rows = [
  {
    name: 0,
    Naslov: "Star Wars: Light of the Jedi",
    Autor: "Charles Soule",
    Godina: 2021,
    Žanr: "Sci-Fi"
  },
  {
    name: 1,
    Naslov: "Družba Pere Kvržice",
    Autor: "Mato Lovrak",
    Godina: 1933,
    Žanr: "Fikcija"
  },
  {
    name: 2,
    Naslov: "Vlak u snijegu",
    Autor: "Mate Relja",
    Godina: 1976,
    Žanr: "Avanturistički"
  },
  {
    name: 3,
    Naslov: "Hamlet",
    Autor: "William Shakespeare",
    Godina: 1623,
    Žanr: "Tragedija"
  }
]
</script>
