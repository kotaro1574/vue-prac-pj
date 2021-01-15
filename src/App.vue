<template>
  <div id="app">
    <input type="text" v-model="keyword">
    <table>
      <tr v-for="(user, index) in filteredUsers" :key="index">
        <td>{{index+1}}</td>
        <td>{{user.name}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      keyword: "",
      users: [
        {
          name: "佐藤"
        },
        {
          name: "山田"
        },
        {
          name: "鈴木"
        },
        {
          name: "田中"
        }
      ]
    };
  },
  computed: {
    filteredUsers() {
      const users = [];
      for (const i in this.users) {
        const user = this.users[i];
        if (user.name.indexOf(this.keyword) !== -1) {
          users.push(user);
        }
      }
      return users;
    }
  }
};
</script>

<style>
</style>
