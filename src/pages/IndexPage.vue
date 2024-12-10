<template>
  <q-page class="flex q-pa-md justify-center">
    <div class="row">
      <div>
        <q-input class="col q-mx-sm" :v-model="submit.name" label="名前" ></q-input>
        <q-input class="col q-mx-sm" :v-model="submit.hurigana" label="ふりがな"></q-input>
        <q-select class="col q-mx-sm" :v-model="submit.職業" :options="options" label="職業" />
        <q-file
          v-model="files"
          label="Pick files"
          filled
          counter
          :counter-label="counterLabelFn"
          max-files="3"
          multiple
          style="max-width: 300px"
        >
          <template v-slot:prepend>
            <q-icon name="attach_file" />
          </template>
        </q-file>

      </div>
      <q-btn label="Submit" type="submit" color="primary"/>
    </div>

  </q-page>
</template>

<script setup>
//
import {ref} from "vue"

let submit = {
  name : ref(""),
  hurigana : ref(""),
  職業 : ref()
}
let options = ["会社員","学生"]

</script>
