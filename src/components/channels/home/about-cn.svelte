<script>
    import Projects from '../categories/projects.svelte';
    import Links from '../categories/other.svelte';

    export function closeNav() {
        document.getElementById("mySidenav").style.width = "0";
        document.getElementById("mySidenav").style.transition = "width 0.5s";
    }
    
    export function openNav() {
        document.getElementById("mySidenav").style.width = null;
        document.getElementById("mySidenav").style.transition = "width 0.5s";
    }

    import { swipe } from "svelte-gestures";
    let direction;

    function handler(event) {
        direction = event.detail.direction;

        if (window.innerWidth < 1500) {
            if (direction == "left") {
                closeNav();
            } else if (direction == "right") {
                openNav();
            }
        }
    }
</script>

<main>
    <script src="https://kit.fontawesome.com/8dc570c5d4.js" crossorigin="anonymous"></script>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <div class="channels" id="mySidenav" use:swipe={{ timeframe: 300, minSwipeDistance: 0.1 }} on:swipe={handler}>
        <div>
            <div class="server-template-icon">
                <img
                    src="https://cdn.discordapp.com/attachments/977949070893125632/1010593053410599064/banner.png"
                    alt=""
                    width="100%"
                    height="100%"
                />
                <h3 class="server-name-on-template">Kurizu</h3>
                <span class="close-btn" on:click="{closeNav}">&times;</span>
            </div>
            <hr />
        </div>
        <div class="categories">
            <details class="home" open>
                <summary>Home</summary>
                <hr width="50%" />
                <div class="channels-list">
                    <button class="channelbtn">
                        <a class="home-cn" href="/"># Home</a>
                    </button>
                    <button class="channelbtn">
                        <a class="about-cn" href="/about"># About me</a>
                    </button>
                </div>
            </details>
            <br />
            <Projects />
            <br />
            <Links />
        </div>
    </div>
</main>

<style>

    ::-webkit-scrollbar {
        width: 5px;
    }

    ::-webkit-scrollbar-thumb {
        background: #888; 
    }

    ::-webkit-scrollbar-thumb:hover {
        background: #555; 
    }

    .channels {
        position: absolute;
        width: 14.1%;
        height: 100%;
        /* text-align: left; */
        margin-left: 82px;
        background-color: #2f3136;
        top: 0%;
        color: rgb(255, 255, 255);
        z-index: 0;
    }

    .server-template-icon {
        position: relative;
        width: 100%;
        height: 100%;
        background-color: #2f3136;
        border-radius: 10px;
        overflow: hidden;
    }

    .server-name-on-template {
        position: absolute;
        top: 3px;
        left: 20px;
    }

    .close-btn {
        /* position: absolute;
        top: 5%;
        left: 80%;
        font-size: 40px;
        cursor: pointer;
        color: orangered; */
        display: none;
    }

    .categories {
        text-align: left;
        margin-left: 10px;
    }

    .channels-list {
        margin-top: 0px;
        margin-left: 10px;
    }

    .channelbtn {
        background-color: #2f3136;
        color: rgb(255, 255, 255);
        border-radius: 10px;
        width: 100%;
        text-align: left;
        border: none;
        outline: none;
        cursor: pointer;
    }

    .channels-list a {
        color: rgb(158, 158, 158);
        text-decoration: none;
    }

    .channels-list a:hover {
        color: rgb(255, 255, 255);
        text-decoration: none;
    }

    summary {
        display: block;
    }

    summary::after {
        margin-left: 1ch;
        display: inline-block;
        transition: 0.2s;
        content: "\203A"; /* chevron */
    }

    details[open] summary::after {
        transform: rotate(90deg);
    }

    .about-cn {
        background: rgb(104, 104, 104) none repeat scroll 0 0;
        border-right: 5px none white;
        box-sizing: border-box;
        display: block;
        border-radius: 3px;
        padding: 5px;
    }
    
    .about-cn:hover {
        background: rgb(104, 104, 104) none repeat scroll 0 0;
        border-right: 5px none white;
        box-sizing: border-box;
        display: block;
        border-radius: 3px;
        padding: 5px;
        color: rgb(255, 255, 255);
    }

    .home-cn:hover {
        background: rgb(104, 104, 104) none repeat scroll 0 0;
        border-right: 5px none white;
        box-sizing: border-box;
        display: block;
        border-radius: 3px;
        padding: 3px;
        color: rgb(255, 255, 255);
    }

    @media screen and (max-width: 1910px) {
        .channels {
            position: absolute;
            width: 15.7%;
            height: 100%;
            margin-left: 82px;
            background-color: #2f3136;
            top: 0%;
            color: rgb(255, 255, 255);
            z-index: 1;
            overflow: scroll;

            font-size: small;
            /* display: none; */
        }

        .channelbtn {
            width: 75%;
        }
    }

    @media screen and (max-width: 1500px) {
        .channels {
            position: absolute;
            width: 20%;
            height: 100%;
            margin-left: 57px;
            background-color: #2f3136;
            top: 0%;
            color: rgb(255, 255, 255);
            z-index: 1;
            overflow: scroll;

            font-size: small;
            /* display: none; */
        }

        .channelbtn {
            width: 100%;
        }

        .close-btn {
            position: absolute;
            top: 5%;
            left: 80%;
            font-size: 35px;
            cursor: pointer;
            color: orangered;
            display: block;
        }

    }

    @media screen and (max-width: 1000px) {
        .channels {
            position: absolute;
            width: 40%;
            height: 100%;
            margin-left: 57px;
            background-color: #2f3136;
            top: 0%;
            color: rgb(255, 255, 255);
            z-index: 1;
            overflow: scroll;

            font-size: small;
            /* display: none; */
        }

        .channelbtn {
            width: 100%;
        }

        .close-btn {
            position: absolute;
            top: 5%;
            left: 80%;
            font-size: 35px;
            cursor: pointer;
            color: orangered;
            display: block;
        }
    }
</style>
