<template>
  <div id="app">
    <nav class="navbar navbar-dark bg-dark">
      <div id="nav">
        <router-link to="/">
          <b-icon
            icon="basket"
            style="width: 50px; height: 30px"
          ></b-icon>
        </router-link>
        |
        <router-link to="/about">Product</router-link>
      </div>
      <div>
        <router-link to="/User">
          <button
            type="button "
            class="btn btn-outline-success mr-1"
            @click="submit()"
          >
            confirm
          </button>
          <button
            type="button"
            class="btn btn-outline-danger"
            @click="cleardata()"
          >
            Clear
          </button>
        </router-link>
      </div>
    </nav>
    <router-view

    />
  </div>
</template>
<script>
import { mapMutations } from 'vuex';
export default {
 computed: {
   ...mapMutations(["clear", "Submit"]),
 },

 /* methods: {
    //คิดเงินรวมทั้งหมด
    submit() {
      this.Data = this.select;
      this.Total = 0;
      for (var i = 0; i < this.Data.length; i++) {
        this.Total = this.Total + this.Data[i].Total;
      }
    },
    cleardata() {
      this.Total = 0;
      this.Data = [{}];
      this.select = [{}];
    },
    menuorder(value) {
      this.select = value;
    },
    AddMenu(value) {
      this.Menuitem.push(value);
    }
  }*/
};
</script>

<style>


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #e637dd;
}

#nav {
  padding: 10px;
}

#nav a {
  font-weight: bold;
  color: #ecd25d;
}

#nav a.router-link-exact-active {
  color: #1bc2b4;
}
</style>
