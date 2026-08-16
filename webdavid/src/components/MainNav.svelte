<div id="main_nav" class="has-background-dark d-block mt-3">
    <ul id="main_nav_items" class="tabs is-flex-desktop is-hidden-touch w-100 is-flex-direction-rows is-justify-content-center is-align-items-center">
       {#each mainmenuitems as menuitem}
       {#if menuitem.id===activo}
        <li><a href={menuitem.url} target="_blank" title={menuitem.titulo} class="has-text-light menuitem_activo">{menuitem.titulo}</a></li>
       {:else}
         <li><a href={menuitem.url} target="_blank" title={menuitem.titulo} class="has-text-light menuitem">{menuitem.titulo}</a></li>
        {/if}
       {/each}
    </ul>
</div>
<div id="menu-movil-bar" class="has-background-dark is-flex-touch w-100 is-hidden-desktop is-flex-direction-row is-justify-content-baseline is-align-item-center pl-3">
        <button id="btn-menumovil" type="button" class="button is-dark has-text-light is-medium is-responsive" aria-label="Botón Menu Móvil" onclick={() => menu_movil()}>
            <span class="icon">
                <i class="fa fa-bars"></i>
            </span>
        </button>
</div>
{#if openmenu }
<div id="menu-movil" class="has-background-dark panel animate__animated animate__fadeInLeft">
    <header class="w-100 is-flex is-flex-direction-column has-background-success is-justify-content-flex-end is-align-items-center pr-3">
        <button id="btn-close-menu" class="button is-outlined is-light is-medium is-resposive" type="button" aria-label="Cerrar Menu Movil" onclick={() => menu_movil()}>
            <span class="icon"><i class="fa fa-times"></i></span>
        </button>
    </header>
    <ul class="is-flex is-flex-direction-column is-justify-content-center is-align-items-center is-gap-3 mt-3">
    {#each mainmenuitems as menuitem }
        {#if activo === menuitem.id}
            <li><a href={menuitem.url} target="_self" title={menuitem.titulo} class="button is-danger has-text-light botones-moviles">{menuitem.titulo}</a></li>
        {:else}
            <li><a href={menuitem.url} target="_self" title={menuitem.titulo} class="button is-success has-text-light botones-moviles">{menuitem.titulo}</a></li>
        {/if}
    {/each}
  </ul>
</div>
{/if}
<style>

    #main_nav
    {
        width: 95%;
    }

    .menuitem {
        font-size: 1.2rem;
    }

    .menuitem_activo {
        font-size: 1.2rem;
        font-weight: bold;
    }

    #menu-movil
    {
        width: 100%;
        height: 100vh;
        position: absolute;
        top:0;
        left:0;
        display: flex;
        flex-direction: column;
        justify-content: baseline;
        align-items: center;
    }

    #btn-close-menu
    {
        border-style: none;
    }

    .botones-moviles
    {
        width: 20rem;
    }
</style>

<script lang="ts">
    interface Props {
        activo:Number
    }
    let { activo }: Props = $props();
    let openmenu = $state(false);

    const mainmenuitems = [
        {"id":1,"titulo":"Inicio","url":"/"},
        {"id":2,"titulo":"Blog","url":"https://www.blogdedavid.com"},
        {"id":3,"titulo":"Podcast","url":"/podcast"},
        {"id":4,"titulo":"Sobre Mí","url":"/about"},
        {"id":5,"titulo":"Contacto","url":"/contacto"},
    ];

    function menu_movil() {
        openmenu = !openmenu;
    }
</script>