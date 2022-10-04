<template>
    <div class="container">
        <div class="row">
            <div class="col">
                <h2 class="mt-3">View Details of Contact.</h2>
                <p class="fst-italic">Check all details of a contact on a simple way...</p>
            </div>
        </div>
    </div>

     <!-- Spinner -->
     <div v-if="loading">
        <div class="container">
            <div class="row">
                <div class="col">
                    <LoadingSpinner />
                </div>
            </div>
        </div>
    </div>
    <!-- Error Message -->
    <div v-if="!loading && errorMessage">
        <div class="container">
            <div class="row">
                <div class="col">
                  <p class="h2 text-danger fw-bold">{{errorMessage}}</p>
                </div>
            </div>
        </div>
    </div>
    
    <div class="container mt-4" v-if="!loading && idDone()">
        <div class="row align-items-center">
            <div class="col-md-4">
                <img :src="contact.photo" alt=""
                    class="contact-img-big">
            </div>
            <div class="col-md-6 mt-4">
                <ul class="list-group">
                    <li class="list-group-item">
                        Name : <span class="fw-bold">{{contact.name}}</span>
                    </li>
                    <li class="list-group-item">
                        Email : <span class="fw-bold">{{contact.email}}</span>
                    </li>
                    <li class="list-group-item">
                        Phone : <span class="fw-bold">{{contact.phone}}</span>
                    </li>

                    <li class="list-group-item">
                        Company : <span class="fw-bold">{{contact.company}}</span>
                    </li>
                    <li class="list-group-item">
                        Title : <span class="fw-bold">{{contact.title}}</span>
                    </li>
                    <li class="list-group-item">
                        Group : <span class="fw-bold">{{group.name}}</span>
                    </li>
                </ul>
            </div>
        </div>
        <div class="row">
            <div class="col mt-4">
                <router-link to="/" class="btn btn-success btn-sm"><i class="fa fa-arrow-left"></i> Go Back
                </router-link>
            </div>
        </div>
    </div>
</template>
    
<script>
import { ContactService } from '@/services/ContactService';
import LoadingSpinner from '../components/LoadingSpinner.vue';


export default {
    name: "ViewContact",
    data: function () {
        return {
            contactId: this.$route.params.contactId,
            loading: false,
            contact: {},
            errorMessage: null,
            group: {}
        };
    },
    created: async function () {
        try {
            this.loading = true;
            let response = await ContactService.getContact(this.contactId);
            let groupResponse = await ContactService.getGroup(response.data);
            this.contact = response.data;
            this.group = groupResponse.data;
            this.loading = false;
        }
        catch (error) {
            this.errorMessage = error;
            this.loading = false;
        }
    },
    methods: {
        idDone: function () {
            return Object.keys(this.contact).length > 0 && Object.keys(this.group).length > 0;
        }
    },
    components: { LoadingSpinner }
}
</script>
    
<style>

</style>