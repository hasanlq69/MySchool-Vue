<template>
    <footer>
        <div class="container-fluid" style="background: white;">
            <div class="row p-4">
                <div class="col-md-4">
                    <h5>TENTANG</h5>
                    <hr>
                    <p>
                        My School adalah pendidikan formal yang menyelenggarakan pendidikan koding pada jenjang pendidikan menengah sebagai lanjutan dari SMP/MTs.
                    </p>
                </div>
                <div class="col-md-4">
                    <h5>TAGS</h5>
                    <hr>
                    <div v-if="tags.length > 0">
                        <router-link :to="{name: 'detail_tag', params: { slug: tag.slug }}" v-for="tag in tags" :key="tag.id" class="btn btn-sm btn-outline-secondary mb-2 me-2">{{ tag.name.toUpperCase() }}</router-link>
                    </div>
                    <div v-else class="text-center">
                        <ListLoader/>
                    </div>
                </div>
                <div class="col-md-4">
                    <h5>KONTAK</h5>
                    <hr>
                    <p>
                        <i class="fa fa-map-marker" aria-hidden="true"></i> Jl. Pringapus Ungaran Kab.Semarang Indonesia
                        <i class="fas fa-phone"></i> +62857-2599-3706
                    </p>
                </div>
            </div>
        </div>
        <div class="container-fluid bg-dark">
            <div class="row p-3">
                <div class="text-center text-white font-weight-bold">
                    Copyright © 2025 My School Muhammad Hasan. All rights reserved.
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
    //import content loader
    import {
        ListLoader
    } from 'vue-content-loader';

    //import axios
    import axios from 'axios';

    //import hook onMounted from vue
    import { ref, onMounted } from 'vue';

    export default {
        name: 'FooterComponent',

        components: {
            //loader component
            ListLoader
        },

        setup() {

            //define state
            const tags = ref([]);

            //on mounted
            onMounted(() => {
                axios.get('/api/tag')
                    .then(response => {
                        tags.value = response.data.data.data;
                    })
                    .catch(() => {
                        tags.value = [];
                    });
            })

            //return data
            return {
                tags,
            }
        }
    }
</script>