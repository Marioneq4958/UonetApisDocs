# uonetplus-uczen

## Obiekty
### OcenyCzastkowePrzedmiot
```js
{
    Przedmiot: String // nazwa przedmiotu
    Pozycja: Number // pozycja przedmiotu w liście przedmiotów
    OcenyCzastkowe: [OcenaCzastkowa] // lista ocen czastkowych z przedmiotu
    ProponowanaOcenaRoczna: String // proponowana ocena roczna/semestralna z przedmiotu
    OcenaRoczna: String // ocena roczna/semestralna z przedmiotu
    ProponowanaOcenaRocznaPunkty: String | Null // proponowana ocena roczna/semestralna punkty z przedmiotu
    OcenaRocznaPunkty: String | Null // ocena roczna/semestralna punkty z przedmiotu
    Srednia: Number // średnia ocen cząstkowych z przedmiotu (gdy szkoła wyłączy liczenie średniej wartością zawsze będzie 0)
    SumaPunktow: String | Null // suma punktów z przedmiotu
    WidocznyPrzedmiot: Boolean // widoczność przedmiotu
}
```

### OcenaCzastkowa
```js
{
    Nauczyciel: String // Nauczyciel, który wpisał ocenę
    Wpis: String // Ocena
    Waga: Number // Waga oceny
    NazwaKolumny: String // Nazwa kolumny oceny
    KodKolumny: String // Kod kolumny oceny
    DataOceny: String // Data wpisania oceny ("DD.MM.YYYY")
    KolorOceny: Number // Kolor oceny
}
```

### OcenaOpisowa
```js
{
    NazwaPrzedmiotu: String // Przedmiot
    Opis: String // Opis oceny
    IsReligiaEtyka: Boolean // Czy przedmiot to religia lub etyka
}
```

### UczenDziennik
```js
{
    Id: Number // Pozycja ucznia w liście
    IdUczen: Number // ID ucznia
    UczenImie: String // Imię ucznia
    UczenImie2: String | Null // Drugie imię ucznia
    IdDziennik: Number // ID dziennika
    IdPrzedszkoleDziennik: Number // ID dziennika przedszkole
    IdWychowankowieDziennik: Number // ID dziennika wychowankowie
    Poziom: Number // Poziom oddziału
    Symbol: String // Symbol oddziału
    Nazwa: String | Null // Pseudonim ucznia
    DziennikRokSzkolny: Number // ID roku szkolnego dziennika
    Okresy: [Okres] // Lista okresów dla dziennika
    DziennikDataOd: String // Data od której dziennik jest aktualny
    DziennikDataDo: String // Data do której dziennik jest aktualny
    IdJednostkaSkładowa: Number // ID jednostki składowej
    IdSioTyp: Number
    IsDorosli: Boolean
    IsPolicealna: Boolean
    Is13: Boolean
    IsArtystyczna: Boolean
    IsArtystyczna13: Boolean
    IsSpecjalny: Boolean
    IsPrzedszkola: Boolean
    IsWychowankowie: Boolean
    IsArchiwalny: Boolean
    IsOplaty: Boolean
    IsPlatnosci: Boolean
    IsPayButtonOn: Boolean
    CanMergeAccounts: Boolean // Czy użytkownik może przyłączyć ucznia do innego konta lub odwrotnie
    UczenPelnaNazwa: String // Imię i nazwisko ucznia oraz symbol i poziom oddziału
                            // ("{PoziomOddziału}{SymbolOdzizału} - {ImięUcznia} {NazwiskoUcznia}")
    O365PassType: Number
    IsAdult: Boolean // Czy uczeń jest pełnoletni
    IsStudentParent: Boolean // Czy użytkownik to rodzic ucznia
    IsAuthorized: Boolean // Czy użytkownik został zautoryzowany (gdy opiekun po raz pierwszy będzie chciał uzyskać
                          // informacje o uczniu na początku będzie musiał przejść autoryzację, polegającą na wpisaniu
                          // PESEL'u lub daty urodzenia ucznia)
    Obywatelstwo: Number
}
```

### UczenDziennikOkres
```js
{
    NumerOkresu: Number // Numer okresu w roku szkolnym
    Poziom: Number // Poziom oddziału w okresie
    DataOd: String // Data od której trwa okres ("YYYY:mm:DD HH:MM:SS")
    DataDo: String // Data do której trwa okres ("YYYY:mm:DD HH:MM:SS")
    IdOddzial: Number // ID oddziału do którego uczęszcza uczeń
    IdJednostkaSprawozdawcza: Number // ID jednostki sprawozdawczej
    IsLastOkres: Boolean // Czy okres jest ostatnim okresem w danym roku szkolnym
    Id: Number // ID okresu
}
```

### Uczen
```js
{
    Imie: String // Imię ucznia
    Imie2: String // Drugie imię ucznia
    NumerDokumentu: ? | Null
    Nazwisko: String // Nazwisko ucznia
    DataUrodzenia: String // Data urodzenia ucznia ("YYYY:mm:DD HH:MM:SS")
    MiejsceUrodzenia: String // Miejsce urodzenia ucznia
    NazwiskoRodowe: String // Nazwisko rodowe ucznia
    ObywatelstwoPolskie: Number
    ImieMatki: String // Imię matki ucznia
    ImieOjca: String // Imię ojca ucznia
    Plec: Boolean // Płeć ucznia true=mężczyzna false=kobieta
    AdresZamieszkania: String // Adres zamieszkania ucznia
    AdresZameldowania: String // Adres zameldowania ucznia
    AdresKorespondencji: String // Adres korespondencji
    TelDomowy: String | Null // Telefon domowy ucznia
    TelKomorkowy: String | Null // Telefon komórkowy ucznia
    Email: String // Adres e-mail ucznia
    CzyWidocznyPesel: Boolean
    Opiekun1: Opiekun
    Opiekun2: Opiekun
    UkryteDaneAdresowe: Boolean // Czy dane adresowe są ukryte
    ImieNazwisko: String // Imię, drugie imię i nazwisko ucznia
    PosiadaPesel: Boolean // Czy uczeń posiada PESEl
    Polak: Boolean // Czy uczeń jest Polakiem
    ImieMatkiIOjca: String // Imię matki i ojca ucznia
    ShowPhoto: String // Czy pokazywać zdjęcie ucznia
}
```

### UczenOpiekun
```js
{
    Id: Number // ID opiekuna
    Imie: String // Imię opiekuna
    Nazwisko: String // Nazwisko opiekuna
    StPokrewiensta: String // Stopień pokrewieństwa opiekuna z uczniem
    Adres: String // Adres opiekuna
    TelDomowy: String | Null // Telefon domowy opiekuna
    TelKomorkowy: String | Null // Telefon domowy opiekuna
    TelSluzbowy: String | Null // Telefon służbowy opiekuna
    Email: String // Adres e-mail opiekuna
    FullName: String // Imię i nazwisko opiekuna
    Telefon: String // Telefon komórkowy ("Telefon: ${TelefonKomorkowyRodzica}")
}
```

### UczenCache
```js
{
    poryLekcji: [PoraLekcji]
    pokazLekcjeZrealizowane: Boolean // Czy szkoła włączyła pokazywanie lekcji zrealizowanych
    pokazLekcjeZaplanowane: Boolean // Czy szkoła włączyła pokazywanie lekcji zaplanowanych
    serverDate: String // Czas serwera ("YYYY-MM-DD HH-mm-SS")
    infoCookieUrl: String
    privacyPolicyUrl: String
    infoEnclosureUrl: String
    accessDeclarationUrl: String
    isParentUser: Boolean // Czy użytkownik jest rodzicem
    isPupilUser: Boolean // Czy użytkownik jest uczniem
    isMenuOn: Boolean // Czy szkoła włączyła pokazywanie jadłospisu
    isDostepOffice: Boolean
    isO365LoginOff: Boolean
    isO365PassOff: Boolean
    isHomeworksOneDriveAttachmentsOn: Boolean // Czy w zadaniach domowych wymagających odpowiedź uczeń może w odpowiedzi
                                              // umieścić załącznik z OneDrive
    isHomeworksGoogleDriveAttachmentsOn: Boolean // Czy w zadaniach domowych wymagających odpowiedź uczeń może w
                                                 // odpowiedzi umieścić załącznik z Google Drive
    oneDriveClientId: String
    googleDriveClientId: String
    googleDriveApiKey: String
    modulNawigacja: {
        ModulyLinki: {
            "{SymbolJednostkiSprawozdawczej}": {
                Nazwa: String
                Link: String // Link do modułu z symbolem jednostki grupującej i symbolem jednostki sprawozdawczej
                Modul: Number
            } // Linki do pozostałych modułów, do których użytkownik ma dostęp, bez modułu wiadomości plus
        }
    }
    isPayButtonOn: Boolean
    isZglaszanieNieobecnosciOn: Boolean
    zglaszanieNieobecnosciConfig: [ZglaszanieNieobecnosciConfig]
    isBetacomOn: Boolean
    isPodrecznikiOn: Boolean // Czy szkoła włączyła udostępnianie listy podręczników dla uczniów
}
```

### PoraLekcji
```js
{
    Nazwa: String // Nazwa pory lekcji, najczęściej numer lekcji
    Numer: Number // Numer pory lekcji
    Poczatek: String // Pora początku lekcji ("1900-01-01 HH:MM:SS")
    Koniec: String // Pora początku lekcji ("1900-01-01 HH:MM:SS")
    DataModyfikacji: String // Data modyfikacji pory lekcji ("YYYY:mm:DD HH:MM:SS")
    IsJednostkaSprawozdawcza: Number // ID jednostki sprawozdawczej
}
```

### ZglaszanieNieobecnosciConfig
```js
{
    idJednostkaSkladowa: Number // ID jednostki składowej
    mozeRodzicZglaszac: Boolean
    dinPrzed: Number
    doGodziny: String // ("HH:MM:SS")
}
```

## Endpoint'y
- `{SymbolGrupujacy}/{SymbolJednostkiSprawozdawczej}/UczenDziennik.mvc/Get`
    #### Request:
    ```js
    POST `{SymbolGrupujacy}/{SymbolJednostkiSprawozdawczej}/UczenDziennik.mvc/Get`
    Accept: */*
    Accept-Encoding: gzip
    Connection: Keep-Alive
    Content-Type: application/json; charset=utf-8
    User-Agent: okhttp/3.11.0
    Cookies: {
        // Tu należy wstawić cookies'y sesji
    }
    ```

    #### Response
    ```js
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
        data: {
            [UczenDziennik]
        }
        success: Boolean
    }
    ```
- `{SymbolGrupujacy}/{SymbolJednostkiSprawozdawczej}/UczenCache.mvc/Get`
    #### Request
    ```js
    POST `{SymbolGrupujacy}/{SymbolJednostkiSprawozdawczej}/UczenCache.mvc/Get`
    Accept: */*
    Accept-Encoding: gzip
    Connection: Keep-Alive
    Content-Type: application/json; charset=utf-8
    User-Agent: okhttp/3.11.0
    Cookies: {
        biezacyRokSzkolny: Number // ID roku szkolnego
        idBiezacyUczen: Number // ID ucznia
        idBiezacyDziennik: Number // ID dziennika
        idBiezacyDziennikPrzedszkole: Number // ID dziennika przedszkolne
        idBiezacyDziennikWychowankowie: Number // ID dziennika wychowankowie
        // Należy dodać do tego cookies'y sesji
    }
    ```
  
    #### Response
    ```js
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
        data: UczenCache
        success: Boolean
    }
    ```
  
- `{SymbolGrupujacy}/{SymbolJednostkiSprawozdawczej}/Oceny.mvc/Get`
    #### Request
    ```js
    POST `{SymbolGrupujacy}/{SymbolJednostkiSprawozdawczej}/Oceny.mvc/Get`
    Accept: */*
    Accept-Encoding: gzip
    Connection: Keep-Alive
    Content-Type: application/json; charset=utf-8
    User-Agent: okhttp/3.11.0
    Cookies: {
        biezacyRokSzkolny: Number // ID roku szkolnego
        idBiezacyUczen: Number // ID ucznia
        idBiezacyDziennik: Number // ID dziennika
        idBiezacyDziennikPrzedszkole: Number // ID dziennika przedszkolne
        idBiezacyDziennikWychowankowie: Number // ID dziennika wychowankowie
        // Należy dodać do tego cookies'y sesji
    }
  
    {
        okres: Number // ID okresu
    }
    ```
  
    #### Response
    ```js
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
        data: {
            isSrednia: Boolean
            isPunkty: Boolean
            Oceny: [OcenyCzastkowePrzedmiot] // Lista przedmiotów z ocenami czastkowymi
            OcenyOpisowe: [OcenaOpisowa] // Lista ocen opisowych
            TypOcen: Number
            IsOstatniSemestr: Boolean // Czy okres z którego są pobierane oceny jest ostatnim w danym roku szkolnym
            IsDlaDoroslych: Boolean
        }
        success: Boolean
    }
    ```

