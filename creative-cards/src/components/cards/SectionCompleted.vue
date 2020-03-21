<template>
  <div class="row">
    <div class="form-check form-check-inline">
      <div class="form-check-label">
        <input type="checkbox" class="form-check-input" v-model="checked" @click="sectionCompleted"> Mark section as completed
      </div>
    </div>
  </div>
</template>

<script>
  import { EventBus } from '../../main.js'

  export default {
    data: function() {
      return {
        checked: false
      }
    },
    methods: {
      sectionCompleted: function() {
        this.checked = !this.checked
        EventBus.$emit('mark-as-completed', this.checked)


      }
    }
  }
</script>
