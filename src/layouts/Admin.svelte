<script>
  import { Router, Route } from "svelte-routing";

  // components for this layout
  import AdminNavbar from "components/Navbars/AdminNavbar.svelte";
  import Sidebar from "components/Sidebar/Sidebar.svelte";
  import HeaderStats from "components/Headers/HeaderStats.svelte";
  import FooterAdmin from "components/Footers/FooterAdmin.svelte";

  // pages for this layout
  import DodajUlaz from "../views/admin/DodajUlaz.svelte";
  import DodajStanara from "../views/admin/DodajStanara.svelte";
  import DodajIzvod from "../views/admin/DodajIzvod.svelte";
  import Dashboard from "views/admin/Dashboard.svelte";
  import Settings from "views/admin/Settings.svelte";
  import Tables from "views/admin/Tables.svelte";
  import Maps from "views/admin/Maps.svelte";
    
    import KarticePlacanja from "../views/admin/KarticePlacanja.svelte";
    import ZavediUplatu from "../views/admin/ZavediUplatu.svelte";
    import ObrisiIzvod from "../views/admin/ObrisiIzvod.svelte";
    import ObrisiStanara from "../views/admin/ObrisiStanara.svelte";
    import ObrisiUlaz from "../views/admin/ObrisiUlaz.svelte";
    import IzmjeniIzvod from "../views/admin/IzmjeniIzvod.svelte";
    import IzmjeniStanara from "../views/admin/IzmjeniStanara.svelte";
    import IzmjeniUlaz from "../views/admin/IzmjeniUlaz.svelte";
    
    

  export let location;
  export let admin = "";
</script>

<div>
  <Sidebar location={location}/>
  <div class="relative md:ml-64 bg-blueGray-100">
    <AdminNavbar />
    <HeaderStats />
    <div class="px-4 md:px-10 mx-auto w-full -m-24">
      <Router url="admin">
        <Route path="obrisiizvod" component="{ObrisiIzvod}" />
        <Route path="obrisiulaz" component="{ObrisiUlaz}" />

        <Route path="obrisistanara" component="{ObrisiStanara}" />
        <Route path="izmjeniizvod" component="{IzmjeniIzvod}" />
        <Route path="izmjeniulaz" component="{IzmjeniUlaz}" />

        <Route path="izmjenistanara" component="{IzmjeniStanara}" />
        <Route path="karticeplacanja" component="{KarticePlacanja}" />
        <Route path="zavediuplatu" component="{ZavediUplatu}" />



        <Route path="dodajulaz" component="{DodajUlaz}" />
        <Route path="dodajstanara" component="{DodajStanara}" />

        <Route path="dodajizvod" component="{DodajIzvod}" />
        <Route path="dashboard" component="{Dashboard}" />
        <Route path="settings" component="{Settings}" />
        <Route path="tables" component="{Tables}" />
        <Route path="maps" component="{Maps}" />
      </Router>
      <FooterAdmin />
    </div>
  </div>
</div>
