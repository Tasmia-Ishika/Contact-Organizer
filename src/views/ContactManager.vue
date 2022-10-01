<template>
<div class="container row row-cols-sm-1  row-cols-lg-2 g-4 m-4 mx-2 text-center">
    <div class="">
     <p class="h1 mt-3 fw-bold "> 𝐖𝐞𝐥𝐜𝐨𝐦𝐞 𝐭𝐨 𝐂𝐨𝐧𝐭𝐚𝐜𝐭 𝐎𝐫𝐠𝐚𝐧𝐢𝐳𝐞𝐫</p>
     <p class="h5">𝒲𝑒 𝒶𝓇𝑒 𝒽𝑒𝓇𝑒 𝓉𝑜 𝑒𝒶𝓈𝑒 𝓎𝑜𝓊𝓇 𝒽𝒶𝓈𝓈𝓁𝑒 𝓉𝑜 𝓀𝑒𝑒𝓅 𝒶𝓃𝓎 𝒸𝑜𝓃𝓉𝒶𝒸𝓉𝓈 𝓎𝑜𝓊 𝓂𝒾𝑔𝒽𝓉 𝓃𝑒𝑒𝒹.</p>   
     <p>
        <router-link to="/contacts/add" class="btn btn-success mt-3"><i class="fa fa-plus-circle"></i> Create New Contact</router-link>
     </p>
    </div>
    <div>
        <img class="img-fluid img-thumbnail rounded " src="../assets/contact-org2.png" alt="Responsive image"/>
    </div>
</div>

</template>

<script>
export default {
    name: "ContactManager"
}
</script>

<style>

</style>