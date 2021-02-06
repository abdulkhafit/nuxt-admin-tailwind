<template>
    <div>
        <Nuxt/>
    </div>
</template>

<script>
export default {
    head : {
     link : [
      { rel : 'stylesheet', href : 'https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap'},
      { rel:'stylesheet' , href: '/vendors/styles/core.css' },
      { rel:'stylesheet' , href: '/vendors/styles/icon-font.min.css' },
      { rel:'stylesheet' , href: '/vendors/styles/style.css' },
    ],
    script : [
        { src: 'vendors/scripts/core.js' } , 
        { src: 'vendors/scripts/script.min.js' } , 
        { src: 'vendors/scripts/process.js' } , 
        { src: 'vendors/scripts/layout-settings.js' } , 
        // { src: '/src/plugins/apexcharts/apexcharts.min.js' } , 
        // { src: 'src/plugins/datatables/js/jquery.dataTables.min.js' } , 
        // { src: '/src/plugins/datatables/js/dataTables.bootstrap4.min.js' } , 
        // { src: '/src/plugins/datatables/js/dataTables.responsive.min.js' } , 
        // { src: '/src/plugins/datatables/js/responsive.bootstrap4.min.js' } , 
        // { src: '/vendors/scripts/dashboard.js' } , 
    ]
 }
}
</script>

<style scoped>
 /* @import '~/assets/vendors/styles/core.css'; */
</style>