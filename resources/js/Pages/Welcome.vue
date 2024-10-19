<script setup>
import { Head, Link } from '@inertiajs/vue3';
</script>

<template>
    <Head title="SB Admin" />
    <div class="d-flex vh-100 align-items-center justify-content-center">
        <Link :href="route('login')" class="btn btn-lg btn-success mx-2">Login</Link>
        <Link :href="route('register')" class="btn btn-lg btn-primary mx-2">Register</Link>
    </div>
    
</template>
