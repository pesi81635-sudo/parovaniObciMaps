
# parovaniObciMaps

Webová aplikace pro párování obcí podle dopravní vzdálenosti autem. Určena primárně pro obce Středočeského kraje.

## Co aplikace dělá

Ze zadaného seznamu obcí sestaví páry vždy dvou k sobě nejbližších obcí podle doby jízdy autem. Používá Google Maps Distance Matrix API.

## Jak používat

1. Otevři aplikaci na [pesi81635-sudo.github.io/parovaniObciMaps](https://pesi81635-sudo.github.io/parovaniObciMaps)
2. Zadej svůj Google Maps API klíč
3. Vlož seznam obcí, každou na nový řádek
4. Klikni na **Spárovat obce**
5. Výsledky lze stáhnout jako CSV

## API klíč

Aplikace nevyžaduje žádnou registraci. Každý uživatel používá vlastní Google Maps API klíč, který zadává přímo do stránky. Klíč se nikam neukládá — existuje pouze v paměti prohlížeče po dobu otevření záložky.

Pro získání API klíče: [Google Cloud Console](https://console.cloud.google.com)

Potřebná povolená API:
- Maps JavaScript API
- Distance Matrix API
- Geocoding API

## Technické poznámky

- Čistý HTML/JS, bez závislostí a bez serveru
- Počet API dotazů je optimalizován — počítá pouze horní trojúhelník matice vzdáleností (úspora ~50 % oproti plné matici)
- Párování probíhá greedy algoritmem — vždy vezme nejbližší dosud nepárovanou dvojici
