<script>
  import { goto } from "$app/navigation";

  // Function to navigate to the /signup page
  const navigateToSignup = () => {
    goto("/signup");
  };
</script>

<main>
  <h1>Welcome to Our Application!</h1>
  <p>
    We are excited to have you here. Click the button below to get started with
    signing up.
  </p>
  <button on:click={navigateToSignup}>Go to Signup</button>
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    text-align: center;
  }

  button {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    margin-top: 20px;
  }
</style>
