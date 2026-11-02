<template>
  <q-page padding>
    <div class="text-h3">Log in</div>
    <div>Prijavite se na svoj korisnički račun</div>
    <div class="q-pa-md" style="max-width: 400px">
  <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md">
    <q-input
      filled
      v-model="name"
      label="Korisničko ime"
      lazy-rules
      :rules="[val => (val && val.length > 0) || 'Please type something']"
    />

    <q-input
      filled
      v-model="name"
      label="Lozinka"
      lazy-rules
      :rules="[val => (val && val.length > 0) || 'Please type something']"
    />

    <div>
      <q-btn label="Submit" type="submit" color="primary" />
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
import { useQuasar } from 'quasar'
import { ref } from 'vue'

const $q = useQuasar()

const name = ref(null)
const age = ref(null)
const accept = ref(false)

function onSubmit() {
  if (accept.value !== true) {
    $q.notify({
      color: 'red-5',
      textColor: 'white',
      icon: 'warning',
      message: 'You need to accept the license and terms first'
    })
  } else {
    $q.notify({
      color: 'green-4',
      textColor: 'white',
      icon: 'cloud_done',
      message: 'Submitted'
    })
  }
}

function onReset() {
  name.value = null
  age.value = null
  accept.value = false
}
</script>
