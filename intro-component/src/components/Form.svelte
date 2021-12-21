<div id="form">
    <div id="try">
        <p>
            <span class="emphasized">Try it free 7 days</span> then $20/mo. thereafter
        </p>
    </div>
    <div id="trial-form">
        <form>
            <div class="form-field">
                <input
                    type="text"
                    name="first-name"
                    placeholder="First Name"
                    required
                />
            </div>
            <div class="form-field">
                <input
                    type="text"
                    name="last-name"
                    placeholder="Last Name"
                    required
                />
            </div>
            <div class="form-field">
                <input
                    type="email"
                    name="email"
                    placeholder="Email Address"
                    required
                />
            </div>
            <div class="form-field">
                <input
                    type="password"
                    name="password"
                    placeholder="Password"
                    required
                />
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
    }
    .form-field {
        margin-bottom: 20px;
        width: 100%;
    }
    .form-field > input {
        width: 100%;
        padding: 15px 30px;
        border: 1px solid rgb(217, 217, 217);
        border-radius: 5px;
        font-weight: 600;
        color: rgb(52, 51, 55);
    }
    .form-field > input:focus {
        border: 1px solid rgb(86, 81, 112);
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
    }
</style>
