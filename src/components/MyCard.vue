<template>
  <div class="card mb-3" style="min-width:400px;max-width:538px;">
    <div class="row no-gutters">
      <div class="col-md-4">
        <img :src="bookDetail.cover" class="card-img" alt />
      </div>
      <div class="col-md-8">
        <div class="card-body">
          <h5 class="card-title">{{bookDetail.name}}</h5>
          <p class="card-text">{{bookDetail.description}}</p>
          <p class="card-text">
            <small class="text-muted">By {{bookDetail.author}}</small>
          </p>
          <div class="small-box">
            <small class="text-small">DATE: {{bookDetail.date}}</small>
            <small class="text-small rating">
              RATING:
              <b>{{bookDetail.rating}}</b>
            </small>
          </div>
          <div class="small-box">
            <router-link :to="'/edit-book/'+index" class="btn btn-primary">EDIT</router-link>
            <a href="#" @click.prevent="deleteBook(index)" class="btn btn-danger">DELETE</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "MyCard",
  props: ["bookDetail", "index"],
  methods: {
    ...mapActions(["deleteBook"]),
    comfirmDelete() {
      var confirm = window.confirm("Are You sure to delete book");
      if (confirm) this.delelteBook(index);
      else return;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.small-box {
  display: flex;
  justify-content: space-between;
  margin: 16px;
}
.text-small {
  font-size: 14px;
}
.rating {
  font-size: 16px;
  color: red;
}
</style>
