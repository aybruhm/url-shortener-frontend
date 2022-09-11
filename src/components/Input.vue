<template>
    <div class="form-container">
        <form method="POST">

            <!-- When Original URL has been shortened, show this -->
            <div v-if="shortened_url_length > 1">
                <div class="form-group">
                    <input type="text" class="form-control" :value="original_url" disabled>
                </div>

                <div class="form-group">
                    <h4 class="main-subtitle">
                        New URL:
                        <a :href="shortened_url" class="shortened-link">
                            {{ shortened_url }}
                        </a>
                    </h4>
                </div>

                <div class="form-group button-group">
                    <button class="btn back-btn" type="button" @click="refreshPage()">Back</button>
                    <button class="btn copy-shorten-btn" type="button" @click="copyShortenURL(shortened_url)">
                        <span v-if="copied">Copied</span>
                        <span v-else>Copy</span>
                    </button>
                </div>
            </div>

            <!-- Default Form to be shown -->
            <div v-else="shortened_url_length === 0">

                <div class="form-group">
                    <input type="text" v-model="original_url" class="form-control" placeholder="Type URL Link" required>
                    <p class="errors" v-if="error">{{ error_message }}</p>
                </div>

                <div class="form-group">
                    <button class="btn submit-btn" type="button" @click="shortenURL()">
                        <span v-if="loading">
                            <div class="spinner-border text-light" role="status">
                                <span class="visually-hidden">Loading...</span>
                            </div>
                        </span>
                        <span v-else>Continue</span>
                    </button>
                </div>
            </div>

        </form>
    </div>
</template>


<script>
import axios from "axios";
let baseURL = "https://shortly-api.abram.tech/api/"; // http://127.0.0.1:8800/api/

export default {
    name: "Input",
    data() {
        return {
            original_url: "",
            shortened_url: "",
            error_message: "",
            shortened_url_length: 0,
            copied: false,
            disabled: false,
            loading: false,
            error: false,
        }
    },
    methods: {
        async shortenURL() {

            // set loading to true
            this.loading = true;

            // check if original_url exist
            if (this.original_url === "") {
                this.error = true;
                this.error_message = "Can't leave this blank..";

                // remove error and loading spin after 3 seconds
                setTimeout(() => {
                    this.error = false;
                    this.loading = false;
                }, 3000);
            }

            else {

                await axios({
                    method: "POST",
                    url: `${baseURL}shorten/`,
                    data: {
                        "original_url": this.original_url,
                    },
                    headers: {
                        "Content-Type": "application/json"
                    }
                })
                    .then((res) => {
                        this.shortened_url = "https://" + res.data.data.short_url;
                        this.shortened_url_length = this.shortened_url.length

                        // set loading to false
                        this.loading = false;
                    })
                    .catch((err) => {

                        // set error to variables
                        this.error = true;
                        this.error_message = err.message;

                        // reload window after 3sec
                        setTimeout(() => {
                            window.location.reload();
                        }, 3000)
                    });
            }

        },
        refreshPage() {
            // reloads page
            window.location.reload();
        },
        copyShortenURL(url) {
            // sets copied to true and copies url to clipboard
            this.copied = true;
            navigator.clipboard.writeText(url);
        }
    }
}
</script>


<style scoped>
input.form-control {
    box-sizing: border-box;
    width: 652px;
    height: 80px;
    margin: auto;
    margin-top: 20px;
    background: rgba(222, 164, 196, 0.44);
    border: 3px solid #000000;
    border-radius: 1px;

    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 39px;
    letter-spacing: 0.065em;
    color: #000000;
}

input.form-control:active,
input.form-control:focus {
    background: transparent;
}

img.img-responsive {
    position: absolute;
    left: 64%;
    right: 29.51%;
    top: 49%;
    bottom: 58.3%;
    cursor: pointer;
}

button.back-btn,
button.copy-shorten-btn,
button.submit-btn {
    justify-content: center;
    align-items: center;
    padding: 15px 25px;
    gap: 10px;
    background-color: #000;
    border-radius: 0px;
    width: 150px;
    margin-top: 20px;

    font-weight: 500;
    font-size: 16px;
    line-height: 30px;
    text-transform: Capitalize;
    letter-spacing: 0.065em;
    color: #FFA36A;
}

button.back-btn {
    background-color: transparent;
    border: 3px solid #000;
    color: #000;
}

button.back-btn,
button.copy-shorten-btn {
    padding: 12px 25px;
}

div.form-group>h4.main-subtitle {
    margin-top: 10px;
    font-size: 20px;
}

p.errors {
    background-color: #af233a;
    padding: 6px 25px;
    max-width: 35%;
    margin: auto;
    margin-top: 10px;
    color: #fff;
}

div.button-group {
    display: flex;
    justify-content: space-between;
    max-width: 20%;
    margin: auto;
}

a.shortened-link {
    color: #000;
}

div.spinner-border {
    padding: 0px 0px;
}

@media screen and (max-width: 489px) {
    input.form-control {
        width: 100%;
        height: 70px;
    }

    p.errors {
        max-width: 100%;
    }

    div.button-group {
        max-width: 100%;
    }
}

@media screen and (max-width: 320px) {

}
</style>