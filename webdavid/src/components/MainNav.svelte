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
        <button id="btn-menumovil" type="button" class="button is-dark has-text-light is-medium is-responsive" aria-label="Botón Menu Móvil">
            <span class="icon">
                <i class="fa fa-bars"></i>
            </span>
        </button>
</div>
<div id="menu-movil" class="has-background-dark menu">
    <ul class="menu-list is-flex is-flex-direction-column is-justify-content-center is-align-items-center">
    {#each mainmenuitems as menuitem }
        {#if activo === menuitem.id}
            <li><a href={menuitem.url} target="_self" title={menuitem.titulo} class="menumovil-item-activo">{menuitem.titulo}</a></li>
        {:else}
            <li><a href={menuitem.url} target="_self" title={menuitem.titulo} class="menumovil-item">{menuitem.titulo}</a></li>
        {/if}
    {/each}
  </ul>
</div>

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
        width: 95%;
    }

    .menumovil-item
    {
        font-size: 1.2rem;
        color:white;
    }

     .menumovil-item-activo
    {
        font-size: 1.2rem;
        color:white;
        font-weight: bold;
    }
</style>

<script lang="ts">
    interface Props {
        activo:Number
    }
    let { activo }: Props = $props();

    const mainmenuitems = [
        {"id":1,"titulo":"Inicio","url":"/"},
        {"id":2,"titulo":"Blog","url":"https://www.blogdedavid.com"},
        {"id":3,"titulo":"Podcast","url":"/podcast"},
        {"id":4,"titulo":"Sobre Mí","url":"/about"},
        {"id":5,"titulo":"Contacto","url":"/contacto"},
    ];
</script>