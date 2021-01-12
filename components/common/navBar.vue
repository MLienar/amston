<template>
    <div class="navbar">
        <div class="logo">
            <img src="~assets/logo.svg" alt="logo Amston Beats">
        </div>
        <div class="links">
            <nav>
                <ul>
                    <li>music</li>
                    <li>mixing</li>
                    <li>contact</li>
                </ul>
            </nav>
        </div>
    </div>
</template>

<script>
export default {
    name:'navBar'
}
</script>

<style lang="scss">
    .navbar {
        width: 100vw;
        height: 12vh;
        background: white;
        display: flex;
        flex-flow: row nowrap;
        justify-content: space-between;
        align-items: center;
        .logo {
            margin-left: 5vw;
            height: 37%;
            img {
                height: 100%;
                width: auto;
            }
        }
        ul {
            display: flex; 
            flex-flow: row nowrap;
            list-style: none;
            li {
                margin-right: 5vw;
                cursor: pointer;
            }
        }
    }
</style>