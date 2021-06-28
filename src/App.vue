<script>
import { styled } from "@egoist/vue-emotion";
import TextBox from "./components/TextBox";
import InputValidation from "./components/InputValidation";

export default {
  name: "App",
  components: {
    TextBox,
    InputValidation,
  },
  data() {
    return {
      validationType: "email",
    };
  },
  methods: {
    getValidationType(type) {
      this.validationType = type;
    },
  },
  render() {
    const WrapperDiv = styled("div")`
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    `;

    // {this.validationType === null ? (
    //       <TextBox getValidationType={this.getValidationType} />
    //     ) : (
    //       <InputValidation validationType={this.validationType} />
    // )}

    return (
      <WrapperDiv>
        <p>Default input box :</p>
        <TextBox getValidationType={this.getValidationType} />
        <p>Email Validation input box :</p>
        <InputValidation
          uniqueId={"email-validator"}
          placeholder={"Email"}
          validationType={"email"}
        />
        <p>URL Validation input box :</p>
        <InputValidation
          uniqueId={"url-validator"}
          placeholder={"URL"}
          validationType={"url"}
        />
        <p>Phone Validation input box :</p>
        <InputValidation
          uniqueId={"phone-validator"}
          placeholder={"Phone"}
          validationType={"phone"}
        />
      </WrapperDiv>
    );
  },
};
</script>
