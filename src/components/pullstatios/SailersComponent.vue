<!-- eslint-disable prettier/prettier -->
<!-- eslint-disable no-unused-vars -->
<!-- eslint-disable no-unused-vars -->

<template>
  <div class="container">
    <div class="position-relative">
      <h3 class="font-w fw-bolder shadow p-3 mb-5 bg-body rounded">
        <span class="text-success text-large">S</span>ailers polling station members
        <span class="top-0 translate-middle badge rounded-pill bg-danger"> 99+ </span>
      </h3>
    </div>
    <div class="d-flex justify-content-between my-2px">
      <div class="mr-4 mt-4 mb-2">
        <form class="d-flex">
          <input
            class="form-control me-2"
            type="search"
            placeholder="Search"
            aria-label="Search"
          />
          <button class="btn btn-outline-success" type="submit">Search</button>
        </form>
      </div>

      <div class="d-flex justify-content-between my-0/4px">
        <button
          @click="leadersDialogToggle"
          class="btn btn-outline-success m-1 ml-5 mt-4 mb-4 px-3"
        >
          Leaders
        </button>
        <button type="button" class="btn btn-outline-success m-3 ml-5 mt-4 mb-4 px-3">
          Meetings
        </button>
        <button
          @click="dialoState"
          type="button"
          class="btn btn-success ml-5 mt-4 mb-4 px-3"
        >
          Add Member
        </button>
      </div>
    </div>

    <div class="card mt-0">
      <div class="content p-3">
        <table class="table">
          <thead class="table-light">
            <tr>
              <th scope="col">#</th>
              <th scope="col">Full Name</th>
              <th scope="col">Phone Number</th>
              <th scope="col">Membership Number</th>
              <th scope="col">GPS</th>
              <th scope="col">Action</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <th scope="row">1</th>
              <td>{{ membersInput.full_name }}</td>
              <td>{{ membersInput.phone }}</td>
              <td>{{ membersInput.membership_number }}</td>
              <td>{{ membersInput.gps }}</td>
              <td>edit</td>
            </tr>
            <tr>
              <th scope="row">2</th>
              <td>{{ membersInput.full_name }}</td>
              <td>{{ membersInput.phone }}</td>
              <td>{{ membersInput.membership_number }}</td>
              <td>{{ membersInput.gps }}</td>
              <td>edit</td>
            </tr>
            <tr>
              <th scope="row">3</th>
              <td>{{ membersInput.full_name }}</td>
              <td>{{ membersInput.phone }}</td>
              <td>{{ membersInput.membership_number }}</td>
              <td>{{ membersInput.gps }}</td>
              <td>edit</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
    <Modal
      :okButton="{ text: 'h', onclick: () => {}, loading: true }"
      :modalClass="bg - success"
      v-model:visible="isVisible"
      title="Add member"
      :cancelButton="{
        text: 'no',
        onclick: () => {
          isVisible = false;
        },
        loading: true,
      }"
    >
      <div>
        <form action="/action_page.php">
          <input type="text" id="name" name="firstname" placeholder="Your name.." />
          <input type="text" id="phone" name="phone" placeholder="Your phone number.." />
          <input
            type="text"
            id="membership"
            name="membership"
            placeholder="Your membership number.."
          />
          <input type="text" id="gps" name="gps" placeholder="Your GPS address.." />
        </form>
      </div>
    </Modal>
    <LeadersComponent v-if="leadersDialog" />
  </div>
</template>
<script setup>
import { ref, reactive } from "vue";
// eslint-disable-next-line no-unused-vars
import LeadersComponent from "../Leaders/LeadersComponent.vue";
// eslint-disable-next-line no-unused-vars
import { Modal } from "usemodal-vue3";
// eslint-disable-next-line no-unused-vars
let isVisible = ref(false);
// eslint-disable-next-line no-unused-vars
let leadersDialog = ref(false);

// eslint-disable-next-line no-unused-vars
let membersInput = reactive(
  {
    full_name: "Francis Coffie",
    phone: "0248360435",
    membership_number: "ndc-1451445",
    gps: "WS-1254552",
  },
  {
    full_name: "Nati Senior",
    phone: "0248360455",
    membership_number: "ndc-1451545",
    gps: "WS-12545555",
  }
);
// eslint-disable-next-line no-unused-vars
const dialoState = () => {
  isVisible.value = !isVisible.value;
  leadersDialog.value = !leadersDialog.value;
};
// eslint-disable-next-line no-unused-vars
const leadersDialogToggle = () => {
  leadersDialog.value = !leadersDialog.value;
};
</script>

<style scoped>
.form-control {
  width: 50%;
}

input[type="text"],
select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-sizing: border-box;
}

.badge {
  margin-left: 15px;
  --bs-badge-font-size: 0.5em;
}

div {
  border-radius: 8px;
  padding: 20px;
}
.phone {
  margin-right: 5px;
}
h3 {
  font-weight: 900;
  font-size: 2em;
  color: #42b983;
  text-shadow: 2px 2px black;
}
.text-large {
  text-shadow: #ccc;
  font-weight: bolder;
  border-color: black;
}
.card {
  z-index: 1;
}
</style>
