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
      return false;
    }
  };
  const handleSubmit = (event) => {
    event.preventDefault();
    if (validate()) {
      alert("Response Captured!");
    }
  };
</script>

<main>
  <div class="card">
    <h2>Signup</h2>
    <form on:submit={handleSubmit}>
      <div class="form-group">
        <label for="email">Email:</label>
        <input
          type="email"
          id="email"
          bind:value={email}
          placeholder="Enter your email"
        />
      </div>
      <div class="form-group">
        <label for="password">Password:</label>
        <input
          type="password"
          id="password"
          bind:value={password}
          placeholder="Enter your password"
        />
      </div>
      <button type="submit">Signup</button>
    </form>
  </div>
</main>

<style>
  main {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    background-color: #f0f0f0;
  }

  .card {
    background: white;
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    width: 100%;
    max-width: 400px;
    text-align: center;
  }

  .form-group {
    margin-bottom: 1.5rem;
    text-align: left;
  }

  label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: bold;
  }

  input {
    width: 100%;
    padding: 0.75rem;
    font-size: 1rem;
    border-radius: 4px;
    border: 1px solid #ccc;
  }

  button {
    width: 100%;
    padding: 0.75rem;
    font-size: 1rem;
    cursor: pointer;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 4px;
  }

  button:hover {
    background-color: #0056b3;
  }
</style>
