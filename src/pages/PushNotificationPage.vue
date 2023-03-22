<template>
  <q-page class="flex flex-center">
    <div class="row justify-center">
      <div class="col-8 q-mb-lg q-mt-xl">
        <q-card class="my-card">
          <q-card-section class="bg-primary text-white">
            <div class="text-h4">Sourcing Team</div>
            <div class="text-subtitle1">WeThinkCode_</div>
          </q-card-section>

          <q-separator />
          <q-form
            @submit="sourcingOnSubmit"
            @reset="sourcingOnReset"
            class="q-gutter-md q-pa-sm"
          >
            <q-input
              square
              outlined
              v-model="sourcingTextTitle"
              label="Notification Title"
            />
            <q-input
              square
              outlined
              v-model="sourcingTextBody"
              label="Notification Body"
            />

            <q-card-actions align="right">
              <q-btn flat label="Submit" type="submit" color="primary" />
              <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
            </q-card-actions>
          </q-form>
        </q-card>
      </div>

      <div class="col-8 q-mb-lg">
        <q-card class="my-card">
          <q-card-section class="bg-primary text-white">
            <div class="text-h4">Performance Team</div>
            <div class="text-subtitle1">WeThinkCode_</div>
          </q-card-section>

          <q-separator />
          <q-form
            @submit="performanceOnSubmit"
            @reset="performanceOnReset"
            class="q-gutter-md q-pa-sm"
          >
            <q-input
              square
              outlined
              v-model="performanceTextTitle"
              label="Notification Title"
            />
            <q-input
              square
              outlined
              v-model="performanceTextBody"
              label="Notification Body"
            />

            <q-card-actions align="right">
              <q-btn flat label="Submit" type="submit" color="primary" />
              <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
            </q-card-actions>
          </q-form>
        </q-card>
      </div>

      <div class="col-8 q-mb-lg">
        <q-card class="my-card">
          <q-card-section class="bg-primary text-white">
            <div class="text-h4">LMS Updates</div>
            <div class="text-subtitle1">WeThinkCode_</div>
          </q-card-section>

          <q-separator />
          <q-form @submit="lmsOnSubmit" @reset="lmsOnReset" class="q-gutter-md q-pa-sm">
            <q-input square outlined v-model="lmsTextTitle" label="Notification Title" />
            <q-input square outlined v-model="lmsTextBody" label="Notification Body" />

            <q-card-actions align="right">
              <q-btn flat label="Submit" type="submit" color="primary" />
              <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
            </q-card-actions>
          </q-form>
        </q-card>
      </div>

      <div class="col-8 q-mb-lg">
        <q-card class="my-card">
          <q-card-section class="bg-primary text-white">
            <div class="text-h4">Students</div>
            <div class="text-subtitle1">WeThinkCode_</div>
          </q-card-section>

          <q-separator />
          <q-form
            @submit="studentsOnSubmit"
            @reset="studentsOnReset"
            class="q-gutter-md q-pa-sm"
          >
            <q-input
              square
              outlined
              v-model="studentsTextTitle"
              label="Notification Title"
            />
            <q-input
              square
              outlined
              v-model="studentsTextBody"
              label="Notification Body"
            />

            <q-card-actions align="right">
              <q-btn flat label="Submit" type="submit" color="primary" />
              <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
            </q-card-actions>
          </q-form>
        </q-card>
      </div>

      <div class="col-8 q-mb-lg">
        <q-card class="my-card">
          <q-card-section class="bg-primary text-white">
            <div class="text-h4">Alumni Jobs Portal</div>
            <div class="text-subtitle1">WeThinkCode_</div>
          </q-card-section>

          <q-separator />
          <q-form
            @submit="alumniOnSubmit"
            @reset="alumniOnReset"
            class="q-gutter-md q-pa-sm"
          >
            <q-input
              square
              outlined
              v-model="alumniTextTitle"
              label="Notification Title"
            />
            <q-input square outlined v-model="alumniTextBody" label="Notification Body" />

            <q-card-actions align="right">
              <q-btn flat label="Submit" type="submit" color="primary" />
              <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
            </q-card-actions>
          </q-form>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";
import axios from "axios";

export default defineComponent({
  name: "PushNotificationPage",

  setup() {
    // const host = ref("localhost:3000");
    const host = ref("wethinkcode-2-l4603293.deta.app")

    const sourcingTextTitle = ref(null);
    const sourcingTextBody = ref(null);

    const performanceTextTitle = ref(null);
    const performanceTextBody = ref(null);

    const lmsTextTitle = ref(null);
    const lmsTextBody = ref(null);

    const studentsTextTitle = ref(null);
    const studentsTextBody = ref(null);

    const alumniTextTitle = ref(null);
    const alumniTextBody = ref(null);
    return {
      host,

      sourcingTextTitle,
      sourcingTextBody,

      performanceTextTitle,
      performanceTextBody,

      lmsTextTitle,
      lmsTextBody,

      studentsTextTitle,
      studentsTextBody,

      alumniTextTitle,
      alumniTextBody,

      async sourcingOnSubmit() {
        try {
          await axios.post("http://" + host.value + "/wethinkcode", {
            title: sourcingTextTitle.value,
            body: sourcingTextBody.value,
          });
        } catch (err) {
          console.log(err);
        }
      },
      async performanceOnSubmit() {
        try {
          await axios.post("http://" + host.value + "/wethinkcode", {
            title: performanceTextTitle.value,
            body: performanceTextBody.value,
          });
        } catch (err) {
          console.log(err);
        }
      },
      async lmsOnSubmit() {
        try {
          await axios.post("http://" + host.value + "/wethinkcode", {
            title: lmsTextTitle.value,
            body: lmsTextBody.value,
          });
        } catch (err) {
          console.log(err);
        }
      },
      async studentsOnSubmit() {
        try {
          await axios.post("http://" + host.value + "/wethinkcode", {
            title: studentsTextTitle.value,
            body: studentsTextBody.value,
          });
        } catch (err) {
          console.log(err);
        }
      },
      async alumniOnSubmit() {
        try {
          await axios.post("http://" + host.value + "/wethinkcode", {
            title: alumniTextTitle.value,
            body: alumniTextBody.value,
          });
        } catch (err) {
          console.log(err);
        }
      },

      sourcingOnReset() {
        (sourcingTextTitle.value = null), (sourcingTextBody.value = null);
      },
      performanceOnReset() {
        (performanceTextTitle.value = null), (performanceTextBody.value = null);
      },
      lmsOnReset() {
        (lmsTextTitle.value = null), (lmsTextBody.value = null);
      },
      studentsOnReset() {
        (studentsTextTitle.value = null), (studentsTextBody.value = null);
      },
      alumniOnReset() {
        (alumniTextTitle.value = null), (alumniTextBody.value = null);
      },
    };
  },
});
</script>
