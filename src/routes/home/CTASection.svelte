<script>
	import Button from "$lib/components/Button/Button.svelte";
	import fbIcon from '$lib/images/icon/fb.svg';
	import igIcon from '$lib/images/icon/ig.svg';
	import inIcon from '$lib/images/icon/in.svg';
	import twIcon from '$lib/images/icon/tw.svg';
</script>

<section class="bg-gray-100 py-20 lg:py-[120px] overflow-hidden relative z-10">
   <div class="container">
    <div class="w-full  px-4">
        <div class="mb-12 mx-auto text-center">
           <h2
              class="
              text-dark
              mb-6
              uppercase
              font-bold
              text-[32px]
              sm:text-[40px]
              lg:text-[36px]
              xl:text-[40px]
              "
              >
              GET IN TOUCH WITH US
           </h2>
           <p class="text-base text-body-color leading-relaxed mb-9">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eius tempor incididunt ut labore et dolore magna aliqua. Ut enim
              adiqua minim veniam quis nostrud exercitation ullamco
           </p>
        </div>
     </div>
      <div class="flex flex-wrap lg:justify-between lg:mx-40 flex-col-reverse lg:flex-row">
         <div class="w-full lg:w-1/2 px-4">
            <div class="p-6 shadow-md max-w-md rounded-lg">
                <div class="flex items-center mt-2 text-gray-600">
                    <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" class="w-8 h-8 text-gray-500">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                    </svg>
                    <div class="ml-4 text-md tracking-wide font-semibold w-40">
                        info@column9.com
                        <br>
                        <p class="font-normal">lorem ispum lorem ispumlorem ispum </p>
                    </div>
                </div>



                <div class="flex items-center mt-4 text-gray-600">
                    <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" class="w-8 h-8 text-gray-500">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
                    </svg>
                    <div class="ml-4 text-md tracking-wide font-semibold w-40">
                        +44 1234567890
                        <br>
                        <p class="font-normal">lorem ispum lorem ispumlorem ispum </p>
                    </div>
                </div>

                <div class="flex items-center mt-8 text-gray-600">
                    <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" class="w-8 h-8 text-gray-500">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                    </svg>
                    <div class="ml-4 text-md tracking-wide font-semibold w-40">
                        Support Center
                        <br>
                        <p class="font-normal">lorem ispum lorem ispumlorem ispum </p>
                    </div>
                </div>

                <div class="flex my-10 justify-center space-x-16">
                    <a class="hover:opacity-75 relative" href="/" target="_blank" rel="noreferrer">
                      <div class="w-10 h-10 bg-gray-500 rounded-full flex items-center justify-center absolute inset-0 transform translate-x-[-50%] translate-y-[-50%]">
                        <img src={fbIcon} alt="Facebook" />
                      </div>
                    </a>
                    <a class="hover:opacity-75 relative" href="/" target="_blank" rel="noreferrer">
                      <div class="w-10 h-10 bg-gray-500 rounded-full flex items-center justify-center absolute inset-0 transform translate-x-[-50%] translate-y-[-50%]">
                        <img src={igIcon} alt="Instagram" />
                      </div>
                    </a>
                    <a class="hover:opacity-75 relative" href="/" target="_blank" rel="noreferrer">
                      <div class="w-10 h-10 bg-gray-500 rounded-full flex items-center justify-center absolute inset-0 transform translate-x-[-50%] translate-y-[-50%]">
                        <img src={inIcon} alt="LinkedIn" />
                      </div>
                    </a>
                    <a class="hover:opacity-75 relative" href="/" target="_blank" rel="noreferrer">
                      <div class="w-10 h-10 bg-gray-500 rounded-full flex items-center justify-center absolute inset-0 transform translate-x-[-50%] translate-y-[-50%]">
                        <img src={twIcon} alt="Twitter" />
                      </div>
                    </a>
                  </div>
                  

            </div>
         </div>

         <div class="w-full lg:w-1/2 xl:w-5/12 px-4">
            <div class="relative rounded-lg p-8 sm:p-12">
               <form>
                  <div class="mb-6">
                     <input
                        type="text"
                        placeholder="Your Name"
                        class="
                        w-full
                        rounded
                        py-3
                        px-[14px]
                        text-body-color text-base
                        border border-[f0f0f0]
                        outline-none
                        focus-visible:shadow-none
                        focus:border-primary
                        "
                        />
                  </div>
                  <div class="mb-6">
                     <input
                        type="email"
                        placeholder="Your Email"
                        class="
                        w-full
                        rounded
                        py-3
                        px-[14px]
                        text-body-color text-base
                        border border-[f0f0f0]
                        outline-none
                        focus-visible:shadow-none
                        focus:border-primary
                        "
                        />
                  </div>
                  <div class="mb-6">
                     <input
                        type="text"
                        placeholder="Your Phone"
                        class="
                        w-full
                        rounded
                        py-3
                        px-[14px]
                        text-body-color text-base
                        border border-[f0f0f0]
                        outline-none
                        focus-visible:shadow-none
                        focus:border-primary
                        "
                        />
                  </div>
                  <div class="mb-6">
                     <textarea
                        rows="6"
                        placeholder="Your Message"
                        class="
                        w-full
                        rounded
                        py-3
                        px-[14px]
                        text-body-color text-base
                        border border-[f0f0f0]
                        resize-none
                        outline-none
                        focus-visible:shadow-none
                        focus:border-primary
                        "
                        ></textarea>
                  </div>
                  <div class="flex justify-end">
                    <Button variant="secondary">Send</Button>
                  </div>
               </form>
            </div>
         </div>
      </div>
   </div>
</section>
