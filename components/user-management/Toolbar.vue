<template>
  <v-toolbar
    class="d-flex-inline flex-row mt-10 toolbar-app"
    height="64"
    rounded="lg"
    dense
  >
    <v-col class="pl-0" align-self="center" cols="8" md="4">
      <h3>Admin</h3>
    </v-col>
    <v-col class="pr-0" cols="4" md="8" align="end">
      <v-dialog v-model="addUserDialog" width="500">
        <template #activator="{ on, attrs }">
          <v-btn color="primary" dark v-bind="attrs" v-on="on">
            <v-icon class="mr-1" small> mdi-account-plus </v-icon>
            EKLE
          </v-btn>
        </template>

        <v-card v-if="!addUserLoading">
          <v-card-title class="text-h4 primary--text pt-12 ml-n2">
            Kullanıcı Ekle
          </v-card-title>

          <v-col class="pa-4">
            <v-text-field
              v-model="newUser.displayName"
              outlined
              label="Ad Soyad"
            />
            <v-text-field
              v-model="newUser.email"
              outlined
              label="E-Posta"
            />
            <div v-if="userInviteError" class="error--text">
              {{ userInviteError }}
            </div>
          </v-col>

          <v-card-actions class="pb-6">
            <v-btn
              color="primary"
              block
            >
              <v-icon class="mr-1" small> mdi-content-save </v-icon>
              KAYDET
            </v-btn>
          </v-card-actions>
        </v-card>

        <v-card
          v-else
          width="500"
          height="300"
          class="d-flex flex-row justify-center align-center"
        >
          <v-progress-circular :size="50" color="primary" indeterminate />
        </v-card>
      </v-dialog>
    </v-col>
  </v-toolbar>
</template>

<script>
export default {
  name: 'Toolbar',
  data () {
    return {
      newUser: {
        displayName: '',
        email: ''
      },
      userInviteError: null,
      addUserDialog: false
    }
  }
}
</script>

