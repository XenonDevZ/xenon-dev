<script>
    const serverWidth = "50px";

    function openNav() {
        document.getElementById("mySidenav").style.width = null;
        document.getElementById("mySidenav").style.transition = "width 0.5s";
    }
</script>

<main>
    <div class="sidebar">
        <div class="sidebar-header">
            <div class="sidebar-header-logo">
                <img
                    src="https://media.discordapp.net/attachments/952764969638834228/969830435444097054/Criz.png"
                    alt=""
                    width={serverWidth}
                    on:click="{openNav}"
                />
            </div>
            <hr>
        </div>
    </div>
</main>

<style>
    
    .sidebar-header-logo {
        text-align: center;
        margin-top: 10px
    }

    .sidebar-header-logo img {
        width: 50px;
        height: 50px;
        border-radius: 50%;
        margin-right: 10px;
    }

    .sidebar-header-logo img:hover {
        border-radius: 10%;
        transition: all 0.3s ease-in-out;
    }

    @media screen and (max-width: 1500px) {
        .sidebar-header-logo img {
            width: 37px;
            height: 37px;
            margin-right: 5px;
        }
    }
    
</style>
