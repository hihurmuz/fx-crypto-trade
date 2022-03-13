<template>
  <v-card class="mx-auto pa-10"
          max-width="600">
    <v-radio-group v-model="paymentType" class="px-2 pt-8">
      <v-layout>

        <v-flex>
          <v-radio value="Banka" label="Banka" />
        </v-flex>

        <v-flex>
          <v-radio value="Papara" label="Papara" />
        </v-flex>

      </v-layout>
    </v-radio-group>

    <div v-if="paymentType === 'Banka'">
      <v-col>
        <v-select
          class="pt-0"
          :items="items"
          label="Banka Adı"
        />
      </v-col>
      <v-col>
        <v-text-field
          class="pt-0"
          label="IBAN"
        />
      </v-col>
      <v-col>
        <v-text-field
          class="pt-0"
          label="Hesap Sahibi"
        />
      </v-col>
    </div>
    <div v-else>
      <v-col>
        <v-text-field
          class="pt-0"
          label="Papara No"
        />
      </v-col>
      <v-col>
        <v-text-field
          class="pt-0"
          label="Hesap Sahibi Adı"
        />
      </v-col>
    </div>
    <div>
      <v-col>
        <v-text-field
          class="pt-0"
          label="Müşteri Adı"
        />
      </v-col>
      <v-col>
        <v-text-field
          class="pt-0"
          label="Mail"
        />
      </v-col>
      <v-col>
        <v-text-field
          class="pt-0"
          label="Telefon"
        />
      </v-col>
      <v-col>
        <v-text-field
          class="pt-0"
          label="Tutar"
        />
      </v-col>
    </div>
    <v-col>
      <v-btn block outlined large color="primary">
        Ödeme Linki Oluştur
      </v-btn>
    </v-col>

  </v-card>
</template>

<script>
export default {
  name: 'CreateLink',
  data() {
    return {
      items: ['Akbak', 'Garanti', 'Qnb', 'Ziraat'],
      paymentType: 'Banka'
    }
  }
}
</script>
