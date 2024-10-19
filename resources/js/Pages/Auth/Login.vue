<script setup>
    import {
        Head,
        Link,
        useForm
    } from '@inertiajs/vue3';

    defineProps({
        canResetPassword: {
            type: Boolean,
        },
        status: {
            type: String,
        },
    });

    const form = useForm({
        email: '',
        password: '',
        remember: false,
    });

    const submit = () => {
        form.post(route('login'), {
            onFinish: () => form.reset('password'),
        });
    };

</script>

<template>

    <Head title="Log in" />
    <div class="container mt-5">
        <!-- Outer Row -->
        <div class="row justify-content-center">

            <div class="col-xl-10 col-lg-12 col-md-9">

                <div class="card o-hidden border-1 my-5">
                    <div class="card-body p-0">
                        <!-- Nested Row within Card Body -->
                        <div class="row">
                            <!-- <div class="col-lg-6 d-none d-lg-block bg-login-image"></div> -->
                            <div class="col-lg-6 offset-lg-3">
                                <div class="p-5">
                                    <div class="text-center">
                                        <h1 class="h4 text-gray-900 mb-4">Welcome Back!</h1>
                                    </div>

                                    <form @submit.prevent="submit">

                                        <!-- Email -->
                                        <div class="form-group">
                                            <input type="email" class="form-control form-control-user"
                                            id="email"  v-model="form.email" required autofocus autocomplete="username"
                                                placeholder="Email Address...">
                                            <InputError class="mt-2" :message="form.errors.email" />
                                        </div>

                                        <!-- Password -->
                                        <div class="form-group">
                                            <input type="password" v-model="form.password" autocomplete="current-password" required class="form-control form-control-user"
                                            id="password" placeholder="Password">
                                            <InputError class="mt-2" :message="form.errors.password" />
                                        </div>

                                        <!-- CheckBox -->
                                        <div class="form-group">
                                            <div class="custom-control custom-checkbox small">
                                                <input type="checkbox" name="remember" class="custom-control-input" id="remember" v-model="form.remember">
                                                <label class="custom-control-label" for="customCheck">Remember
                                                    Me</label>
                                            </div>
                                        </div>

                                        <button type="submit" class="btn btn-primary btn-user btn-block">
                                            Login
                                        </button>

                                        <hr>

                                        <a href="index.html" class="btn btn-google btn-user btn-block">
                                            <i class="fab fa-google fa-fw"></i> Login with Google
                                        </a>
                                        <a href="index.html" class="btn btn-facebook btn-user btn-block">
                                            <i class="fab fa-facebook-f fa-fw"></i> Login with Facebook
                                        </a>
                                    </form>

                                    <hr>
                                    <div class="text-center">
                                        <Link class="small" :href="route('login')">Forgot Password?</Link>
                                    </div>
                                    <div class="text-center">
                                        <Link class="small" :href="route('register')">Create an Account!</Link>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

            </div>

        </div>
    </div>

</template>
