<template>
 <div class="q-pa-md">
    <q-table
      title="Treats"
      :data="data"
      :columns="columns"
      row-key="id"
      :filter="filter"
      :loading="loading"
    >

      <template v-slot:top>
        <q-btn color="primary" :disable="loading" label="Tambah Data Tas" to="/admin/inputdatatas"/>
        <!-- <q-btn class="q-ml-sm" color="primary" :disable="loading" label="Remove row" @click="removeRow" /> -->
        <q-space />
        <q-input borderless dense debounce="300" color="primary" v-model="filter">
          <template v-slot:append>
            <q-icon name="search" />
          </template>
        </q-input>
      </template>

    </q-table>
  </div>

</template>

<script>
export default {
  data () {
    return {
      loading: false,
      filter: '',
      rowCount: 10,
      columns: [
        {
          name: 'desc',
          required: true,
          label: 'Kode Tas',
          align: 'left',
          field: row => row.kodeTas,
          format: val => `${val}`,
          sortable: true
        },
        { name: 'jenisTas', align: 'center', label: 'Jenis Tas', field: 'jenisTas', sortable: true },
        { name: 'namaTas', align: 'center', label: 'Nama Tas', field: 'namaTas' },
        { name: 'stockTas', align: 'center', label: 'Ketersediaan Tas', field: 'stockTas' },
        { name: 'hargaTas', align: 'center', label: 'Harga Tas', field: 'hargaTas' }
      ],
      data: [
        {
          kodeTas: 'B001',
          jenisTas: 'Tas Wanita',
          namaTas: 'Tas Retro Selempang Fashion Wanita',
          stockTas: '50',
          hargaTas: 'Rp100.000'
        },
        {
          kodeTas: 'B002',
          jenisTas: 'Tas Wanita',
          namaTas: 'Tas Chanel Woc R2075 QAZ 94',
          stockTas: '10',
          hargaTas: 'Rp.350.000'
        },
        {
          kodeTas: 'B003',
          jenisTas: 'Tas Wanita',
          namaTas: 'Tas Cyncyn Jimshoney',
          stockTas: '35',
          hargaTas: 'Rp.200.000'
        }
      ]
    }
  },

  methods: {
    // emulate fetching data from server
    addRow () {
      this.loading = true
      setTimeout(() => {
        const
          index = Math.floor(Math.random() * (this.data.length + 1)),
          row = this.original[Math.floor(Math.random() * this.original.length)]
        if (this.data.length === 0) {
          this.rowCount = 0
        }
        row.id = ++this.rowCount
        const addRow = { ...row } // extend({}, row, { name: `${row.name} (${row.__count})` })
        this.data = [...this.data.slice(0, index), addRow, ...this.data.slice(index)]
        this.loading = false
      }, 500)
    },

    removeRow () {
      this.loading = true
      setTimeout(() => {
        const index = Math.floor(Math.random() * this.data.length)
        this.data = [...this.data.slice(0, index), ...this.data.slice(index + 1)]
        this.loading = false
      }, 500)
    }
  }
}
</script>
