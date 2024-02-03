<template>
    <div class="mx-auto">
        <section class="layers px-[30px]">
            <div class="layers__container">
                <div
                    class="layers__item layer-1"
                    style="background-image: url(/6.jpg)"
                ></div>
                <div
                    class="layers__item layer-2"
                    style="background-image: url(/5.png)"
                ></div>
                <div
                    class="layers__item layer-3"
                    style="background-image: url(/4.png)"
                ></div>
                <div
                    class="layers__item layer-4"
                    style="background-image: url(/3.png)"
                ></div>

                <div
                    class="layers__item layer-5"
                    style="background-image: url(/2.png)"
                ></div>
                <div
                    class="layers__item layer-6"
                    style="background-image: url(/1.png)"
                ></div>
            </div>
        </section>
        <div
            class="h-[100dvh] bg-[#424146] shadow-[0_-10px_60px_-15px_rgba(0,0,0,0.3)] py-12 px-[30px]"
        >
            <div
                class="max-w-[1280px] mx-auto flex items-center justify-center group"
            >
                <img
                    class="rounded-xl w-[500px] mr-[-5%] group-hover:mr-[-3%] transition-all delay-200 duration-500"
                    src="/2.jpeg"
                    alt=""
                />
                <p
                    class="w-[500px] font-mono text-white leading-9 text-lg z-10 flex flex-col justify-end gap-32"
                >
                    <span
                        class="font-semibold text-2xl group-hover:text-3xl delay-200 transition-all duration-500"
                        >Рагулина Маргарита <br
                    /></span>

                    <span>
                        Менеджер по связам с общественностью ( PR ) <br />

                        Я предоставляю услуги PR менеджера. Мой опыт работы
                        составляет 2 года. Я общяюсь с большим количеством людей
                        и работаю для дальнейшего улучшения организации.
                    </span>
                </p>
            </div>
        </div>
        <section
            class="pt-[100px] bg-[#F2F1ED] w-[100dvw] h-[100dvh] px-[30px]"
        >
            <div
                class="max-w-[980px] mx-auto flex flex-col justify-start gap-20"
            >
                <h2 class="text-4xl font-mono font-bold tracking-wider">
                    Направления работы
                </h2>
                <p
                    class="text-2xl font-sans font-seimbold w-[600px] leading-8 tracking-wide"
                >
                    Я специализируюсь на статьях и онлайн курсах "Связь с
                    общественностью". <br />
                    <br />
                    Провожу опросы и общаюсь с большим количеством людей. <br />
                    <br />
                    Узнаю их мнение об организации, какие они хотели бы внести
                    изменения для улучшения организации. <br />
                    <br />Я могу придумать креативные идеи, найти подходящий
                    язык в общении с людьми, имею позитивное отношение к людям.
                </p>
            </div>
        </section>
    </div>
</template>

<script setup>
import { computed, onMounted, onUnmounted, watch } from "vue";
onMounted(() => {
    document.addEventListener("mousemove", (e) => {
        Object.assign(document.documentElement, {
            style: `
		--move-x: ${(e.clientX - window.innerWidth / 2) * -0.005}deg;
		--move-y: ${(e.clientY - window.innerHeight / 2) * 0.01}deg;
		`,
        });
    });
    window.addEventListener("devicemotion", motion_hook, false);

    // Обработчик события DeviceMotionEvent
    function motion_hook(event) {
        Object.assign(document.documentElement, {
            style: `
		--move-x: ${
            (event.accelerationIncludingGravity.x - window.innerWidth / 2) *
            -0.005
        }deg;
		--move-y: ${(event.accelerationIncludingGravity.y / 2) * 0.01}deg;
		`,
        });
        console.log("Z=" + event.accelerationIncludingGravity.z);
    }
});
</script>

<style>
/* .back-head-img {
    background-attachment: fixed;
    background-size: contain;
    background-position: center;
    background-repeat: no-repeat;
    background-image: url("1.jpeg");
} */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
:root {
    --index: calc(1vw + 1vh);
    --transition: 1.5s cubic-bezier(0.05, 0.5, 0, 1);
}

.logo {
    --logo-size: calc(var(--index) * 7.8);
    width: var(--logo-size);
    height: var(--logo-size);
    background-repeat: no-repeat;
    position: absolute;
    left: calc(51% - calc(var(--logo-size) / 2));
    top: calc(var(--index) * 2.8);
    z-index: 1;
}
.layers {
    perspective: 1000px;
    overflow: hidden;
    background-color: #f1f1f1;
}
.layers__container {
    scale: 0.5;
    height: 100vh;
    min-height: 500px;
    transform-style: preserve-3d;
    transform: rotateX(var(--move-y)) rotateY(var(--move-x));
    will-change: transform;
    transition: transform var(--transition);
}
.layers__item {
    position: absolute;
    inset: -5vw;
    background-size: cover;
    background-position: center;
    display: flex;
    align-items: center;
    justify-content: center;
}
.layer-1 {
    transform: translateZ(-55px) scale(1.06);
}
.layer-2 {
    transform: translateZ(80px) scale(0.88);
}
.layer-3 {
    transform: translateZ(180px) scale(0.8);
}
.layer-4 {
    transform: translateZ(190px) scale(0.9);
}
.layer-5 {
    transform: translateZ(300px) scale(0.9);
}
.layer-6 {
    transform: translateZ(380px);
}
.hero-content {
    font-size: calc(var(--index) * 2.9);
    text-align: center;
    text-transform: uppercase;
    letter-spacing: calc(var(--index) * -0.15);
    line-height: 1.35em;
    margin-top: calc(var(--index) * 5.5);
}
.hero-content span {
    display: block;
}
.hero-content__p {
    text-transform: none;
    font-family: merriweather-italic-3d;
    letter-spacing: normal;
    font-size: calc(var(--index) * 0.73);
    line-height: 3;
}
.button-start {
    font-family: Arial;
    font-weight: 600;
    text-transform: uppercase;
    font-size: calc(var(--index) * 0.71);
    letter-spacing: -0.02vw;
    padding: calc(var(--index) * 0.7) calc(var(--index) * 1.25);
    background-color: transparent;
    color: #fff;
    border-radius: 10em;
    border: rgb(255 255 255 / 0.4) 3px solid;
    outline: none;
    cursor: pointer;
    margin-top: calc(var(--index) * 2.5);
}
.layer-4,
.layer-5,
.layer-6 {
    pointer-events: none;
}
</style>
