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
          <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md q-pa-sm">
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
          <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md q-pa-sm">
            <q-input square outlined v-model="performanceTextTitle" label="Notification Title" />
            <q-input square outlined v-model="performanceTextBody" label="Notification Body" />

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
          <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md q-pa-sm">
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
          <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md q-pa-sm">
            <q-input square outlined v-model="studentsTextTitle" label="Notification Title" />
            <q-input square outlined v-model="studentsTextBody" label="Notification Body" />

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
          <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md q-pa-sm">
            <q-input square outlined v-model="alumniTextTitle" label="Notification Title" />
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
import { defineComponent } from "vue";
export default defineComponent({
  name: "IndexPage",

  sourcingTextTitle: "",
  sourcingTextBody: "",

  performanceTextTitle: "",
  performanceTextBody: "",

  lmsTextTitle: "",
  lmsTextBody: "",

  studentsTextTitle: "",
  studentsTextBody: "",

  alumniTextTitle: "",
  alumniTextBody: "",
});
</script>
