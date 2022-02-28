<template>
    <!-- START NAV -->
    <nav class="navbar is-white">
        <div class="container">
            <div class="navbar-brand">
                <a class="navbar-item brand-text" href="#">Ender's Weather</a>
                <div class="navbar-burger burger" data-target="navMenu">
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
            </div>
            <div id="navMenu" class="navbar-menu">
                <div class="navbar-start">
                    <RouterLink class="navbar-item" to="/">Weather</RouterLink>
                    <RouterLink class="navbar-item" to="/about">About</RouterLink>
                </div>
            </div>
        </div>
    </nav>
    <!-- END NAV -->
</template>