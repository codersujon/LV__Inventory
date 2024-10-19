<script setup>
    import {
        Head,
        Link,
        useForm
    } from '@inertiajs/vue3';

    const form = useForm({
        name: '',
        email: '',
        password: '',
        password_confirmation: '',
    });

    const submit = () => {
        form.post(route('register'), {
            onFinish: () => form.reset('password', 'password_confirmation'),
        });
    };

</script>
<template>

    <Head title="Register" />

    <div class="container-fluid mt-5 pt-5">
        <div class="container">
            <div class="card o-hidden border-1">
                <div class="card-body p-0">
                    <!-- Nested Row within Card Body -->
                    <div class="row">
                        <!-- <div class="col-lg-5 d-none d-lg-block bg-register-image"></div> -->
                        <div class="col-lg-6 offset-lg-3">
                            <div class="p-5">
                                <div class="text-center">
                                    <h1 class="h4 text-gray-900 mb-4">Create an Account!</h1>
                                </div>

                                <form @submit.prevent="submit">

                                    <!-- Name -->
                                    <div class="form-group">
                                        <input type="text" class="form-control form-control-user" id="name"
                                            placeholder="Name" v-model="form.name" required autofocus
                                            autocomplete="name">
                                        <InputError class="mt-2" :message="form.errors.name" />
                                    </div>

                                    <!-- Email Address -->
                                    <div class="form-group">
                                        <input type="email" class="form-control form-control-user" id="email"
                                            placeholder="Email Address" v-model="form.email" required
                                            autocomplete="username">
                                        <InputError class="mt-2" :message="form.errors.email" />
                                    </div>

                                    <!-- Password -->
                                    <div class="form-group">
                                        <input type="password" id="password" v-model="form.password"
                                            class="form-control form-control-user" placeholder="Password" required
                                            autocomplete="new-password">
                                        <InputError class="mt-2" :message="form.errors.password" />
                                    </div>

                                    <!-- Password Confirmation -->
                                    <div class="form-group">
                                        <input type="password" v-model="form.password_confirmation"
                                            class="form-control form-control-user" id="password_confirmation"
                                            placeholder="Confirm Password" required autocomplete="new-password">
                                        <InputError class="mt-2" :message="form.errors.password_confirmation" />
                                    </div>

                                    <button type="submit" class="btn btn-primary btn-user btn-block"
                                        :disabled="form.processing" :class="{ 'opacity-25': form.processing }">
                                        Register
                                    </button>

                                    <hr>
                                    <a href="index.html" class="btn btn-google btn-user btn-block">
                                        <i class="fab fa-google fa-fw"></i> Register with Google
                                    </a>
                                    <a href="index.html" class="btn btn-facebook btn-user btn-block">
                                        <i class="fab fa-facebook-f fa-fw"></i> Register with Facebook
                                    </a>

                                </form>

                                <hr>
                                <div class="text-center">
                                    <Link class="small" :href="route('login')">Forgot Password?</Link>
                                </div>
                                <div class="text-center">
                                    <Link class="small" :href="route('login')">Already have an account? Login!
                                    </Link>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>
