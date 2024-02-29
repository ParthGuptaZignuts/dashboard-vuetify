<script setup lang="ts">
import SideBar from '@/components/SideBar.vue'
import DoughtnutMain from '../components/DoughtnutMain.vue'
import BubbleMain from '../components/BubbleMain.vue'
import BarMain from '../components/BarMain.vue'

interface Folders {
  subtitle: string | number
  title: string
  img: any
}

const folders: Folders[] = [
  {
    subtitle: 'John Doe',
    title: 'john@gmail.com',
    img: '1.jpg'
  }
]
</script>

<template>
  <VApp id="inspire" style="background-color: rgba(219, 251, 251, 0.974)">
    <SideBar />
    <VMain>
      <VContainer class="px-6 mt-n2" fluid>
        <VRow>
          <VCol cols="12" sm="4">
            <VCard color="#849239" theme="dark" class="rounded-xl" height="150">
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <VCardTitle class="text-h5 mt-10">Boeing 787</VCardTitle>
                  <VCardSubtitle>$548</VCardSubtitle>
                </div>
                <VImg src="av.png" class="mr-4 mt-5" absolute></VImg>
              </div>
            </VCard>
          </VCol>

          <VCol cols="12" sm="4">
            <VCard color="#B49239" theme="dark" class="rounded-xl" height="150">
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <VCardTitle class="text-h5 mt-10">Airbus 811</VCardTitle>
                  <VCardSubtitle>$620</VCardSubtitle>
                </div>
                <VImg src="av.png" class="mr-4 mt-5" absolute></VImg>
              </div>
            </VCard>
          </VCol>

          <VCol cols="12" sm="4">
            <VCard color="#849239" theme="dark" class="rounded-xl" height="150">
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <VCardTitle class="text-h5 mt-10">Total Flights</VCardTitle>
                  <VCardSubtitle>850</VCardSubtitle>
                </div>
                <VImg src="map.png" class="mr-4 mt-5" absolute></VImg>
              </div>
            </VCard>
          </VCol>

          <VCol cols="12" sm="4" class="mt-n4">
            <VCard class="mx-auto" style="height: fit-content">
              <VCardItem title="Doughnut">
                <DoughtnutMain />
              </VCardItem>
            </VCard>
          </VCol>

          <VCol cols="12" sm="8" class="mt-n4">
            <VCard class="mx-auto" style="height: fit-content">
              <VCardItem>
                <BubbleMain />
              </VCardItem>
            </VCard>
          </VCol>

          <VCol cols="12" sm="8" class="mt-n4">
            <VCard class="mx-auto">
              <VCardItem title="Last Trips">
                <template v-slot:subtitle>Overview of lastest Month</template>
              </VCardItem>
              <VCardText class="py-0 mt-n4">
                <VRow align="center" no-gutters>
                  <VCol class="" cols="12">
                    <VList lines="two">
                      <VListItem
                        v-for="folder in folders"
                        :key="folder.title"
                        :title="folder.title"
                        :subtitle="folder.subtitle"
                      >
                        <template v-slot:prepend>
                          <VAvatar color="">
                            <VImg :src="folder.img" alt="John"></VImg>
                          </VAvatar>
                        </template>

                        <template v-slot:append>
                          <VBtn size="large" color="#B49239" icon="mdi mdi-airplane-off"></VBtn>
                        </template>
                      </VListItem>
                    </VList>
                  </VCol>
                </VRow>
              </VCardText>
            </VCard>
          </VCol>

          <v-col cols="12" sm="4" class="mt-n4">
            <v-card style="height: 150px">
              <v-card-item>
                <BarMain class="mt-n4" />
              </v-card-item>
              <v-card-text class="py-0"> </v-card-text>
            </v-card>
          </v-col>
        </VRow>
      </VContainer>
    </VMain>
  </VApp>
</template>
