<script setup>
import { ref } from 'vue'
import Checkbox from "../../../Checkbox.vue";

const props = defineProps([
  'platform',
  'config',
])

const config = ref(props.config)
</script>

<template>
  <div id="videotoolbox-encoder" class="config-page">
    <!-- Presets -->
    <div class="mb-3">
      <label for="vt_coder" class="form-label">{{ $t('config.vt_coder') }}</label>
      <select id="vt_coder" class="form-select" v-model="config.vt_coder">
        <option value="auto">{{ $t('config.ffmpeg_auto') }}</option>
        <option value="cabac">{{ $t('config.coder_cabac') }}</option>
        <option value="cavlc">{{ $t('config.coder_cavlc') }}</option>
      </select>
    </div>
    <div class="mb-3">
      <label for="vt_software" class="form-label">{{ $t('config.vt_software') }}</label>
      <select id="vt_software" class="form-select" v-model="config.vt_software">
        <option value="auto">{{ $t('_common.auto') }}</option>
        <option value="disabled">{{ $t('_common.disabled') }}</option>
        <option value="allowed">{{ $t('config.vt_software_allowed') }}</option>
        <option value="forced">{{ $t('config.vt_software_forced') }}</option>
      </select>
    </div>
    <Checkbox class="mb-3"
              id="vt_realtime"
              desc=""
              locale-prefix="config"
              v-model="config.vt_realtime"
              default="true"
    ></Checkbox>
  </div>
</template>

<style scoped>

</style>
