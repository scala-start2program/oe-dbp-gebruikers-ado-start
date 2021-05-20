# Oefening Gebruikers met ADO.Net  

  ![demo](assets/demo.gif)

De bedoeling is om een applicatie te maken rond gebruikersbeheer en aan de gebruikers toegangsrechten te verlenen.  

Voer eerst en vooral het script scalagebruikers.sql uit op je SQL server zodat je over de database met wat testgegevens beschikt.  
Het script zelf kan je terugvinden op het leerplatform.  

Het programma moet gebruikers kunnen afbeelden, toevoegen, wijzigen en/of verwijderen en je moet toegang kunnen verlenen tot bepaalde onderdelen.  

In de starterscode is al heel wat aanwezig : 
  * Voor elke tabel in de database is al een entiteitsklasse gemaakt : je moet uiteraard wel nog invulling geven.  
    Denk er vooral aan dat wanneer je een nieuw object aanmaakt in je app er automatisch een GUID wordt toegekend aan de Id eigenschappen.  
  * De service klassen DBService en Helper zijn reeds aanwezig (alsook de nodige bibliotheken en referenties) , dus daar hoef je niets meer voor te doen.  
  * Er is ook een service klasse GebruikersService aanwezig maar die je nog volledig in te vullen.  Deze service klasse vormt de brug tussen de code behind van je WPF venster en het database gebeuren (dus je klasse DBService).  
    Deze GebruikersService klasse dient over volgende methoden te beschikken : 
    * public List<Gebruiker> GetAlleGebruikers()  
      deze methode haalt alle gebruikers, gesorteerd op naam en voornaam uit de tabel en levert de inhoud af als een list van gebruiker objecten.  
    * public List<Gebruiker> GetGebruikersMetToegangTotOnderdeel(Onderdeel onderdeel)    
      deze methode haalt alle gebruikers, gesorteerd op naam en voornaam uit de tabel die toegang hebben tot een opgegeven onderdeel en levert de inhoud af als een list van gebruiker objecten.
    * public List<Gebruiker> GetGebruikersZonderToegangTotOnderdeel(Onderdeel onderdeel)  
      deze methode haalt alle gebruikers, gesorteerd op naam en voornaam uit de tabel die GEEN toegang hebben tot een opgegeven onderdeel en levert de inhoud af als een list van gebruiker objecten.    
    * public bool IsGebruikersnaamUniek(string gebruikersnaam)  
      Deze methode zoekt in de tabel gebruikers of de opgegeven gebruikersnaam al of niet bestaat en geeft TRUE terug wannneer die gevonden wordt, anders FALSE  
    * public List<Onderdeel> GetOnderdelen()
      Deze methode haalt alle onderdelen, gesorteerd op onderdeelnaam op uit de tabel en levert de inhoud af als een list van onderdeel objecten.  
    * 

