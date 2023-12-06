<template>
    <div id="MainLayout" class="w-full fixed z-50">
        <div id="TopMenu" class="w-full bg-[#FAFAFAF] border-b md:block hidden">

            <ul class="
                    flex 
                    items-center 
                    justify-end
                    text-xs 
                    text-[#333333]
                    font-light 
                    px-2
                    h-10
                    bg-[#FAFAFA] 
                    max-w-[1200px] 
                 ">

                <li @mouseenter="isHelpMenu = true" @mouseleave="isHelpMenu = false"
                    class="relative flex items-center px-2.5 hover:text-[#FF4646] h-full cursor-pointer"
                    :class="isHelpMenu ? 'bg-white border z-40 shadow-[0_15px_100px_40px_rgba(0,0,0,0.3)]' : 'border border-[#FAFAFA]'">
                    Yardim

                    <div div id="AccountMenu" v-if="isHelpMenu"
                        class="absolute bg-white w-[160px] text-[#333333] z-40 top-[38px] -left-[1px] border-x border-b">

                        <div class="text-semibold text-[12px]  py-3   hover:bg-gray-200">Yardim merkezi</div>
                        <div class="text-semibold text-[12px]  py-3  hover:bg-gray-200">Bir şikayet girin</div>
                        <div class="text-semibold text-[12px]  py-3  hover:bg-gray-200">Fikri Mülkiyet hakki bildir</div>
                     
                    </div>

                    <Icon name="mdi:chevron-down" size="17" />
                </li>
                <li class="px-3 hover:text-[#FF4646] cursor-pointer">
                    Alici Korumasi
                </li>
                <li class="border-r border-r-gray-400 px-3 hover:text-[#FF4646] cursor-pointer ">
                    <Icon name="ic:sharp-install-mobile" size="17" />
                    Cep
                </li>

                <li class="border-r border-r-gray-400 px-3 hover:text-[#FF4646] cursor-pointer ">
                    <Icon name="ic:sharp-install-mobile" size="17" />
                    /Turkce/EUR
                </li>

                <li class="px-3 hover:text-[#FF4646] cursor-pointer">
                    <Icon name="ion:heart-outline" size="17" />
                    İstek Listesi
                </li>

                <li @mouseenter="isAccountMenu = true" @mouseleave="isAccountMenu = false"
                    class="relative flex items-center px-2.5 hover:text-[#FF4646] h-full cursor-pointer"
                    :class="isAccountMenu ? 'bg-white border z-40 shadow-[0_15px_100px_40px_rgba(0,0,0,0.3)]' : 'border border-[#FAFAFA]'">


                    <Icon name="ph:user-thin" size="14" />
                    Hesap
                    <Icon :name="isAccountMenu ? 'mdi:chevron-up' : 'mdi:chevron-down'" :size="14" />

                    <div id="AccountMenu" v-if="isAccountMenu"
                        class="absolute bg-white w-[220px] text-[#333333] z-40 top-[38px] -left-[140px] border-x border-b">
                        <div v-if="!user">

                            <div class="text-semibold text-[15px] my-4 px-3">Tekrar Hosgeldiniz</div>
                            <div class="flex" items-center gap-1 mb-3>
                                <NuxtLink to="/auth"
                                    class="bg-[#FF4646] text-center w-full text-[16px] rounded-sm text-white font-semibold p-2">
                                    Login / Register
                                </NuxtLink>
                            </div>
                        </div>



                    </div>

                </li>


            </ul>
        </div>
    </div>
</template>

<script setup>
let isAccountMenu = ref(false)
let isHelpMenu = ref(false)

</script>

<style lang="scss" scoped></style>