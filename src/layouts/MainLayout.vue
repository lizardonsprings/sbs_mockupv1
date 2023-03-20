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
        <q-space />
        <q-space />

        <q-input v-model="search" placeholder="Search">
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

    <q-drawer width="200" v-model="leftDrawerOpen" show-if-above bordered>
      <div style="max-width: 350px">
        <div class="mainlogo">
          <img src="budgets2.png" width="180" />
        </div>
        <q-list>
          <q-expansion-item
            group="somegroup"
            icon="settings"
            label="Settings"
            default-opened
            header-class="text-blue"
          >
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                Quidem, eius reprehenderit eos corrupti commodi magni quaerat ex
                numquam, dolorum officiis modi facere maiores architecto
                suscipit iste eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>

          <q-separator />

          <q-expansion-item
            group="somegroup"
            icon="group"
            label="Staffing"
            header-class="text-teal"
          >
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                Quidem, eius reprehenderit eos corrupti commodi magni quaerat ex
                numquam, dolorum officiis modi facere maiores architecto
                suscipit iste eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>

          <q-separator />

          <q-expansion-item
            group="somegroup"
            icon="post_add"
            label="Planning"
            header-class="text-purple"
          >
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                Quidem, eius reprehenderit eos corrupti commodi magni quaerat ex
                numquam, dolorum officiis modi facere maiores architecto
                suscipit iste eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>

          <q-separator />

          <q-expansion-item
            group="somegroup"
            icon="assignment"
            label="Reporting"
            header-class="text-orange"
          >
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                Quidem, eius reprehenderit eos corrupti commodi magni quaerat ex
                numquam, dolorum officiis modi facere maiores architecto
                suscipit iste eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>
          <q-separator />

          <q-expansion-item
            group="somegroup"
            icon="pending_actions"
            label="Monitoring"
            header-class="text-red"
          >
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                Quidem, eius reprehenderit eos corrupti commodi magni quaerat ex
                numquam, dolorum officiis modi facere maiores architecto
                suscipit iste eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>
          <q-separator />

          <q-expansion-item
            group="somegroup"
            icon="holiday_village"
            label="Multi-School"
            header-class="text-green"
          >
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                Quidem, eius reprehenderit eos corrupti commodi magni quaerat ex
                numquam, dolorum officiis modi facere maiores architecto
                suscipit iste eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>
          <q-separator />

          <q-expansion-item
            group="somegroup"
            icon="edit_note"
            label="Reforecasting"
            header-class="text-pink"
          >
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                Quidem, eius reprehenderit eos corrupti commodi magni quaerat ex
                numquam, dolorum officiis modi facere maiores architecto
                suscipit iste eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>
        </q-list>
      </div>
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
