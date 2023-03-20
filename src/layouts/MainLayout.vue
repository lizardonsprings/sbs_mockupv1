<template>
  <q-layout view="lHh Lpr lFf">
    <q-header>
      <q-toolbar>
        <q-breadcrumbs class="text-blue" active-color="black">
          <q-breadcrumbs-el
            label="Great Academies Trust"
            icon="home"
            to="/"
            @click="onSchoolClick"
          />
          <q-breadcrumbs-el
            label="Initial Budget 2023/24"
            icon="assignment"
            to="/"
            @click="onBudgetClick"
          />
          <q-breadcrumbs-el label="Planning" icon="widgets" />
          <q-breadcrumbs-el label="Budget Entries" />
        </q-breadcrumbs>

        <q-space />
        <q-space />
        <q-space />

        <q-input v-model="search" placeholder="Search SBS Budgets..">
          <template v-slot:append>
            <q-icon name="search" />

            <q-space />
          </template>
        </q-input>

        <q-space />

        <div>
          <q-btn
            flat
            dense
            round
            icon="apps"
            aria-label="Menu"
            color="blue"
            @click="toggleLeftDrawer"
          />
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="drawer" show-if-above :width="200" :breakpoint="500">
      <q-scroll-area class="fit">
        <div class="mainlogo">
          <img src="budgets2.png" width="180" />
        </div>
        <q-list padding class="menu-list">
          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="inbox" />
            </q-item-section>

            <q-item-section> Settings </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="star" />
            </q-item-section>

            <q-item-section> Staffing </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="send" />
            </q-item-section>

            <q-item-section> Planning </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="drafts" />
            </q-item-section>

            <q-item-section> Reporting </q-item-section>
          </q-item>
        </q-list>
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "MainLayout",

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>
