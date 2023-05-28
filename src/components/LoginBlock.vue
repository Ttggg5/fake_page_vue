<template>
    <div class="login-block" id="loginBox">
        <div class="form-title">
            <img src="/baha_logo_horizontal.svg">
            <h5>會員登入</h5>
        </div>

        <form id="form-login" method="post">
            <input type="text" class="input-form-login" placeholder="帳號" required>
            <div class="password-block">
                <input type="password" class="input-form-login" id="input_password" placeholder="密碼" required>
                <i class="far fa-eye" id="togglePassword"></i>
            </div>

            <div style="display: flex; align-items: center; width: 100%; height: 20px; margin-top: 8px">
                <div class="check-group">
                    <input type="checkbox" id="check-saveid">
                    <label for="check-saveid">
                        <h6>記住帳號</h6>
                    </label>
                </div>

                <div class="check-group" style="margin-left: 10px">
                    <input type="checkbox" id="check-active">
                    <label for="check-active">
                        <h6>保持登入狀態</h6>
                    </label>
                </div>

                <a class="caption-text" href="https://user.gamer.com.tw/login_problem.php" style="margin-left: auto;">登入有問題嗎？</a>
            </div>

            <a class="btn-login" id="loginBtn">登入</a>
        </form>

        <div style="font-size: 13px; color: rgba(76, 87, 102, 0.6); margin-top: 15px; display: flex; justify-content: center;">
            還沒有帳號嗎？
            <a class="caption-text" href="https://user.gamer.com.tw/register.php">我要註冊</a>
        </div>
    </div>
</template>

<script>
export default {
    mounted() {
        let togglePassword = document.getElementById("togglePassword");
        let password = document.getElementById("input_password");
        let loginBtn = document.getElementById("loginBtn");

        togglePassword.addEventListener('click', function (e){
            let type = password.getAttribute('type') === 'password' ? 'text' : 'password';
            password.setAttribute('type', type);
            this.classList.toggle('fa-eye-slash');
        });

        loginBtn.addEventListener('mousedown', function (e){
            loginBtn.style.margin = '22px 0 0 0';
        });

        loginBtn.addEventListener('mouseup', function (e){
            loginBtn.style.margin = '20px 0 2px 0';
        });
    }
}
</script>

<style scoped>
.login-block{
    margin: 8rem auto 300px auto;
    background: white;
    border-radius: 4px;
    width: 360px;
    padding: 36px 24px;
    box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.2);
    box-sizing: border-box;
}

.form-title{
    margin-bottom: 12px;
    display: flex;
    justify-content: center;
}

.form-title img{
    width: 190px;
}

.form-title h5{
    display: none;
}

.input-form-login{
    margin: 8px 0;
    border: 1px solid #D9D9D9;
    border-radius: 3px;
    padding: 8px;
    box-sizing: border-box;
    width: 100%;
    background-color: #FFF;
    font-size: 15px;
    color: #2d2d2d;
}

.password-block i{
    position: absolute;
    margin-top: 17px;
    margin-left: -25px;
    cursor: pointer;
    display: inline-block;
    color: #999999;
}

.check-group input, label {
    display: inline-block;
    min-width: 18px;
    min-height: 16px;
    cursor: pointer;
}

.caption-text {
    color: #117E96;
    font-size: 13px;
    text-decoration: none;
}

.btn-login{
    background-color: #117e96;
    color: #FFF;
    text-decoration: none;
    display: inline-flex;
    height: 40px;
    margin: 20px 0 2px 0;
    width: 100%;
    border-radius: 6px;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    border-color: #117e96;
}

.btn-login:hover{
    background-color: #3E7786;
}
</style>