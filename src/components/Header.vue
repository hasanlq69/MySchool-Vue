<template>
    <nav class="navbar navbar-expand-md navbar-dark fixed-top bg-dark" style="border-top: 5px solid #af8ce2;">
        <div class="container-fluid">
            <router-link :to="{name: 'home'}" class="navbar-brand"><i class="fa fa-university" aria-hidden="true"></i> My School</router-link>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarCollapse"
                aria-controls="navbarCollapse" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarCollapse">
                <ul class="navbar-nav mr-auto mb-2 mb-md-0">
                    <li class="nav-item">
                        <router-link :to="{name: 'post'}" class="nav-link" active-class="active"><i class="fa fa-book-open" aria-hidden="true"></i> BERITA</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link :to="{name: 'event'}" class="nav-link" active-class="active"><i class="fa fa-calendar" aria-hidden="true"></i> AGENDA</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link :to="{name: 'photo'}" class="nav-link" active-class="active"><i class="fa fa-image" aria-hidden="true"></i> GALERI</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link :to="{name: 'video'}" class="nav-link" active-class="active"><i class="fa fa-video" aria-hidden="true"></i> VIDEO</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link :to="{name: 'contact'}" class="nav-link" active-class="active"><i class="fa fa-phone" aria-hidden="true"></i> KONTAK</router-link>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
    export default {
        name: 'HeaderComponent'
    }
</script>