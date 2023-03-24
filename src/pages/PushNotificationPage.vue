<template>
  <q-page class="flex flex-center">
    <div class="row">
      <div class="col-12">
        <q-card class="my-card">
          <q-card-section class="bg-primary text-white">
            <div class="text-h4">WeThinkCode_</div>
            <div class="text-h6 text-bold q-ml-xs">{{sourcingTextTitle}}</div>
          </q-card-section>

          <q-separator />
          <q-form
            @submit="sourcingOnSubmit"
            @reset="sourcingOnReset"
            class="q-gutter-sm q-pa-sm"
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
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";
import axios from "axios";

export default defineComponent({
  name: "PushNotificationPage",

  setup() {
    const host = ref("http://localhost:3000");
    // const host = ref("https://wethinkcode-2-l4603293.deta.app")

    const sourcingTextTitle = ref(null);
    const sourcingTextBody = ref(null);

    return {
      host,

      sourcingTextTitle,
      sourcingTextBody,

      async sourcingOnSubmit() {
        try {
          await axios.post(host.value + "/wethinkcode", {
            title: sourcingTextTitle.value,
            body: sourcingTextBody.value,
          });
        } catch (err) {
          console.log(err);
        }
      },

      sourcingOnReset() {
        (sourcingTextTitle.value = null), (sourcingTextBody.value = null);
      },
    };
  },
});
</script>
<style scoped>
.my-card{
  width: 600px;
  margin-top: -300px;
}
</style>
