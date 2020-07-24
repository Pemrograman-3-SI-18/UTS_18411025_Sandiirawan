<template>
<q-page padding class="items-center-justify-center bg-grey-3">
    <q-card flat class="bg-white q-pa-md">
      <span class="text-h5 text-weight-light q-pa-md">
        <span class="text-blue-grey-14">Tambah Data Tas</span>
      </span>
      <div class="q-pa-md">
        <q-form
          class="q-gutter-md"
        >
        <q-input
            label="Kode Tas"
            lazy-rules
            color="teal"
            v-model="kodTas"
            :rules="[
           val => val !== null && val !== '' || 'Tuliskan kode Tas yang inging ditambahkan'
           ]">
            <template v-slot:append>
              <q-icon name="description"/>
            </template>
          </q-input>

          <q-input
            label="Jenis Tas"
            lazy-rules
            color="teal"
            v-model="jenisTas"
            :rules="[
           val => val !== null && val !== '' || 'Tuliskan Jenis tas yang ingin ditambahkan'
           ]">
            <template v-slot:append>
              <q-icon name="title"/>
            </template>
          </q-input>

           <q-input
            label="Nama Tas"
            lazy-rules
            color="teal"
            v-model="namaTas"
            :rules="[
           val => val !== null && val !== '' || 'Tuliskan nama tas yang ingin ditambahkan'
           ]">
            <template v-slot:append>
              <q-icon name="title"/>
            </template>
          </q-input>

           <q-input
            label="Ketersedian Tas"
            lazy-rules
            color="teal"
            v-model="stockTas"
            :rules="[
           val => val !== null && val !== '' || 'Tuliskan ketersediaan tas yang ingin ditambahkan'
           ]">
            <template v-slot:append>
              <q-icon name="exposure"/>
            </template>
          </q-input>

           <q-input
            label="Harga Tas"
            lazy-rules
            color="teal"
            v-model="hargaTas"
            :rules="[
           val => val !== null && val !== '' || 'Tuliskan judul buku yang ingin ditambahkan'
           ]">
            <template v-slot:append>
              <q-icon name="money"/>
            </template>
          </q-input>

          <div>
            <q-btn
              unelevated
              icon="add"
              label="Tambah Data Tas"
              style="height: 50px"
              color="teal-6"/>
          </div>
        </q-form>
      </div>
    </q-card>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      kodTas: null,
      jenisTas: null,
      namaTas: null,
      stockTas: null,
      hargaTas: null
    }
  }
}

</script>
