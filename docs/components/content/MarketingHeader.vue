<template>
    <div class="w-full">
        <a href="https://getspin.pro/?ref=spin" target="_blank" class="py-2 px-1 bg-[#1CE783] w-full flex items-center justify-center font-semibold text-sm md:text-base"
            :class="{
                'mt-[43px]': fixed
            }">
            <svg class="mr-[6px]" width="24" height="25" viewBox="0 0 24 25" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 15.9706L9 12.9706M12 15.9706C13.3968 15.4394 14.7369 14.7694 16 13.9706M12 15.9706V20.9706C12 20.9706 15.03 20.4206 16 18.9706C17.08 17.3506 16 13.9706 16 13.9706M9 12.9706C9.53214 11.5901 10.2022 10.2667 11 9.02065C12.1652 7.15763 13.7876 5.62369 15.713 4.56474C17.6384 3.50578 19.8027 2.95702 22 2.97065C22 5.69065 21.22 10.4706 16 13.9706M9 12.9706H4C4 12.9706 4.55 9.94065 6 8.97065C7.62 7.89065 11 8.97065 11 8.97065M4.5 17.4706C3 18.7306 2.5 22.4706 2.5 22.4706C2.5 22.4706 6.24 21.9706 7.5 20.4706C8.21 19.6306 8.2 18.3406 7.41 17.5606C7.02131 17.1897 6.50929 16.9753 5.97223 16.9587C5.43516 16.9421 4.91088 17.1244 4.5 17.4706Z" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>

            <span class="md:hidden">Spin Pro is now is available for Laravel!</span>
            <span class="hidden md:inline">Spin Pro now available with Laravel Horizon, Reverb, and more!</span>

        </a>

        <header class="w-full py-4 px-6 backdrop-blur z-50 lg:px-8" 
            :class="{ 
                'fixed': fixed 
            }"
            :style="{
                'top': y > 43 ? '43px' : ( 86-y )+'px'
            }">            
            
            <div class="flex items-center justify-between">
                <NuxtLink :to="'/'">
                    <img class="w-32" src="/images/logos/spin-logo.svg"/>
                </NuxtLink>

                <div class="flex items-center">
                    <div class="flex items-center lg:hidden">
                        <button @click="toggleMobileNav()" class="flex items-center justify-center w-6 h-6 cursor-pointer">
                            <div id="nav-icon" class="w-[18px] h-3 relative" :class="{
                                'open': showMobileMenu
                            }">
                                <span></span>
                                <span></span>
                                <span></span>
                                <span></span>
                                <span></span>
                                <span></span>
                            </div>
                        </button>
                    </div>
                    <nav class="items-center hidden lg:flex">
                        <div class="flex items-center gap-4 lg:gap-4 xl:gap-8 mr-8">
                            <button 
                                type="button"
                                @click="promptSearch()"
                                class="flex items-center font-inter font-bold text-slate-300 text-sm rounded py-[6px] px-2 hover:bg-gray-900 xl:text-lg">
                                    <div class="flex items-center justify-center w-5 h-5 mr-2">
                                        <svg width="21" height="21" viewBox="0 0 21 21" fill="none" xmlns="http://www.w3.org/2000/svg">
                                            <path d="M19.3324 19.2572L13.3325 13.2572M15.3324 8.2572C15.3324 12.1232 12.1984 15.2572 8.3324 15.2572C4.4664 15.2572 1.3324 12.1232 1.3324 8.2572C1.3324 4.39121 4.4664 1.2572 8.3324 1.2572C12.1984 1.2572 15.3324 4.39121 15.3324 8.2572Z" stroke="#CBD5E1" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                                        </svg>

                                    </div>
                                    
                                    Search
                            </button>  
                            <NuxtLink 
                                :href="'/docs'"
                                class="flex items-center font-inter font-bold text-slate-300 text-sm rounded py-[6px] px-2 hover:bg-gray-900 xl:text-lg">
                                    <div class="flex items-center justify-center w-5 h-5 mr-2">
                                        <svg width="18" height="23" viewBox="0 0 18 23" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-full max-h-full">
                                            <path d="M17 18.4468V15.4468H4C2.34315 15.4468 1 16.79 1 18.4468M5.8 21.4468H13.8C14.9201 21.4468 15.4802 21.4468 15.908 21.2289C16.2843 21.0371 16.5903 20.7311 16.782 20.3548C17 19.927 17 19.3669 17 18.2468V4.64684C17 3.52673 17 2.96668 16.782 2.53886C16.5903 2.16253 16.2843 1.85657 15.908 1.66483C15.4802 1.44684 14.9201 1.44684 13.8 1.44684H5.8C4.11984 1.44684 3.27976 1.44684 2.63803 1.77382C2.07354 2.06144 1.6146 2.52038 1.32698 3.08487C1 3.7266 1 4.56668 1 6.24684V16.6468C1 18.327 1 19.1671 1.32698 19.8088C1.6146 20.3733 2.07354 20.8322 2.63803 21.1199C3.27976 21.4468 4.11984 21.4468 5.8 21.4468Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                                        </svg>
                                    </div>
                                    
                                    Docs
                            </NuxtLink>

                            <NuxtLink 
                                :href="'/hub'"
                                class="flex items-center font-inter font-bold text-slate-300 text-sm rounded py-[6px] px-2 hover:bg-gray-900 xl:text-lg">
                                    <div class="flex items-center justify-center w-5 h-5 mr-2">
                                        <svg width="25" height="25" viewBox="0 0 25 25" fill="none" xmlns="http://www.w3.org/2000/svg">
                                            <path d="M12.8324 15.2572L9.8324 12.2572M12.8324 15.2572C14.2292 14.7259 15.5693 14.0559 16.8324 13.2572M12.8324 15.2572V20.2572C12.8324 20.2572 15.8624 19.7072 16.8324 18.2572C17.9124 16.6372 16.8324 13.2572 16.8324 13.2572M9.8324 12.2572C10.3645 10.8766 11.0346 9.55327 11.8324 8.30721C12.9976 6.44419 14.62 4.91025 16.5454 3.8513C18.4708 2.79234 20.6351 2.24358 22.8324 2.25721C22.8324 4.97721 22.0524 9.75721 16.8324 13.2572M9.8324 12.2572H4.8324C4.8324 12.2572 5.3824 9.22721 6.8324 8.25721C8.4524 7.17721 11.8324 8.25721 11.8324 8.25721M5.3324 16.7572C3.8324 18.0172 3.3324 21.7572 3.3324 21.7572C3.3324 21.7572 7.0724 21.2572 8.3324 19.7572C9.0424 18.9172 9.0324 17.6272 8.2424 16.8472C7.8537 16.4762 7.34169 16.2618 6.80462 16.2452C6.26756 16.2286 5.74327 16.4109 5.3324 16.7572Z" stroke="#CBD5E1" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                                        </svg>
                                    </div>
                                    
                                    Hub
                            </NuxtLink>  
                            
                            <NuxtLink 
                                :href="'https://serversideup.net/discord'"
                                target="_blank"
                                class="flex items-center font-inter font-bold text-slate-300 text-sm rounded py-[6px] px-2 hover:bg-gray-900 xl:text-lg">
                                    <div class="flex items-center justify-center w-5 h-5 mr-2">
                                        <svg width="24" height="25" viewBox="0 0 24 25" fill="none" xmlns="http://www.w3.org/2000/svg">
                                            <path d="M19.6361 5.39641C18.1907 4.73466 16.6648 4.26519 15.0973 4C14.8828 4.38343 14.6888 4.77793 14.5159 5.18184C12.8463 4.93025 11.1484 4.93025 9.47881 5.18184C9.30587 4.77797 9.1118 4.38348 8.8974 4C7.32897 4.26743 5.80205 4.73801 4.35518 5.39987C1.48276 9.64967 0.70409 13.7939 1.09342 17.8793C2.77558 19.1222 4.6584 20.0674 6.66003 20.6739C7.11074 20.0677 7.50956 19.4246 7.85226 18.7514C7.20135 18.5083 6.57311 18.2084 5.9748 17.8551C6.13227 17.7409 6.28627 17.6232 6.43508 17.509C8.17601 18.3277 10.0761 18.7522 12 18.7522C13.9238 18.7522 15.8239 18.3277 17.5648 17.509C17.7154 17.6319 17.8694 17.7495 18.0251 17.8551C17.4257 18.209 16.7963 18.5095 16.1442 18.7532C16.4865 19.426 16.8853 20.0686 17.3364 20.6739C19.3398 20.0698 21.224 19.1251 22.9065 17.881C23.3633 13.1433 22.1261 9.03711 19.6361 5.39641ZM8.34541 15.3668C7.26047 15.3668 6.36414 14.3822 6.36414 13.171C6.36414 11.9597 7.22932 10.9665 8.34195 10.9665C9.45458 10.9665 10.344 11.9597 10.325 13.171C10.3059 14.3822 9.45112 15.3668 8.34541 15.3668ZM15.6545 15.3668C14.5678 15.3668 13.675 14.3822 13.675 13.171C13.675 11.9597 14.5401 10.9665 15.6545 10.9665C16.7689 10.9665 17.6514 11.9597 17.6323 13.171C17.6133 14.3822 16.7602 15.3668 15.6545 15.3668Z" fill="#E2E8F0"/>
                                        </svg>
                                    </div>
                                    
                                    Discord
                            </NuxtLink>  

                            <NuxtLink 
                                :href="'https://github.com/serversideup/spin'"
                                target="_blank"
                                class="flex items-center font-inter font-bold text-slate-300 text-sm rounded py-[6px] px-2 hover:bg-gray-900 xl:text-lg">
                                    <div class="flex items-center justify-center w-5 h-5 mr-2">
                                        <svg width="20" height="22" viewBox="0 0 14 15" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-full max-h-full">
                                            <path d="M7 0.65799C3.1325 0.65799 0 3.79049 0 7.65799C0 10.7555 2.00375 13.3717 4.78625 14.2992C5.13625 14.3605 5.2675 14.1505 5.2675 13.9667C5.2675 13.8005 5.25875 13.2492 5.25875 12.663C3.5 12.9867 3.045 12.2342 2.905 11.8405C2.82625 11.6392 2.485 11.018 2.1875 10.8517C1.9425 10.7205 1.5925 10.3967 2.17875 10.388C2.73 10.3792 3.12375 10.8955 3.255 11.1055C3.885 12.1642 4.89125 11.8667 5.29375 11.683C5.355 11.228 5.53875 10.9217 5.74 10.7467C4.1825 10.5717 2.555 9.96799 2.555 7.29049C2.555 6.52924 2.82625 5.89924 3.2725 5.40924C3.2025 5.23424 2.9575 4.51674 3.3425 3.55424C3.3425 3.55424 3.92875 3.37049 5.2675 4.27174C5.8275 4.11424 6.4225 4.03549 7.0175 4.03549C7.6125 4.03549 8.2075 4.11424 8.7675 4.27174C10.1063 3.36174 10.6925 3.55424 10.6925 3.55424C11.0775 4.51674 10.8325 5.23424 10.7625 5.40924C11.2087 5.89924 11.48 6.52049 11.48 7.29049C11.48 9.97674 9.84375 10.5717 8.28625 10.7467C8.54 10.9655 8.75875 11.3855 8.75875 12.0417C8.75875 12.978 8.75 13.7305 8.75 13.9667C8.75 14.1505 8.88125 14.3692 9.23125 14.2992C10.6209 13.8301 11.8284 12.937 12.6839 11.7457C13.5393 10.5543 13.9996 9.12467 14 7.65799C14 3.79049 10.8675 0.65799 7 0.65799Z" fill="currentColor"/>
                                        </svg>
                                    </div>
                                    
                                    Github
                            </NuxtLink>  

                            <NuxtLink target="_blank" :to="'https://github.com/sponsors/serversideup'" class="flex items-center px-[14px] py-2 font-bold font-inter text-white rounded-lg border border-solid border-slate-700 bg-slate-800 hover:bg-slate-700 text-sm">
                                Sponsor
                                <img class="ml-[10px]" src="/images/icons/heart.svg"/>
                            </NuxtLink>

                            <NuxtLink :to="'/docs'" class="flex items-center px-[14px] py-2 font-bold font-inter text-[#151A1F] rounded-lg bg-[#1CE783] text-sm hover:bg-[#1CE783]">
                                Get Started &rarr;
                            </NuxtLink>
                        </div>
                    </nav>
                </div>
            </div>
        </header>

        <GlobalMobileMenu
            :show="showMobileMenu"
            :navigation="navigation[0]"/>
    </div>
</template>

<script setup>
const props = defineProps({ 
    fixed: {
        default: false
    }
});

const showMobileMenu = ref(false);
const toggleMobileNav = () => {
    showMobileMenu.value = showMobileMenu.value ? false : true;
}
watch(showMobileMenu, ( newValue ) => {
    if( newValue ){
        document.documentElement.classList.add('overflow-y-hidden');
        document.body.classList.add('overflow-y-hidden');
    }else{
        document.documentElement.classList.remove('overflow-y-hidden');
        document.body.classList.remove('overflow-y-hidden');
    }
});

const { navigation } = useContent();

const docsEventBus = useEventBus('spin-docs-event-bus');
const promptSearch = () => {
    docsEventBus.emit('prompt-search');
}

docsEventBus.on(( event ) => {
    if( event === 'hide-mobile-menu' ){
        showMobileMenu.value = false;
    }
});

const { y } = useWindowScroll();
</script>