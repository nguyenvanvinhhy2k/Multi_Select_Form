<template>
  <div class="" style="position: relative">
    <input
      @click="showUsers"
      class="st-upload"
      type="text"
      placeholder="選択してください"
    />
    <div class="drop-img">
      <span @click="showUsers">
        <img style="width: 10px" src="../assets/select.png" alt="" />
      </span>
    </div>

    <div class="data" v-if="show">
      <ul v-for="user in users" :key="user.id">
        <li>{{ user.name }}</li>
      </ul>
    </div>

   
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      users: [
        { id: 1, name: "グエンヴァンヴィン" },
        { id: 2, name: "グエン・チエン" },
        { id: 3, name: "個人情報につき、そ" },
        { id: 4, name: "職務中に知り" },
        { id: 5, name: "得た第三者の個" },
      ],
    };
  },
  methods: {
    showUsers() {
      this.show = !this.show;
    },
  },
};
</script>

<style scoped>
.st-upload {
  background: #fff;

  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  border-radius: 4px;
  width: 100%;
  padding: 1rem 0.71rem;
}
.data {
  background: #fff;
  border: 1px solid #dcdcdc;
}
.drop-img {
  position: absolute;
  top: 27%;

  right: 12px;
}
.select-icon {
  display: block;
  width: 0;
  height: 0;
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-top: 8px solid #666;
  position: absolute;
  top: 50%;
  right: 1.5rem;
  -webkit-transform: translateY(-50%);
  transform: translateY(-50%);
}
ul:hover {
  background: #dcdcdc;
}
ul {
  margin: 0;
  padding: 0 4px;
}
li {
  padding: 4px 4px;
  font-size: 15px;
}
</style>
