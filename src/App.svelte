<div class="container">
  <div class="login">
    <form on:submit|preventDefault={submit} role="form">
      <div class="field">
        <TextField
          bind:value={$login.username}
          label="Username"
          variant="filled"
          style="width: 100%"
          input$aria-controls="username-helper"
          input$aria-describedby="username-helper"
        />
        <HelperText id="username-helper">Username or email of your account</HelperText>
      </div>

      <div class="field">
        <TextField
          bind:value={$login.password}
          label="Password"
          variant="filled"
          type="password"
          style="width: 100%"
          input$aria-controls="password-helper"
          input$aria-describedby="password-helper"
        />
        <HelperText id="password-helper">Password of your account</HelperText>
      </div>

      <div class="submit">
        <Button
          class="button"
          variant="raised"
          type="submit"
        >
          <Label>Log In</Label>
        </Button>
      </div>
    </form>
  </div>
</div>

<script>
  import Button, {Label, Icon} from '@smui/button';
  import TextField from '@smui/textfield';
  import HelperText from '@smui/textfield/helper-text/index';
  import { login } from './login.store.js';

  function submit() {
    alert(JSON.stringify($login));
  }
</script>

<style>
  .login {
    width: 360px;
    margin: 0 auto;
    margin-top: 10%;
    display: block;
  }

  .login .field {
    display: block;
    width: 100%;
  }

  .login .field:nth-child(2) {
    margin-top: 10px;
  }

  .submit {
    margin-top: 20px;
  }

  .submit :global(.button) {
    width: 100%;
    text-align: center;
  }
</style>