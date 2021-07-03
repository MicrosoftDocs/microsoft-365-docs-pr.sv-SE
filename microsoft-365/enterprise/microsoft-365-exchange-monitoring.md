---
title: Exchange Online-övervakning för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Använd Exchange Online-övervakning för information om e-postincidenter eller rekommendationer i Microsoft 365.
ms.openlocfilehash: 3d88378449879d451b21ba8bf2a7b5c3032a2c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286447"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a>Exchange Online-övervakning för Microsoft 365

Du kan använda Exchange Online-övervakning i Administrationscentret för Microsoft 365 till att övervaka hälsan för Exchange-tjänsten för din organisations Microsoft 365-prenumeration. I Exchange Online-övervakningen finns information om incidenter och rekommendationer som samlas in i följande kategorier:

- **Infrastruktur**: Ett problem identifieras i Microsoft 365-infrastrukturen som Microsoft äger för att ge regelbundna uppdateringar och lösa problemet. Till exempel kan användarna inte få åtkomst till Exchange Online på grund av problem med Exchange eller annan molninfrastruktur för Microsoft 365.
- **Tredje parts infrastruktur**: Ett problem identifieras i tredje parts infrastruktur som din organisation är beroende av och det krävs åtgärder från din organisation för att lösa problemet. Till exempel kan användarautentiserings transaktioner begränsas av en tredjepartsleverantör av säkerhetstokentjänster (STS), vilket hindrar användare från att ansluta till Exchange Online.
- **Kundinfrastruktur**: Ett problem identifieras i din organisations infrastruktur och det krävs åtgärder från din organisation för att lösa problemet. Till exempel kan användare inte få åtkomst till Exchange Online eftersom de inte kan få en autentiseringstoken från STS-leverantören som finns i din organisation, på grund av ett utgånget certifikat.

Här är ett exempel på sidan **Tjänststatus** i Administrationscentret för Microsoft 365, tillgänglig från **Hälsa > Tjänststatus**.

![Sidan Tjänststatus i administrationscentret för Microsoft 365](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

Värdet i kolumnen **Status** anger om tjänsten är felfri eller om det finns rekommendationer eller incidenter baserat på de molntjänster som Microsoft underhåller. 

Värdet i kolumnen **Organisations- och tredjepartsproblem** anger att organisationens infrastruktur eller programvara från tredje part påverkar tjänststatusens användning i Exchange Online. Vid rekommendationer och incidenter krävs åtgärder *från dig* för att lösa problemet.

Här är ett exempel på sidan för **Exchange Online**-övervakning i Administrationscentret för Microsoft 365, tillgängligt från **Hälsa > Tjänststatus > Exchange Online**.

![Sidan för Exchange Online-övervakning i Administrationscentret för Microsoft 365](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

Med sidan för **Exchange Online**-övervakning kan du se om Exchange Online-tjänsten är felfri eller inte, och om det finns några associerade incidenter eller rekommendationer. Med Exchange Online-övervakning kan du titta på tjänststatusen för specifika e-postscenarier och se signaler nästan i realtid för att avgöra effekten efter scenario. 

## <a name="requirements"></a>Krav

Den här förhandsversionen är aktiverad för kunder som uppfyller följande krav: 

- Din organisation måste ha ett licensantal på minst 5 000, med en eller en kombination av dessa produkter: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. 

  Din organisation kan till exempel ha 3 000 Office 365 E3-licenser och 2 500 Microsoft 365 E5 som totalt blir 5 500 licenser av de kvalificerande produkterna.

- Din organisation måste ha minst 50 månatliga aktiva Exchange Online-användare.

Med Exchange Online-övervakning kan du visa hälsan för följande e-postklienter baserat på läsaktiviteten för e-post:

- Outlook (skrivbordsversion)
- Outlook på webben
- Inbyggda e-postklienter för iOS och Android 
- Outlook Mobile-app på iOS och Android 
- Outlook Mac-klient

För dessa klienter kan du se antalet aktiva användare under de senaste 30 minuterna baserat på användare som läser ett e-postmeddelande, samt antalet incidenter och rekommendationer på instrumentpanelen. Dessa data jämförs med samma intervall för föregående vecka för att se om det finns ett problem. 

>[!Note]
> Antalet aktiva användare mäts med en enskild aktivitet, till exempel när en användare läser ett e-postmeddelande. Den redovisar bara de senaste 30 minuternas aktivitet.
>

Du kan också övervaka Exchange Online-hälsan för följande scenarier:

- **E-postflöde**: Antalet meddelanden som skickas till en postlåda utan fördröjning när meddelandet kommit till Microsoft 365-nätverket. 
- **Grundläggande autentisering och modern autentisering**: Antalet användare som har verifierats i Exchange Online-tjänsten.

![Ett exempel på övervakning av Exchange-hälsan för e-postleverans](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

För alla de här scenarierna gäller nyckeltalen för de senaste 30 minuterna på huvudinstrumentpanelen. Detaljerade vyer för vart och ett av dessa scenarier visar trenden nästan i realtid för sju dagar med 30 minuters aggregerade jämfört med föregående vecka. 

## <a name="send-us-feedback"></a>Skicka feedback

Du kan lämna feedback på två sätt:

- Använd alternativet **Ge feedback** som finns på varje sida i administrationscentret för Microsoft 365.
- Skicka feedback med länken **Är det här inlägget användbart?** för en särskild incident eller rekommendation.

![Länken ”Är det här inlägget användbart?” för en särskild incident eller rekommendation](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a>1. Varför ser jag inte ”Exchange Online-övervakning” under Hälsa i Administrationscentret för Microsoft 365? 

Kontrollera först att du har aktiverat det nya Administrationscentret på **Startsidan** i Administrationscentret för Microsoft 365. 

Kontrollera sedan att du uppfyller båda följande krav: 

- Din organisation måste ha ett licensantal på minst 5 000, med en eller en kombination av dessa produkter: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. 
- Din organisation måste ha minst 50 månatliga aktiva Exchange Online-användare.

Om licensantalet för din organisation understiger 5 000 användare och antalet månatliga aktiva användare hamnar under 50 användare aktiveras inte Exchange Online-övervakning förrän dessa kraven uppfyllts.

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a>2. Antalet aktiva användare på instrumentpanelen för varje klient verkar vara lågt. Vi har många aktiva licenser tilldelade till användare. Vad betyder det här? 

Antalet aktiva användare som visas i övervakningen baseras på en 30-minutersperiod där användare har utfört aktiviteten som anges i funktionen. Det här ska inte förväxlas med användningstal. Använd aktivitetsrapporter i Administrationscentret för Microsoft 365 (**Rapporter > Användning**) för att visa användningstal.

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a>3. Kommer det att finnas andra övervakningsscenarier för andra tjänster, till exempel Teams och SharePoint? 

Microsoft har integrerat den här funktionen direkt i instrumentpanelen för tjänststatus i Administrationscentret för Microsoft 365. Detta ger Microsoft möjlighet att utöka övervakningsscenarier för andra tjänster, som kommer att meddelas när det finns nyheter att dela. 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a>4. Vad är planen för att få allmän tillgänglighet för den här funktionen? 

Microsoft har integrerat Exchange Online-övervakning direkt på **Tjänststatus**-instrumentpanelen i administrationscentret för Microsoft 365. 

Med den här nya integrerade funktionen är Microsofts plan att samla in din feedback och sedan definiera vår plan för allmän tillgänglighet.

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a>5. Är det här en kostnadsfri (inkluderad) eller betald (extra) funktion? 

Den här funktionen är en allmänt tillgänglig förhandsversion och är bara tillgänglig för kunder som uppfyller kraven i fråga 1.

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a>6. Hur ger jag feedback? 

Om du vill lämna allmän feedback kan du använda ikonen **Ge feedback** längst ned till höger på sidan för **Exchange Online**-övervakning. 

För att lämna feedback om incidenter eller rekommendationer använder du länken **Är det här inlägget användbart?**.

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a>7. Var är data instrumenterad för de scenarier som visar aktivitetstrender?

Data är instrumenterade i Exchange Online-tjänsten. Om det finns ett fel som uppstår innan begäran når Exchange Online eller om det finns ett fel i Exchange Online ser du en nedgång i aktivitetssignalen.
