<template>
    <div class="form-container">
        <form>
            <div class="form-group">
                <input type="text" name="original_url" class="form-control" placeholder="Type URL Link">

                <img src="@/assets/paste-it.png" alt="paste-it" class="img-responsive">
            </div>

            <div class="form-group">
                <button class="btn submit-btn" type="submit">Continue</button>
            </div>
        </form>
    </div>
</template>


<script>
export default {
    name: "Input"
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
</style>