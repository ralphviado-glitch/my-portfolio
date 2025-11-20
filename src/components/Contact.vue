<script setup>
    import {ref, onMounted, onBeforeUnmount} from 'vue';

    import {Notyf} from "notyf";
    import 'notyf/notyf.min.css';
    const notyf = new Notyf();

    const WEB3FORMS_ACCESS_KEY = "428bb2ad-3e7a-4163-b606-735d65275442";

    const subject = "New Message from Portfolio Contact Form";
    const name = ref("");
    const email = ref("");
    const message = ref("");

    const isLoading = ref(false);

    const submitForm = async () => {

        if(!recaptchaToken.value) {
            notyf.error("Please verify that you are not a robot.");
            return;
        }

        isLoading.value = true;

        try {
            const response = await fetch("https://api.web3forms.com/submit", {

                method: "POST",
                headers: {
                    "Content-Type": "application/json",
                    Accept: "application/json"
                },
                body: JSON.stringify({
                    access_key: WEB3FORMS_ACCESS_KEY,
                    subject: subject,
                    name: name.value,
                    email: email.value,
                    message: message.value
                })
            });

            const result = await response.json();
            if(result.success) {
                console.log(result);

                isLoading.value = false;
                notyf.success("Message Sent!");
            }
        } catch (error) {

            console.log(error)

            isLoading.value = false;
            notyf.error("Failed to send message");

        } finally {

            resetRecaptcha();

        }
    }

    const SITE_KEY = '6Ldm0xIsAAAAAMb5dze_tkzvUoSPbIJirYAhRl57';

    const recaptchaContainer = ref(null);
    const recaptchaWidgetId = ref(null);
    const recaptchaToken = ref('');

    function onRecaptchaSuccess(token) {
        recaptchaToken.value = token
    }

    function onRecaptchaExpired() {
        recaptchaToken.value = '';
    }

    function renderRecaptcha() {
        if(!window.grecaptcha) {
            console.error('reCAPTCHA not loaded');
            return;
        }

        recaptchaWidgetId.value = window.grecaptcha.render(
            recaptchaContainer.value, {
            sitekey: SITE_KEY,
            size: 'normal',
            callback: onRecaptchaSuccess,
            'expired-callback' : onRecaptchaExpired
        })

    }

    function resetRecaptcha() {
        if(recaptchaWidgetId.value !== null) {
            window.grecaptcha.reset(recaptchaWidgetId.value);
            recaptchaToken.value = ''
        }
    }

    onMounted(() => {
        const interval = setInterval(() => {
            if(window.grecaptcha && window.grecaptcha.render) {
                renderRecaptcha();
                clearInterval(interval);
            }
        }, 100)

        onBeforeUnmount(() => {
            clearInterval(interval);
        })
    })
</script>

<template>
	<!-- contact -->
	<div class="container-fluid" id="contact">
		<div class="row d-grid gap-2 d-flex justify-content-md-center">	

			<div class="col-md-12 col-lg-6 pt-5">
				<h2 id="contact-title" class="px-3 pb-3 text-center">Contact Me</h2>
				<form @submit.prevent="submitForm">
					<div class="form-group">
						<label class="mb-2" for="name">Name</label>
						<input type="text" v-model="name" class="form-control contact-form-control" placeholder="First Name M.I. Last Name">						
					</div>
					<div class="form-group">
						<label class="mt-3 mb-2" for="email">Email Address</label>
						<input type="email" v-model="email" class="form-control contact-form-control" placeholder="Email">	
					</div>
					<div class="form-group">
						<label class="mt-3 mb-2" for="message">Message</label>
						<textarea v-model="message" class="form-control contact-form-control" rows="6" placeholder="Message"></textarea>
					</div>
					<div class="mt-4 d-grid gap-2 d-md-flex mb-5">
						<button type="submit" class="btn btn-secondary" :disabled="isLoading">
                        {{isLoading ? "Sending..." : "Submit"}}
                    </button>

                        <!-- Recaptcha checkbox -->
                    <div class="d-flex justify-content-end mt-2">
                        <div ref="recaptchaContainer"></div>
                    </div>
					</div>
				</form>
			</div>	
		</div>		
	</div>
</template>