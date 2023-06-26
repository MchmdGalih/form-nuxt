<template>
  <div class="w-full flex justify-center items-center">
    <div class="w-3/5">
      <Form @add="add"></Form>
      <Data :data="dataSiswa" @deleteData="deleteData" />
    </div>
  </div>
</template>

<script>
import Form from '../components/Form.vue'
import Data from '../components/Data.vue'
export default {
  name: 'IndexPage',
  components: {
    Form,
    Data,
  },
  data() {
    return {
      dataSiswa: [],
    }
  },
  methods: {
    add(data) {
      console.log('this->', data)
      if (!data.nis || !data.nama || !data.length <= 0) {
      } else {
        data = { ...data, id: Date.now() }
        this.dataSiswa.push(data)
      }
    },
    deleteData(id) {
      this.dataSiswa = this.dataSiswa.filter((items) => items.id !== id)
    },
  },
}
</script>
