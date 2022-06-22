<h2>Implementace</h2>
<p>K implementaci projektu jsme využili PHP framework Laravel verzi 5.5.22. Námi vytvořený informační systém je postaven na architektuře MVC (model-view-contoler). Tato architektura rozděluje aplikaci do tří nezávislých částí tak, že modifikace kterékoli z nich má jen minimální vliv na ostatní.</p>
<h3>Modely</h3>
<p>Modely se nachází ve složce '/app'. Pro každou entitní množinu se zde nachází jeden model, který je pojmenován shodně s názvem entitní množiny. Vyjímkou je implementace modelu person, ten je řešen v modelu '/app/User.php', kvůli jeho využití jako modelu pro správu uživatelů informačního systému.</p>
<h3>Kontrolery</h3>
<p>Kontrolery se nachází ve složce '/app/Http/Controllers'. Pro každý model se zde nachází jeden kontroler, který obsahuje funkce, kterými zprostředkovává data pro jednotlivé pohledy. Kontroler '/app/Http/Controllers/SessionsController.php' se stará o autorizaci a autentifikaci uživatelů.</p>
<h3>Pohledy</h3>
<p>Pohledy se nachází ve složce '/resources/views'. Počet pohledů neodpovídá ani počtu modelů, ani počtu kontrolerů, jejich počet odpovídá počtu stránek, které využívá náš informační systém. K implementaci jednotlivých stránek využíváme prostředku blade, který nám usnadňuje hromadné úpravy uživatelského rozhraní bez nutnosti průchodu všech upravovaných souborů. Vazby mezi jednotlivými stránkami jsou zprostředkovány přes cesty (Routes) v souboru '/routes/web.php'.</p>
<h3>Middleware</h3>
<p>Což je lepidlo mezi jednotlivými částmi MVC. Zjednodušuje komunikaci a input-output. Nachází se ve složce 'app/Http/Middleware'. V middlewaru kontrolujeme role uživatelů - Student, Garant a Učitel. Pomocí něho pak určité stránky nemohou zpřístupnit nebo je nevidí. Kromě rolí se v middlewaru implementuje samotná autentizace a automatické odhlašování.</p>
<h2>Instalace</h2>
<p>Softwarové požadavky naleznete v souboru 'composer.json'.</p>
<h3>Postup instalace</h3>
<ol>
<li>Nainstalujte program Composer.</li>
<li>V příkazové řádce vytvořte příkazem 'composer create-project laravel/laravel app' nový projekt frameworku laravel.</li>
<li>Zkopírujte a přepište soubory vytvořeného projektu soubory z archivu obsahujícího náš informační systém. V archivu jsou všechny soubory až na složku vendor, který obsahuje veškeré frameworky a addony a složky node_modules.</li>
</ol>
<p>Připojte se k MYSQL databázi se jménem, heslem a hostem v IDE. Skript SQL iisprojekt.sql vložte do Vámi preferovaného IDE pro databáze a spusťte.</p>
</body>
</html>
