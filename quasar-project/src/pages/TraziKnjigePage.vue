<template>
  <q-page padding>
    <div class="text-h3">Pretraživanje</div>
    <div>Pretražite knjigu po naslovu ili autoru</div>
    <div class="q-pa-md" style="max-width: 400px">
      <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md">
        <q-input
          filled
          v-model="name"
          label="Unesite pojam"
          lazy-rules
          :rules="[val => (val && val.length > 0) || 'Please type something']"
        />
        <div class="q-pa-md">
          <div class="q-gutter-sm">
            <q-checkbox v-model="right" label="Pretraživanje po naslovu" />
            <q-checkbox v-model="right1" label="Pretraživanje po autoru" />
          </div>
        </div>
        <div>
          <q-btn label="Traži" type="submit" color="primary" />
          <q-btn
            label="Reset"
            type="reset"
            color="primary"
            flat
            class="q-ml-sm"
          />
        </div>
      </q-form>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const right = ref(true)
const right1 = ref(true)
</script>
