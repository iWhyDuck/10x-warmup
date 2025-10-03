/rick-and-morty characterId: {characterId}, locationId: {locationId}

Instrukcja dla Agenta:
1. Wywołaj publiczne API Rick and Morty:
   - Pobierz dane postaci z endpointu:
     GET https://rickandmortyapi.com/api/character/{characterId}
   - Pobierz dane lokalizacji z endpointu:
     GET https://rickandmortyapi.com/api/location/{locationId}

2. Na podstawie uzyskanych danych (imię, status, gatunek, obrazek postaci oraz nazwa i typ lokalizacji), wygeneruj krótką opowieść w 3 akapitach:
   - Akapit 1: przedstaw postać i opisz jej charakter (na bazie danych z API).
   - Akapit 2: osadź postać w wybranej lokalizacji (jej nazwa i typ).
   - Akapit 3: opisz krótką interakcję lub przygodę bohatera w tej lokalizacji.

3. Styl narracji: kreatywny, fabularny, z lekkim humorem pasującym do klimatu "Rick and Morty".
4. Nie powtarzaj surowych danych API wprost – wpleć je w naturalną narrację.
