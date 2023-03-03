<!-- eslint-disable no-unused-vars -->

<template>
  <div class="container">
    <div class="d-flex justify-content-between">
      <div class="mr-4 mt-4 mb-4">
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
      <!-- Modal -->

      <div class="d-flex justify-content-between">
        <button type="button" class="btn btn-outline-success m-1 ml-5 mt-4 mb-4 px-3">
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

    <div class="card mt-3">
      <div class="content p-3">
        <table class="table">
          <thead class="table-light">
            <tr>
              <th scope="col">#</th>
              <th scope="col">Full Name</th>
              <th scope="col">Phone Number</th>
              <th scope="col">membership Number</th>
              <th scope="col">GPS</th>
              <th scope="col">Action</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <th scope="row">1</th>
              <td>Mark</td>
              <td>Otto</td>
              <td>@mdo</td>
              <td>@mdo</td>
              <td>@mdo</td>
            </tr>
            <tr>
              <th scope="row">2</th>
              <td>Jacob</td>
              <td>Thornton</td>
              <td>@fat</td>
              <td>@fat</td>
              <td>@fat</td>
            </tr>
            <tr>
              <th scope="row">3</th>
              <td>Larry the Bird</td>
              <td>@twitter</td>
              <td>Thornton</td>
              <td>Thornton</td>
              <td>Thornton</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
  <Modal
    v-model:visible="isVisible"
    title="hello"
    cancelButton="{ text: 'no', onclick: () => {}, loading: false }"
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
</template>
<script setup>
import { ref } from "vue";
// eslint-disable-next-line no-unused-vars
import { Modal } from "usemodal-vue3";
// eslint-disable-next-line no-unused-vars
let isVisible = ref(false);

// eslint-disable-next-line no-unused-vars
const dialoState = () => {
  isVisible.value = !isVisible.value;
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

div {
  border-radius: 8px;
  padding: 20px;
}
.phone {
  margin-right: 5px;
}
</style>
