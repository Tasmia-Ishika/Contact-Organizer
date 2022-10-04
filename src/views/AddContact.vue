<template>
    <div class="container">
        <div class="row">
            <div class="col">
                <h2 class="mt-3">Add Your Contact</h2>
                <p class="fst-italic">Add as many as contacts you want without any extra hassle...</p>
            </div>
        </div>
    </div>
    <!-- <prev>{{groups}}</prev> -->
    <div class="container mt-4">
        <div class="row">
            <div class="col-md-4">
                <form @submit.prevent="submitCreate()">
                    <div class="mb-2">
                        <input required v-model="contact.name" type="text" class="form-control" placeholder="Name" />
                    </div>
                    <div class="mb-2">
                        <input required v-model="contact.photo" type="text" class="form-control" placeholder="Add Photo" />
                    </div>
                    <div class="mb-2">
                        <input required v-model="contact.email" type="email" class="form-control" placeholder="Email" />
                    </div>
                    <div class="mb-2">
                        <input required v-model="contact.phone" type="number" class="form-control" placeholder="Phone" />
                    </div>
                    <div class="mb-2">
                        <input required v-model="contact.company" type="text" class="form-control" placeholder="Company" />
                    </div>
                    <div class="mb-2">
                        <input required v-model="contact.title" type="text" class="form-control" placeholder="Title" />
                    </div>
                    <div class="mb-2">
                        <select required v-model="contact.groupId" class="form-control" v-if="groups.length > 0">
                            <option value="">Select Group</option>
                            <option :value="group.id" v-for="group of groups" :key="group.id">{{group.name}}</option>
                        </select>
                    </div>
                    <div class="mb-2">
                        <input type="submit" class="btn btn-success" value="Save" />
                    </div>
                </form>
            </div>
            <div class="col-md-4">
                <img :src="contact.photo" alt="" class="contact-img">
            </div>
            <div class="row mt-3">
                <div class="col">
                    <router-link to="/" class="btn btn-success btn-sm"><i class="fa fa-arrow-left"></i> Go Back
                    </router-link>
                </div>
            </div>
        </div>
    </div>
</template>
    
<script>
import { ContactService } from '@/services/ContactService';

export default {
    name: "AddContact",
    data: function () {
        return {
            contact: {
                name: '',
                photo: '',
                email: '',
                phone: '',
                company: '',
                title: '',
                groupId: '',
            },
            groups: []
        }
    },
    created: async function () {
        try {
            let response = await ContactService.getAllGroups();
            this.groups = response.data;
        }
        catch (error) {
            console.log(error)
        }
    },
    methods: {
        submitCreate: async function () {
            try {
                let response = await ContactService.createContact(this.contact);
                if (response) {
                    return this.$router.push('/');
                }
                else {
                    return this.$router.push('/contacts/add');
                }
            }
            catch (error) {
                console.log(error);
            }
        }
    }
}
</script>
    
<style>

</style>