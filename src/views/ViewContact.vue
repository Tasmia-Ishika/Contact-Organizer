<template>
    <div class="container">
        <div class="row">
            <div class="col">
                <h2 class="mt-3">View Details of Contact.</h2>
                <p class="fst-italic">Edit any changes for an individual contacts...</p>
            </div>
        </div>
    </div>
    <div class="container mt-4">
        <div class="row align-items-center">
            <div class="col-md-4">
                <img src="https://www.kindpng.com/picc/m/22-223910_circle-user-png-icon-transparent-png.png" alt=""
                    class="contact-img-big">
            </div>
            <div class="col-md-6">
                <ul class="list-group">
                    <li class="list-group-item">
                        Name : <span class="fw-bold">Name</span>
                    </li>
                    <li class="list-group-item">
                        Email : <span class="fw-bold">Email</span>
                    </li>
                    <li class="list-group-item">
                        Phone : <span class="fw-bold">Phone</span>
                    </li>

                    <li class="list-group-item">
                        Company : <span class="fw-bold">Name</span>
                    </li>
                    <li class="list-group-item">
                        Title : <span class="fw-bold">Email</span>
                    </li>
                    <li class="list-group-item">
                        Group : <span class="fw-bold">Phone</span>
                    </li>
                </ul>
            </div>
        </div>
        <div class="row">
            <div class="col mt-4">
                <router-link to="/" class="btn btn-success btn-sm"><i class="fa fa-arrow-left"></i> Go Back</router-link>
            </div>
        </div>
    </div>
</template>
    
<script>
export default {
    name: "ViewContact"
}
</script>
    
<style>

</style>