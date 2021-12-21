<script lang="ts">
    import { slide, fade } from "svelte/transition";
    const emailRegex: RegExp = new RegExp(
        /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
    );
    let firstName: string;
    let lastName: string;
    let email: string;
    let password: string;
    let alertFirstName,
        alertLastName,
        alertEmail,
        alertPassword,
        alertInvalidEmail: boolean = false;
    const submitHandler: (any) => void = (event) => {
        alertFirstName = !firstName;
        alertLastName = !lastName;
        alertEmail = !email;
        alertPassword = !password;
        if (email && !email.match(emailRegex)) {
            alertInvalidEmail = true;
        } else {
            alertInvalidEmail = false;
        }
    };
</script>

<div id="form">
    <div id="try">
        <p>
            <span class="emphasized">Try it free 7 days</span> then $20/mo. thereafter
        </p>
    </div>
    <div id="trial-form">
        <form on:submit|preventDefault={submitHandler} novalidate>
            <div class="form-field">
                <input
                    type="text"
                    name="first-name"
                    placeholder="First Name"
                    bind:value={firstName}
                    class:warning={alertFirstName}
                    required
                />
                {#if alertFirstName}
                    <img
                        src="/assets/icon-error.svg"
                        alt="Error"
                        transition:fade
                    />
                    <p transition:slide>First Name cannot be empty</p>
                {/if}
            </div>
            <div class="form-field">
                <input
                    type="text"
                    name="last-name"
                    placeholder="Last Name"
                    bind:value={lastName}
                    class:warning={alertLastName}
                    required
                />
                {#if alertLastName}
                    <img
                        src="/assets/icon-error.svg"
                        alt="Error"
                        transition:fade
                    />
                    <p transition:slide>Last Name cannot be empty</p>
                {/if}
            </div>
            <div class="form-field">
                <input
                    type="email"
                    name="email"
                    placeholder="Email Address"
                    bind:value={email}
                    class:warning={alertEmail || alertInvalidEmail}
                    required
                />
                {#if alertEmail && !alertInvalidEmail}
                    <img
                        src="/assets/icon-error.svg"
                        alt="Error"
                        transition:fade
                    />
                    <p transition:slide>Email cannot be empty</p>
                {:else if alertInvalidEmail}
                    <img
                        src="/assets/icon-error.svg"
                        alt="Error"
                        transition:fade
                    />
                    <p transition:slide>Looks like this is not an email</p>
                {/if}
            </div>
            <div class="form-field">
                <input
                    type="password"
                    name="password"
                    placeholder="Password"
                    bind:value={password}
                    class:warning={alertPassword}
                    required
                />
                {#if alertPassword}
                    <img
                        src="/assets/icon-error.svg"
                        alt="Error"
                        transition:fade
                    />
                    <p transition:slide>Password cannot be empty</p>
                {/if}
            </div>
            <input type="submit" value="CLAIM YOUR FREE TRIAL" />
        </form>
        <p>
            By clicking the button, you are agreeing to our <span class="term"
                >Terms and Services</span
            >
        </p>
    </div>
</div>

<style>
    #form {
        width: 50%;
        display: flex;
        flex-direction: column;
    }
    #try {
        background-color: rgb(83, 74, 153);
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 10px rgba(0, 0, 0, 0.1);
        margin-bottom: 30px;
    }
    #try > p {
        text-align: center;
        color: white;
        font-weight: 400;
    }
    .emphasized {
        font-weight: 600;
    }
    #trial-form {
        background-color: white;
        border-radius: 10px;
        box-shadow: 0 10px rgba(0, 0, 0, 0.1);
        padding: 36px;
    }
    #trial-form > form {
        display: flex;
        flex-direction: column;
        margin-bottom: 20px;
    }
    #trial-form > p {
        text-align: center;
        color: rgb(174, 174, 182);
        font-size: 12px;
    }
    .term {
        color: rgb(232, 114, 121);
        font-weight: 700;
        cursor: pointer;
    }
    .form-field {
        margin-bottom: 20px;
        width: 100%;
        position: relative;
    }
    .form-field > input {
        width: 100%;
        padding: 15px 30px;
        border: 1px solid rgb(217, 217, 217);
        border-radius: 5px;
        font-weight: 600;
        color: rgb(52, 51, 55);
        transition: border 0.3s, color 0.3s;
    }
    .form-field > input:focus {
        border: 1px solid rgb(86, 81, 112);
    }
    .form-field > p {
        text-align: right;
        color: rgb(232, 114, 121);
        font-style: italic;
        font-size: 12px;
        margin-top: 5px;
    }
    .form-field > img {
        position: absolute;
        right: 40px;
        top: 26px;
        transform: translate(50%, -50%);
    }
    input[type="submit"] {
        cursor: pointer;
        border: none;
        border-radius: 10px;
        background-color: rgb(48, 197, 127);
        padding: 15px 30px;
        box-shadow: 0 5px rgb(74, 162, 123);
        color: white;
        font-size: 18px;
        letter-spacing: 1px;
        font-weight: 400;
        transition: filter 0.3s;
    }
    input[type="submit"]:hover {
        filter: brightness(0.8);
    }
    input[type="submit"]:active {
        filter: brightness(1.2);
    }
    .warning {
        border: 1px solid rgb(203, 130, 128) !important;
        color: rgb(232, 114, 121) !important;
    }
</style>
