<template>
  <div class="flex">
    <div class="left">
      <SideNav />
    </div>
    <div class="right">
      <div class="title">
        <p>ホーム</p>
      </div>
      <Message />
    </div>
  </div>
</template>

<script>
import SideNav from "../components/SideNav";
import Message from "../components/Message";
export default {
  components: {
    SideNav,
    Message
  }
}
</script>

<style scoped>
.flex {
  display: flex;
}
.left {
  width: 22%;
  height: 100vh;
}
.right {
  width: 78%;
  height: 100vh;
}
.title {
  border-bottom: 1px solid #fff;
  border-left: 1px solid #fff;
  padding: 15px;
}
.title p {
  font-size: 20px;
  font-weight: bold;
}

</style>
