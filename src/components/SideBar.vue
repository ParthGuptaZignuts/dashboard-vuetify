<script setup lang="ts">
import { ref } from "vue";
import {
  VAvatar,
  VIcon,
  VListItem,
  VListItemTitle,
  VNavigationDrawer,
  VProgressCircular,
} from "vuetify/components";

interface Link {
  text: string;
  icon: string;
}

const links: Link[] = [
  { text: "DASHBOARD", icon: "mdi mdi-home-outline" },
  { text: "FLIGHTS", icon: "mdi mdi-airplane-off" },
  { text: "WALLET", icon: "mdi mdi-wallet-outline" },
  { text: "REPORTS", icon: "mdi mdi-file-chart-outline" },
  { text: "STATISTICS", icon: "mdi mdi-chart-pie" },
  { text: "SETTINGS", icon: "mdi mdi-cog-outline" },
];

const drawer = ref(null);
</script>

<template>
    <VNavigationDrawer v-model="drawer" color="#425C5A" class="rounded-e-xl">
      <VSheet color="#3D5654" class="pa-4 rounded-te-xl text-center">
        <VProgressCircular
          model-value="80"
          color="#B49239"
          :size="100"
          :width="2"
          class=""
        >
          <VAvatar size="85">
            <VImg src="1.jpg" alt="John"></VImg>
          </VAvatar>
        </VProgressCircular>
  
        <div class="mt-4">AAE Ideapro</div>
        <span class="mb-6 text-caption">aae.ideapro@gmail.com</span>
      </VSheet>
  
      <VList>
        <VListItem
          v-for="(item, i) in links"
          :key="i"
          :value="item"
          active-class="border"
          :ripple="false"
        >
          <template v-slot:prepend>
            <VIcon :icon="item.icon" color="#B49239"></VIcon>
          </template>
  
          <VListItemTitle v-text="item.text"></VListItemTitle>
        </VListItem>
      </VList>
      <h5 class="ml-5 text-yellow-darken-2">ACTIVE USERS</h5>
      <VRow align="center" class="spacer ml-16 mt-4" no-gutters>
        <VCol cols="4" sm="2" md="1">
          <VAvatar size="36px">
            <VImg alt="Avatar" src="1.jpg"></VImg>
          </VAvatar>
        </VCol>
        <VCol cols="4" sm="2" md="1">
          <VAvatar size="36px">
            <VImg alt="Avatar" src="2.jpg"></VImg>
          </VAvatar>
        </VCol>
        <VCol cols="4" sm="2" md="1">
          <VAvatar size="36px">
            <VImg alt="Avatar" src="3.jpg"></VImg>
          </VAvatar>
        </VCol>
        <VCol cols="4" sm="2" md="1">
          <VAvatar size="36px">
            <VImg alt="Avatar" src="4.jpg"></VImg>
          </VAvatar>
        </VCol>
        <VCol cols="4" sm="2" md="1">
          <VAvatar size="36px" color="#B49239"> +70 </VAvatar>
        </VCol>
      </VRow>
      <div style="position: relative; z-index: 9999" class="mt-2">
        <VImg src="map.png" contain max-height="100"></VImg>
      </div>
    </VNavigationDrawer>
</template>

