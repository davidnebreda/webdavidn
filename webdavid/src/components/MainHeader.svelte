<header id="main-header" class="w-100 is-flex is-flex-direction-row is-justify-content-space-between is-align-items-center py-3 px-3">
    <div id="main-header-left" class="is-flex is-flex-direction-row is-align-items-center pl-3">
       
            <img src={DnsLogo} width="96" height="96" class="has-ratio" alt="David Nebreda Logo">
       
    </div>
   <div id="main-header-left" class="is-inline-flex is-flex-direction-row is-align-items-center pr-3">
       <ul id="menu-social" class="is-inline-flex is-flex-direction-row is-align-items-center is-gap-1">
          <li>
            <a href="/" title="Facebook" class="button is-outlined is-dark menu-social-botones is-small" target="_blank">
              <img src={FbLogo} alt="Facebook Logo" width="32" height="32">
          </a>
        </li>
        <li>
            <a href="/" title="X" class="button is-outlined is-dark menu-social-botones is-small" target="_blank">
             <img src={FbX} alt="X Logo" width="32" height="32">
          </a>
        </li>
         <li>
            <a href="/" title="Linkedin" class="button is-outlined is-dark menu-social-botones is-small" target="_blank">
             <img src={LinkedinLogo} alt="Linkedin Logo" width="32" height="32">
          </a>
        </li>
       </ul>
    </div>
</header>

<style>
    #menu-social
    {
        list-style: none;
    }

    .menu-social-botones
    {
        border-style: none;
    }
</style>

<script lang="ts">
    import DnsLogo from '../assets/images/logo_dns.png';
    import FbLogo from '../assets/images/facebook.png';
    import FbX from '../assets/images/x.png';
    import LinkedinLogo from '../assets/images/linkedin.png';
</script>