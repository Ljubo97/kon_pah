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
    import { combinePaths } from "svelte-routing/src/utils";
    

  export let location;
  export let admin = "admin";
</script>

<div>
  <Sidebar location={location}/>
  <div class="relative md:ml-64 bg-blueGray-100">
    <AdminNavbar />
    <HeaderStats />
    <div class="px-4 md:px-10 mx-auto w-full -m-24">
      <Router url="admin">
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
