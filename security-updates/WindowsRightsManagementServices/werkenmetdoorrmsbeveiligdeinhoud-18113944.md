---
TOCTitle: Werken met door RMS beveiligde inhoud
Title: Werken met door RMS beveiligde inhoud
ms:assetid: '3cf6d64b-1187-433c-bbb2-c68069bc3c30'
ms:contentKeyID: 18113944
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720251(v=WS.10)'
---

Werken met door RMS beveiligde inhoud
=====================================

Als gebruikers met beveiligde inhoud werken, vinden er twee voor de gebruiker transparante processen plaats. Eerst wordt vanuit de toepassing met RMS-ondersteuning een gebruikslicentie aangevraagd wanneer de gebruiker het document opent. Vervolgens wordt de gebruikslicentie in de toepassing met RMS-ondersteuning beoordeeld om te bepalen of een intrekkingslijst vereist is en wordt gecontroleerd of er certificaten zijn ingetrokken in de vertrouwensketen van de toepassing met RMS-ondersteuning of het rechtenaccountcertificaat. Wanneer beide processen zijn voltooid en de rechten en intrekkingen het toestaan, wordt de door RMS beveiligde inhoud gegenereerd in de toepassing met RMS-ondersteuning.

Als een intrekkingslijst vereist is, wordt lokaal gezocht naar een geldig exemplaar van de intrekkingslijst. Indien nodig wordt er een huidig exemplaar van de intrekkingslijst opgehaald. Vervolgens worden de intrekkingsvoorwaarden toegepast die relevant zijn in de huidige context.

Als de toegang tot de inhoud niet wordt geblokkeerd door intrekkingsvoorwaarden, wordt de inhoud gegenereerd en kan de gebruiker de rechten uitoefenen die aan hem of haar zijn verleend.

U kunt RMS zo configureren dat aanvragen voor gebruikslicenties van gemachtigde externe gebruikers worden verwerkt. In dat geval kan beveiligde inhoud worden gedeeld via internet.

Dit gedeelte bevat de volgende onderwerpen:

-   [Gebruikslicentie verkrijgen](https://technet.microsoft.com/0b6cde34-418a-4dee-9d27-b65b93b535ac)
-   [Gebruikslicenties en externe gebruikers](https://technet.microsoft.com/02db9bda-180e-438f-863d-26252083a471)
