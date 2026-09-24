<!-- Header and footer are added in layout.svelte -->
<div class="container">
    <h1>Impressum</h1>
    <div class="spacer"></div>

    <h2>Kontaktadresse</h2>
    <p>
        Brainflick<br>
        Erika-Mann-Strasse 11<br>
        8050 Zürich<br>
        Schweiz<br>
        support@brainflick.ch
    </p>

    <div class="spacer"></div>
    <h2>Vertretungsberechtigte Personen</h2>
    <p>
        Robin Welmers, Co-Founder, Tech Lead<br>
        Manuel Ineichen, Co-Founder, Art Lead
    </p>

    <div class="spacer"></div>
    <h2>Haftungsausschluss</h2>
    <p>Der Autor übernimmt keinerlei Gewähr hinsichtlich der inhaltlichen Richtigkeit,
        Genauigkeit, Aktualität, Zuverlässigkeit und Vollständigkeit der Informationen.
        Haftungsansprüche gegen den Autor wegen Schäden materieller oder immaterieller Art,
        welche aus dem Zugriff oder der Nutzung bzw. Nichtnutzung der veröffentlichten Informationen,
        durch Missbrauch der Verbindung oder durch technische Störungen entstanden sind, werden ausgeschlossen.
        Alle Angebote sind unverbindlich. Der Autor behält es sich ausdrücklich vor,
        Teile der Seiten oder das gesamte Angebot ohne gesonderte Ankündigung zu verändern,
        zu ergänzen, zu löschen oder die Veröffentlichung zeitweise oder endgültig einzustellen.
    </p>
    
    <div class="spacer"></div>
    <h2>Haftung für Links</h2>
    <p>
        Verweise und Links auf Webseiten Dritter liegen ausserhalb unseres Verantwortungsbereichs. 
        Es wird jegliche Verantwortung für solche Webseiten abgelehnt. 
        Der Zugriff und die Nutzung solcher Webseiten erfolgen auf eigene Gefahr des Nutzers oder der Nutzerin.
    </p>
    
    <div class="spacer"></div>
    <h2>Urheberrechte</h2>
    <p>
        Die Urheber- und alle anderen Rechte an Inhalten, Bildern, Fotos oder anderen Dateien 
        auf der Website gehören ausschliesslich der Firma Brainflick oder den speziell genannten Rechtsinhabern. 
        Für die Reproduktion jeglicher Elemente ist die schriftliche Zustimmung der Urheberrechtsträger 
        im Voraus einzuholen.
    </p>
</div>

<style lang="scss">
    .container {
        display: flex;
        align-items: flex-start;
        flex-direction: column;
        text-align: left;
    }

    .spacer {
        height: 2em;
    }

    h2 {
        margin-bottom: 1em;
    }
</style>