<script>
    import logo from '../img/nike.png'
    import blues from '../img/shoe1.png'
    import reds from '../img/shoe2.png'
    import { slide } from 'svelte/transition';
    let change = true;
    const changer = ()=>{
        console.log("just clicked")
        change = !change;
    }
</script>





<div class="flex h-screen bg-gray-900">
    <div class="container flex flex-col items-start w-1/3 mx-auto my-auto mt-16">
        <div class="relative items-center p-10 mx-auto bg-red-500 w-80 rounded-t-3xl h-72">
           <div class="flex space-x-10">
            <img src="{logo}" alt="logo" srcset="" class="pb-3" width="100" height="100"> 
           </div>
           {#if change}
           <div transition:slide="{{delay: 250, duration: 300, axis: 'x'}}">
            <img src="{reds}" alt="logo" srcset="" class="absolute z-40 transition delay-1000 -rotate-45 translate-x-10 -right-12 bottom-20" 
            width="350" height="350"> 
           </div>
           <div transition:slide="{{delay: 250, duration: 300, axis: 'x'}}">
            <img src="{blues}" alt="logo" srcset="" class="absolute z-40 transition delay-1000 -rotate-45 right-96 -top-96 bottom-20"
             width="350" height="350"> 
           </div>
           {:else}
           <div transition:slide="{{delay: 250, duration: 300, axis: 'x'}}">
            <img src="{reds}" alt="logo" srcset="" class="absolute z-40 transition delay-1000 -rotate-45 right-96 -top-96 bottom-20"
             width="350" height="350"> 
           </div>
           <div transition:slide="{{delay: 250, duration: 300, axis: 'x'}}">
            <img src="{blues}" alt="logo" srcset="" class="absolute z-40 transition delay-1000 rotate-12 -right-28 bottom-8" 
            width="350" height="350"> 
           </div>
           {/if}
           <div>
            <h4 class="pb-3 text-3xl leading-normal text-white">AIR STRUCTURE</h4>
           </div>
           <div class="text-white ">
            <p class="text-sm">Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae velit ea, voluptatem eveniet,
                 illum voluptate ipsum dolor sit amet consectetur</p>
           </div>
        </div>
        <div class="items-center p-10 mx-auto bg-white rounded-b-3xl h-72 w-80">
            <div class="flex space-x-10">
             <h4 class="text-xl leading-normal text-black">AIR STRUCTURE</h4>
             <p class="h-8 p-1 font-bold text-center text-white bg-green-500 rounded-md w-15">NEW</p>
            </div>
            <div class="flex flex-row space-y-5">
                <h4 class="text-sm leading-normal text-black">RUNNING COLLECTION</h4>
            </div>
            <div class="flex flex-col pt-7 ">
                <h4 class="text-sm leading-normal text-black">SIZE</h4>
                <div class="flex flex-row pt-3 space-x-5">
                    <p class="text-sm">7</p>
                    <p class="text-sm">8</p>
                    <p class="w-5 h-5 text-sm text-center bg-blue-300 rounded-full">9</p>
                    <p class="text-sm">10</p>
                    <p class="text-sm">11</p>
                </div>
            </div>
            <div class="relative flex flex-col pt-5 ">
                <h4 class="text-sm leading-normal text-black">COLOR</h4>
                <div class="flex flex-row items-center justify-between pt-2 space-x-32">
                    <div class="flex flex-row space-x-5">
                        <p class="w-5 h-5 text-center bg-blue-500 rounded-full" on:click={changer} on:keydown={changer}></p>
                        <p class="w-5 h-5 text-center bg-red-500 rounded-full" on:click={changer} on:keydown={changer}></p>
                    </div>
                    <div class="absolute shadow-xl left-10">
                       {#if change}
                       <p 
                        class="w-32 h-10 text-xl text-center text-white transition delay-1000 translate-x-10 bg-red-500 rounded-lg shadow-md">USD 350</p>
                       {:else}
                       <p
                        class="w-32 h-10 text-xl text-center text-white transition delay-1000 translate-x-10 bg-blue-500 rounded-lg shadow-md ">USD 350</p>
                       {/if}
                    </div>
                </div>
            </div>
         </div>

    </div>

</div>
