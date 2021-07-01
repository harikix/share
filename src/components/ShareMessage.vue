<template>
  <div class="share">
      <p>シェア</p>
      <textarea v-model="share"></textarea>
      <div @click="send">
          <button>シェアする</button>
      </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      share: "",
    };
  },
  methods: {
    send() {
      if(this.share === "") {
        alert('シェアする内容を入力してください')
      } else {
        axios.post(
          "https://lit-chamber-18338.herokuapp.com/api/shares", {
            user_id: this.$store.state.user.id,
            share: this.share,
          }
        ).then((response) => {
          console.log(response);
          alert('シェアしました');
          this.share = '';
          this.$router.go({
            path: this.$router.currentRoute.path,
            force: true,
          });
        });
      }
    },
  },
}
</script>

<style scoped>
.share {
  margin: 15px;
}
.share textarea {
  width: 95%;
  height: 120px;
  margin: 15px 0;
  border: 1px solid #fff;
  border-radius: 10px;
  background-color: #15202b;
  color: #fff;
  resize: none;
}
button {
  width: 100px;
  text-align: center;
  padding: 8px 0 10px;
  border: 1px solid #fff;
  border-radius: 25px;
  background-color: #5419da;
  display: block;
  margin: 0 0 0 auto;
}
</style>