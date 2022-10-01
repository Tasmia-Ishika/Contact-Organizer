<template>
    <div class="container">
        <div class="row">
            <div class="col">
                <h2 class="mt-3">Edit Contact.</h2>
                <p class="fst-italic">Edit any changes for an individual contacts...</p>
            </div>
        </div>
    </div>
    <div class="container mt-4">
        <div class="row">
            <div class="col-md-4">
                <form>
                    <div  class="mb-2">
                        <input type="text" class="form-control" placeholder="Name" />
                    </div>
                    <div  class="mb-2">
                        <input type="text" class="form-control" placeholder="Add Photo" />
                    </div>
                    <div  class="mb-2">
                        <input type="email" class="form-control" placeholder="Email" />
                    </div>
                    <div  class="mb-2">
                        <input type="number" class="form-control" placeholder="Phone" />
                    </div>
                    <div  class="mb-2">
                        <input type="text" class="form-control" placeholder="Company" />
                    </div>
                    <div  class="mb-2">
                        <input type="text" class="form-control" placeholder="Title" />
                    </div>
                    <div  class="mb-2">
                        <select class="form-control">
                            <option value="">Select Group</option>
                        </select>
                    </div>
                    <div  class="mb-2">
                        <input type="submit" class="btn btn-success" value="Update" />
                    </div>
                </form>
            </div>
            <div class="col-md-4">
                <img src="https://www.kindpng.com/picc/m/22-223910_circle-user-png-icon-transparent-png.png" alt="" class="contact-img">
            </div>
        </div>
    </div>
</template>
    
    <script>
    export default {
        name: "EditContact"
    }
    </script>
    
    <style>
    
    </style>