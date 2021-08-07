<script lang="tsx">
import "./button.css";
import { reactive, computed, defineComponent } from "vue";

export default defineComponent({
  name: "my-button",

  props: {
    label: {
      type: String,
      required: true,
    },
    primary: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      validator: function (value: string) {
        return ["small", "medium", "large"].indexOf(value) !== -1;
      },
    },
    backgroundColor: {
      type: String,
    },
  },

  emits: ["click"],

  setup(props: any, { emit }) {
    props = reactive(props);
    const classes = computed(() => ({
      "storybook-button": true,
      "storybook-button--primary": props.primary,
      "storybook-button--secondary": !props.primary,
      [`storybook-button--${props.size || "medium"}`]: true,
    }));
    const style = computed(() => ({
      backgroundColor: props.backgroundColor,
    }));

    function onClick() {
      emit("click");
    }
    return () => (
      <button
        type="button"
        class={classes.value}
        onClick={onClick}
        style={style.value}
      >
        {props.label}
      </button>
    );
  },
});
</script>
