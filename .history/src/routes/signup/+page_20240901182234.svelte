<script>
  import { goto } from "$app/navigation";
  import { z } from "zod";
  let email = "";
  let password = "";
  const emailSchema = z
    .string()
    .email({ message: "Kindly enter a valid Email!" });
  const passwordSchema = z
    .string()
    .min(8, { message: "The password should contain minimum of 8 characters!" })
    .max(10, {
      message: "The password should contain maximum of 10 characters!",
    });
  const validate = () => {
    try {
      emailSchema.parse(email);
      passwordSchema.parse(password);
      return true;
    } catch (error) {
      alert(error.errors[0].message);
      return true;
    }
  };
  const handleSubmit = (event) => {
    event.preventDefault();
    if (!validate) {
    }
  };
</script>

<main></main>

<style>
</style>
