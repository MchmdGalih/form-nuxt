<template>
  <div class="flex flex-col py-5">
    <h4 class="text-center py-5">Nilai Rata-rata Siswa : {{ average }}</h4>
    <table class="table-fixed w-full border-2 black">
      <thead class="bg-zinc-500">
        <tr>
          <th>ID</th>
          <th>NIS</th>
          <th>NAMA SISWA</th>
          <th>NILAI TUGAS</th>
          <th></th>
        </tr>
      </thead>
      <tbody class="text-center">
        <tr v-for="items of data" :key="items.id">
          <td>{{ items.id }}</td>
          <td>{{ items.nis }}</td>
          <td>{{ items.nama }}</td>
          <td>{{ items.nilai }}</td>
          <td>
            <button
              class="rounded-full bg-teal-600 text-white w-16"
              @click="$emit('deleteData', items.id)"
            >
              Delete
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Array,
      required: true,
    },
  },
  computed: {
    average() {
      if (this.data.length > 0) {
        const sum = this.data.reduce((sum, items) => sum + items.nilai, 0)
        return sum / this.data.length
      } else {
        return 0
      }
    },
  },
}
</script>

<style></style>
