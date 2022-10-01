<template>
    <div class=" row row-cols-1 row-cols-lg-2 g-4 m-4  text-center">
        <div>
            <p class="h1 mt-4 fw-bold "> Welcome to Contact Organizer</p>
            <p class="h5 lg:mt-2 fst-italic">Save your times by preventing yourself from memorizing any contacts. Simply
                store them so that you can have access on them when you might need !!</p>
            <p>
                <router-link to="/contacts/add" class="btn btn-success mt-3"><i class="fa fa-plus-circle"></i> Create
                    New Contact</router-link>
            </p>
        </div>
        <div>
            <img class="img-fluid img-thumbnail rounded " src="../assets/contact-org2.png" alt="Responsive image" />
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


    <div class="container mt-4" v-if="contacts.length > 0">
        <p class="m-5 text-center h1 fw-bold">Your Contact List</p>
        <div class="row">
            <div class="col-md-6" v-for="contact of contacts" :key="contact">
                <div class="card my-2 list-group-item-success shadow-lg">
                    <div class="card-body">
                        <div class="row align-items-center">
                            <div class="col-sm-4">
                                <img :src="contact.photo" alt="" class="contact-img">
                            </div>
                            <div class="col-sm-7">
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
                                </ul>
                            </div>
                            <div class="col-sm-1 d-flex flex-column justify-content-center align-items-center ">
                                <router-link to="/contacts/view/:contactId" class="btn btn-warning my-1">
                                    <i class="fa fa-eye"></i>
                                </router-link>
                                <router-link to="/contacts/edit/:contactId" class="btn btn-primary my-1">
                                    <i class="fa fa-pen"></i>
                                </router-link>
                                <button class="btn btn-danger my-1">
                                    <i class="fa fa-trash"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<script>
import { ContactService } from '@/services/ContactService';
import LoadingSpinner from '../components/LoadingSpinner.vue';

export default {
    name: "ContactManager",
    data: function () {
        return {
            loading: false,
            contacts: [],
            errorMessage: null,
        };
    },
    created: async function () {
        try {
            this.loading = true;
            let response = await ContactService.getAllContacts();
            this.contacts = response.data;
            this.loading = false;
        }
        catch (error) {
            this.errorMessage = error;
            this.loading = false;
        }
    },
    methods: {},
    components: { LoadingSpinner }
}
</script>

<style>

</style>