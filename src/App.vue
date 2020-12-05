<template>
  <div id="app">
    <input v-model="message" placeholder="edit me" />
    <p>Message is: {{ message }}</p>
    <p><button @click="message = 'form'">set message to form</button></p>
    <hr />
    复选框： 爱好：{{ x }}
    <label>
      <input type="checkbox" v-model="x" :value="1" />
      <span>看书</span>
    </label>
    <label>
      <input type="checkbox" v-model="x" :value="2" />
      <span>写码</span>
    </label>
    <label>
      <input type="checkbox" v-model="x" :value="3" />
      <span>打球</span>
    </label>
    <hr />
    单选框： 你现在在干嘛：{{ y }}
    <label>
      <input name="now" type="radio" v-model="y" :value="1" />
      <span>看书</span>
    </label>
    <label>
      <input name="now" type="radio" v-model="y" :value="2" />
      <span>写码</span>
    </label>
    <label>
      <input name="now" type="radio" v-model="y" :value="3" />
      <span>打球</span>
    </label>

    <hr />
    下拉列表：{{ z }}
    <select v-model="z">
      <option value>-</option>
      <option v-for="item in array" :value="item.value" :key="item.value">
        {{ item.text }}
      </option>
    </select>

    <hr />
    登录：
    <form>
      <!-- 自动回车刷新，form标签 + 一个按钮 
  如果不想要页面刷新 保存数据：
  监听form的submit事件
    <form @submit.prevent="onSubmit">
      ...</form>
      methods:{
    onSubmit(){
      console.log(this.user);
    }
  },
   -->
      {{ user }}
      <hr />
      <label>
        <span>用户名</span>
        <input type="text" v-model.trim="user.username" />
      </label>
      <label>
        <span>密码</span>
        <input type="password" v-model.trim="user.password" />
      </label>
      <button type="submit">登录</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      user: {
        username: "",
        password: "",
      },
      array: [
        { text: "看书", value: 1 },
        { text: "写码", value: 2 },
        { text: "打球", value: 3 },
      ],
      z: "",
      y: "",
      x: [],
      message: `hi`,
    };
  },
  components: {},
};
</script>

