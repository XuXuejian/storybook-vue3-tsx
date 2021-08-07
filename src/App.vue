<script lang="tsx">
import { defineComponent, Fragment } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import imgSrc from "./assets/logo.png";

export default defineComponent({
  name: "App",
  components: {
    HelloWorld,
  },
  setup() {
    return () => (
      <Fragment>
        <img alt="Vue logo" src={imgSrc} />
        <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
      </Fragment>
    );
  },
});
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
