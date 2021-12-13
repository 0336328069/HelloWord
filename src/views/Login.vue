<template>
  <div class="absolute top-0 left-0 right-0 bottom-0 bg-[#6a88a1]">
      <form @submit="onSubmit" class="mgi__login-form h-[384px] w-[320px] bg-[#ffffff] rounded-lg">
        <div class="px-[30px] py-[45px]">
          <div class="flex flex-col items-center mb-[30px]">
              <img src="../assets/font/logo/logo.png" alt="" class="w-[137px] h-[26px]">
          </div>
          <div class="flex flex-col items-center mb-10">
              <p class="text-[14px] h-[5px] font-bold">Welcome to IT Support App!</p>
          </div>
          <label for="username" class="flex flex-col mb-[15px]">
            <span class="font-semibold text-[12px] mb-2">User Name</span>
            <input type="text" class="h-[30px] text-[13px] px-2" id="username">
          </label>
           <label for="password" class="flex flex-col mb-[15px] relative">
            <span class="font-semibold text-[12px] mb-2">Password</span>
            <input :type="passwordType" class="h-[30px] text-[13px] px-2" id="password">
            <img @click="onClickEye" src="../assets/font/action-icon/eye_1.svg" alt="" class="h-[15px] absolute top-[26px] right-2 cursor-pointer">
            <img @click="onClickEye" v-show="eyeCheckPass" src="../assets/font/action-icon/eye_2.svg" alt="" class="h-[15px] absolute top-[26px] right-2 cursor-pointer">
          </label>
          <div class="flex items-center justify-between">
            <label for="remember" class="flex  items-center cursor-pointer">
              <input type="checkbox" id="remember">
              <div  class="mgi__checkbox h-4 w-4 mr-2 rounded-[3px]"></div>
              <span class="text-[12px] font-thin select-none">Remember me?</span>
            </label>
            <div class="flex items-center">
              <a href="#" class="text-[#1bb690] text-[12px] font-bold underline decoration-[2px]">Forgot Password</a>
            </div>
          </div>
          <div class="mt-6">
              <button type="submit" class="text-[14px] font-semibold w-full h-[38px] bg-[#208dec] text-[#FFFFFF] hover:bg-[#337ab8]">LOGIN</button>
          </div>
        </div>
      </form>
      
  </div>
</template>


<script>
import { ref } from 'vue';
import "../assets/style/login.css";
export default {
  setup() {
    const eyeCheckPass = ref(false);
    const passwordType = ref("password");
    const onClickEye = ()=>{
      eyeCheckPass.value = !eyeCheckPass.value;
      passwordType.value = passwordType.value === "password" ? "text" : "password";
    }
    function onSubmit(){}
    return {onSubmit , eyeCheckPass , onClickEye ,passwordType};
  },
}
</script>
