<template>
    <div id="main-menu" class="wsmainfull menu clearfix">
        <div class="wsmainwp clearfix">
            <!-- HEADER BLACK LOGO -->
            <div class="desktoplogo">
                <NuxtLink to="/" class="logo-black"> <h2> Journal Of Justice </h2></NuxtLink>
            </div>
            <!-- HEADER WHITE LOGO -->
            <div class="desktoplogo">
                <NuxtLink to="/" class="logo-white">
                    <h2 class="text-black"> Journal Of Justice</h2>
                </NuxtLink>
            </div>
            <!-- MAIN MENU -->      
            <nav class="wsmenu clearfix ">
                <ul class="wsmenu-list nav-theme">
                    <!-- DROPDOWN SUB MENU -->
                    <li aria-haspopup="true" class="mg_link" :class="{ open: isOpen[0] }">
                        <span class="wsmenu-click 123" @click="toggle(0)"><i class="wsmenu-arrow"></i></span>
                        <NuxtLink to="/" class="h-link">Home</NuxtLink>
                      
                    </li>


                    <!-- SIMPLE NAVIGATION LINK -->
                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/about" class="h-link">About Us</NuxtLink></li>
                    <!-- MEGAMENU -->
                    
                    <li aria-haspopup="true" class="mg_link" :class="{ open: isOpen[1] }">
                        <span class="wsmenu-click 123" @click="toggle(1)"><i class="wsmenu-arrow"></i></span>
                        <NuxtLink to="/services" class="h-link">Last Posts <span class="wsarrow"></span></NuxtLink>
                        <div class="wsmegamenu w-75 clearfix">
                            <div class="container">
                                <div class="row">
                                    <!-- MEGAMENU LINKS -->
                                   

                                      
                                   
                                </div>
                                <!-- End row -->
                            </div>
                            <!-- End container -->
                        </div>
                        <!-- End wsmegamenu -->
                    </li>
                    <!-- END MEGAMENU -->
                    <!-- SIMPLE NAVIGATION LINK -->
                    <!-- <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/blog-listing" class="h-link">Blog</NuxtLink></li> -->
                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/contacts" class="h-link">Contact Us</NuxtLink></li>
                    

                    <!-- SIGN IN LINK -->
                    <!-- <li class="nl-simple reg-fst-link mobile-last-link" aria-haspopup="true">
                        <NuxtLink to="/login-2" class="h-link">Sign in</NuxtLink>
                    </li> -->
                    <!-- SIGN UP BUTTON -->
                    <!-- <li class="nl-simple" aria-haspopup="true">
                        <NuxtLink to="/signup-2" class="btn r-04 btn--theme hover--tra-white last-link">Sign up</NuxtLink>
                    </li> -->
                </ul>
            </nav>
            <!-- END MAIN MENU -->
        </div>
    </div>
</template>
<script>
import { reactive } from 'vue';
export default {
    setup() {
        const state = reactive({
        isOpen: [false, false]
        });
        const toggle = (index) => {
        state.isOpen[index] = !state.isOpen[index];
        };
        return {
        toggle,
        isOpen: state.isOpen
        };
    },
    mounted() {
        window.addEventListener("scroll", this.handleScroll);
    },
    destroyed() {
        window.removeEventListener("scroll", this.handleScroll);
    },
    methods: {
        handleScroll() {
            const menu = document.getElementById("main-menu");
            const header = document.getElementById("header");
            if (window.pageYOffset > 100) {
                menu.classList.add("scroll");
                header.classList.add("scroll");
            } else {
                menu.classList.remove("scroll");
                header.classList.remove("scroll");
            }
        }
    }
};
</script>
