<script>
    import NavBar from "$lib/navbar.svelte"
    let imageNumber = "1"
    function changeActiveImage (event,number){
        console.log("clicked")
        let active = document.querySelector(".active")
        if (active){
            active.classList.remove("active")
        }
        console.log(event)
        event.target.classList.add('active');
        imageNumber = number;
        console.log(imageNumber)
    }
</script>

<NavBar/>
<section class="flex justify-center gap-24 items-center">
    <div class="w-[30%]">
        <img src="images/image-product-{imageNumber}.jpg" class="rounded-lg " alt="">
        <div class="flex justify-between little pt-8">
            <img src="images/image-product-1-thumbnail.jpg" alt="" class="active" on:click={()=>changeActiveImage(event,1)}>
            <img src="images/image-product-2-thumbnail.jpg" alt="" on:click={()=>changeActiveImage(event, 2)}>
            <img src="images/image-product-3-thumbnail.jpg" alt="" on:click={()=>changeActiveImage(event,3)}>
            <img src="images/image-product-4-thumbnail.jpg" alt="" on:click={()=>changeActiveImage(event,4)}>
        </div>
    </div>
    <div class="w-[30%] flex flex-col gap-8">
        <p class="title">sneaker company</p>
        <h1 class="name">Fall Limited Edition Sneakers</h1>
        <p class="description">These low-profile sneakers are your perfect casual wear companion. Featuring a durable
            rubber outer sole,
            they’ll withstand everything the weather can offer.</p>
        <div>
            <p class="price">$125.00</p>
        </div>
        <div class="flex justify-between">
            <div class="flex justify-around items-center w-[157px] bg-[#F6F8FD] py-2 rounded-lg colored-svg">
                <svg width="12" height="4" xmlns="http://www.w3.org/2000/svg"
                     xmlns:xlink="http://www.w3.org/1999/xlink">
                    <defs>
                        <path d="M11.357 3.332A.641.641 0 0 0 12 2.69V.643A.641.641 0 0 0 11.357 0H.643A.641.641 0 0 0 0 .643v2.046c0 .357.287.643.643.643h10.714Z"
                              id="a"/>
                    </defs>
                    <use fill="#FF7E1B" fill-rule="nonzero" xlink:href="#a"/>
                </svg>
                <span>0</span>
                <svg width="12" height="12" xmlns="http://www.w3.org/2000/svg"
                     xmlns:xlink="http://www.w3.org/1999/xlink">
                    <defs>
                        <path d="M12 7.023V4.977a.641.641 0 0 0-.643-.643h-3.69V.643A.641.641 0 0 0 7.022 0H4.977a.641.641 0 0 0-.643.643v3.69H.643A.641.641 0 0 0 0 4.978v2.046c0 .356.287.643.643.643h3.69v3.691c0 .356.288.643.644.643h2.046a.641.641 0 0 0 .643-.643v-3.69h3.691A.641.641 0 0 0 12 7.022Z"
                              id="b"/>
                    </defs>
                    <use fill="#FF7E1B" fill-rule="nonzero" xlink:href="#b"/>
                </svg>
            </div>
            <button class="flex w-3/5 bg-[#FF7E1B] text-white justify-center items-center gap-4 rounded-lg add">
                <svg width="22" height="20" xmlns="http://www.w3.org/2000/svg">
                    <path d="M20.925 3.641H3.863L3.61.816A.896.896 0 0 0 2.717 0H.897a.896.896 0 1 0 0 1.792h1l1.031 11.483c.073.828.52 1.726 1.291 2.336C2.83 17.385 4.099 20 6.359 20c1.875 0 3.197-1.87 2.554-3.642h4.905c-.642 1.77.677 3.642 2.555 3.642a2.72 2.72 0 0 0 2.717-2.717 2.72 2.72 0 0 0-2.717-2.717H6.365c-.681 0-1.274-.41-1.53-1.009l14.321-.842a.896.896 0 0 0 .817-.677l1.821-7.283a.897.897 0 0 0-.87-1.114ZM6.358 18.208a.926.926 0 0 1 0-1.85.926.926 0 0 1 0 1.85Zm10.015 0a.926.926 0 0 1 0-1.85.926.926 0 0 1 0 1.85Zm2.021-7.243-13.8.81-.57-6.341h15.753l-1.383 5.53Z"
                          fill="currentColor" fill-rule="nonzero"/>
                </svg>
                <span>Add to cart</span>
            </button>
        </div>
    </div>
</section>

<style>
    .little img {
        width: 20%;
        aspect-ratio: 1;
        border-radius: 0.5rem;
        cursor: pointer;
    }
    .little img.active{
        /*filter: grayscale(100%);*/
        border: 2px solid #FF7E1B;
        border-radius: 10px;
    }


    .title {
        font-weight: 700;
        letter-spacing: 2px;
        text-transform: uppercase;
        color: #FF7E1B;
    }

    .name, .price {
        font-weight: 700;
        font-size: 44px;
        line-height: 48px;
        color: #1D2026;
    }

    .price {
        font-size: 1.7rem;
    }

    .description {
        color: #69707D;
    }
    .add:hover{
        background-color: #FFAB6A;
        box-shadow: 0px 20px 50px -20px #FF7E1B;
    }
</style>