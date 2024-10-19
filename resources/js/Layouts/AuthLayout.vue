<script setup>
    import Sidebar from './Sidebar.vue';
    import TopBar from './TopBar.vue';
    const fullYear = new Date().getFullYear();
</script>
<template>
    
    <!-- Page Wrapper -->
    <div id="wrapper">

    <!-- Sidebar -->
    <Sidebar />
    <!-- End of Sidebar -->

    <!-- Content Wrapper -->
    <div id="content-wrapper" class="d-flex flex-column">

        <!-- Main Content -->
        <div id="content">

            <!-- Topbar -->
           <TopBar />
            <!-- End of Topbar -->

            <!-- Begin Page Content -->
            <div class="container-fluid">

                <slot />

            </div>
            <!-- /.container-fluid -->

        </div>
        <!-- End of Main Content -->

        <!-- Footer -->
        <footer class="sticky-footer bg-white">
            <div class="container my-auto">
                <div class="copyright text-center my-auto">
                    <span>Copyright &copy; Inventory {{ fullYear }}</span>
                </div>
            </div>
        </footer>
        <!-- End of Footer -->

    </div>
    <!-- End of Content Wrapper -->

    </div>
    <!-- End of Page Wrapper -->

    <!-- Scroll to Top Button-->
    <a class="scroll-to-top rounded" href="#page-top">
    <i class="fas fa-angle-up"></i>
    </a>
</template>
