<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <v-card>
          <v-card-title>
            <h1>Reach out
              <v-icon>
                mdi-arrow-down-right
              </v-icon>
            </h1>
          </v-card-title>
          <v-btn
            variant="plain"
            class="mx-auto"
            :ripple="false"
            >
            <v-icon
              class="mr-2">
              mdi-email
            </v-icon>
              lukas@unlocked.dk
          </v-btn>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<style scoped>
.primary-btn {
border-radius: 25px;
background-color: #02CFAA;
color: black;
}
</style>
