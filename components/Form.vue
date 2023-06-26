<template>
  <div>
    <section class="flex flex-grow border-2 black mt-5 p-2">
      <div class="w-full max-w-xs flex flex-col">
        <label>
          <span>NIS</span>
        </label>
        <input type="number" placeholder="NIS" v-model="nis" />
      </div>
      <div class="w-full max-w-xs flex flex-col">
        <label>
          <span>Nama Siswa</span>
        </label>
        <input type="text" placeholder="Nama Siswa" v-model="nama" />
      </div>
      <div class="w-full max-w-xs flex flex-col">
        <label>
          <span>Nilai Tugas</span>
        </label>
        <input type="number" placeholder="NIS" v-model="nilai" />
      </div>
    </section>
    <section class="flex justify-center gap-2">
      <button
        class="rounded-full bg-teal-600 text-white w-16 mt-3"
        @click="
          $emit('add', { nis, nama, nilai })
          clearInput()
        "
      >
        ADD
      </button>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nis: '',
      nama: '',
      nilai: '',
    }
  },
  methods: {
    clearInput: function () {
      ;(this.nis = ''), (this.nama = ''), (this.nilai = '')
    },
  },
}
</script>

<style></style>
