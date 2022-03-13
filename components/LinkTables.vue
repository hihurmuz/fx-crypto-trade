<template>
<div>
  <v-data-table
    :headers="headers"
    :items="desserts"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>
</div>
</template>

<script>
export default {
  name: 'LinkTables',
  data () {
    return {
      headers: [
        {
          text: 'Tutar',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        { text: 'Banka Adı', value: 'calories' },
        { text: 'Hesap Sahibi', value: 'fat' },
        { text: 'Müşteri Adı', value: 'carbs' },
        { text: 'Mail', value: 'protein' },
        { text: 'Telefon', value: 'iron' },
        { text: 'Durum', value: 'status' },
      ],
      desserts: [
        {
          name: '1.200 ₺',
          calories: 'Akbak',
          fat: 'Ali Veli',
          carbs: 'Hasan Hüseyin',
          protein: 'booo@booo.com',
          iron: '5449949494',
          status: 'Ödendi - Aktarıldı'
        },
        {
          name: '1.600 ₺',
          calories: 'Akbak',
          fat: 'Ali Veli',
          carbs: 'Hasan Hüseyin',
          protein: 'booo@booo.com',
          iron: '5449949494',
          status: 'Ödendi - Aktarma Bekliyor'
        },
      ],
    }
  },
}
</script>
