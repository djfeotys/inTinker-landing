<style>
.vertical-slider>* {
    /* selects all immediate children of .vertical-slider, which includes div.right-side */
    /* width: 50%; */
}

.sticky {
    position: sticky;
    top: 0px;
    height: 100%;
    /* max-height: 100vh; */
}

.absolute-full {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

/* starting position */
.image-wrapper .mask-outer {
    transform: translateY(100%);
    overflow: hidden;
    transition: transform 0.5s ease-out 0.5s;
}

.image-wrapper .mask-inner {
    transform: translateY(-100%);
    transition: transform 0.5s ease-out 0.5s;
}

/* show state */
.image-wrapper.show .mask-outer {
    transform: translateY(0);
    transition: transform 0.5s ease-out 0.5s;
}

.image-wrapper.show .mask-inner {
    transform: translateY(0);
    transition: transform 0.5s ease-out 0.5s;
}

.content-wrapper {
    min-height: 50vh;
    opacity: 0.2;
    transition: opacity 0.5s ease-out;
}

.content-wrapper.in-view {
    opacity: 1;
    transition: opacity 0.5s ease-out;
}

/* starting position */
.image-wrapper .mask-outer {
    transform: translateY(100%);
    overflow: hidden;
    transition: transform 0.5s ease-out 0.5s;
}

.image-wrapper .mask-inner {
    transform: translateY(-100%);
    transition: transform 0.5s ease-out 0.5s;
}

/* show state */
.image-wrapper.show .mask-outer {
    transform: translateY(0);
    transition: transform 0.5s ease-out 0.5s;
}

.image-wrapper.show .mask-inner {
    transform: translateY(0);
    transition: transform 0.5s ease-out 0.5s;
}

.content-wrapper {
    /* min-height: 100vh; */
    opacity: 0.2;
    transition: opacity 1.5s ease-out;
}

.content-wrapper.in-view {
    opacity: 1;
    transition: opacity 1.5s ease-out;
}

.image {
    border-radius: 5px;
    margin-top: 5px;
    box-shadow: 10 10 10;
}
</style>


<template>
    <div class="flex flex-col align-center w-1/2   hidden sm:flex">
        <div class="desktop-only vertical-slider">
            <div class="right-side relative ">
                <section v-for="(content, index) in contents" :key="index" class="content-wrapper sticky" style="top:10%"
                    :data-index="index">
                    <div class="content sm:w-[650px] bg-white h-[500px] pt-4" :class="{ 'in-view': activeIndex === index }">
                        <img :src="content.image" class="image" style="display: flex;" />
                    </div>
                </section>
            </div>
        </div>
    </div>
</template>
  
<script lang="ts">
export default {
    data() {
        return {
            contents: [
                {
                    image: "/img(sec7-1).svg",

                },
                {
                    image: "/img(sec7-2).svg",
                },
                {
                    image: "/img(sec7-3).svg",
                },
                {
                    image: "/img(sec7-4).svg",
                },
                {
                    image: "/img(sec7-5).svg",
                },
                {
                    image: "/img(sec7-6).svg",
                },
                {
                    image: "/img(sec7-7).svg",
                },
            ],
            activeIndex: null,
            options: {
                root: null, // use the viewport as the root
                rootMargin: "0px", // no margin
                threshold: 0.5, // 50% of the target element must be visible
            }
        };
    },
    mounted() {
        // Select all image wrappers
        const imageWrappers = document.querySelectorAll(
            ".vertical-slider.desktop-only .left-side .image-wrapper"
        );

        function callback(entries, observer) {
            entries.forEach((entry) => {
                const currentContentWrapper = entry.target;

                if (entry.isIntersecting) {
                    currentContentWrapper.classList.add("in-view");
                } else {
                    currentContentWrapper.classList.remove("in-view");
                }
            });
        }

        // Interaction Observer for each content section (right side)
        const observer = new IntersectionObserver(callback, this.options);
        const contentWrappers = document.querySelectorAll(
            ".vertical-slider.desktop-only .right-side .content-wrapper"
        );

        contentWrappers.forEach((wrapper) => {
            observer.observe(wrapper);
        });
    },
};
</script>
  