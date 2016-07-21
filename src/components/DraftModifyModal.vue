<template>
  <div class="modal" v-bind:class="{ 'active': show }">
    <div class="modal-overlay"></div>
    <div class="modal-container">

      <div class="modal-header">
        <button class="btn btn-clear float-right" @click="close"></button>
        <div class="modal-title">{{ horse.name }}</div>
      </div>


      <template v-if="action == 'default'">
      <div class="modal-body">
        <div class="content">
          <div class="columns">
            <div class="column col-12">
              <button class="btn btn-lg btn-block"  @click="switchEdit">Edit</button>
            </div>
          </div>
          <div class="columns">
            <div class="column col-12">
              <button class="btn btn-lg btn-block" @click="switchDelete">Delete</button>
            </div>
          </div>
        </div>
      </div>
      </template>

      <!-- Edit -->
      <template v-if="action == 'edit'">
      <div class="modal-body">
        <div class="content">
          TODO: Edit Form
        </div>
      </div>
      <div class="modal-footer">
        <button class="btn btn-link" @click="update">OK</button>
        <button class="btn btn-link" @click="show = false">Close</button>
      </div>
      </template>

      <!-- Delete -->
      <template v-if="action == 'delete'">
      <div class="modal-body">
        <div class="content">Are you sure?</div>
      </div>
      <div class="modal-footer">
        <button class="btn btn-link" @click="delete">OK</button>
        <button class="btn btn-link" @click="close">Close</button>
      </div>
      </template>


    </div>
  </div>
</template>

<script>
export default {
  props: ['horse', 'show'],
  data() {
    return {
      action: 'default',
    };
  },
  methods: {
    switchDelete() {
      this.action = 'delete';
      window.console.log(this.action);
    },
    switchEdit() {
      this.action = 'edit';
    },
    delete() {
      this.show = false;
    },
    update() {
      this.show = false;
    },
    close() {
      this.show = false;
      this.action = 'default';
    },
  },
};
</script>
