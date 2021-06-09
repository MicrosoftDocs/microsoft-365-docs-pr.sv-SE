---
title: Innehavarisolering i Microsoft 365 sökning
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Den här artikeln innehåller en förklaring av hur innehavarisolering fungerar för att separera data i Microsoft 365 Sökning.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332406"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Innehavarisolering i Microsoft 365 sökning

SharePoint Onlinesökning använder en modell för klientindelning som balanserar effektiviteten i delade datastrukturer med skydd mot information som läcker mellan klientorganisationen. Med den här modellen hindrar vi sökfunktionerna från att:

- Returnera frågeresultat som innehåller dokument från andra klientorganisationen
- Genom att lägga till tillräcklig information i frågeresultat som en erfaren användare kan utge information om andra klientorganisationar
- Visar schema eller inställningar från en annan klientorganisation
- Blanda analysbearbetningsinformation mellan klientorganisationen eller lagra resultat i fel klientorganisation
- Använda ordlisteposter från en annan klientorganisation

För varje typ av klientorganisationsdata använder vi ett eller flera lager av skydd i koden för att förhindra att information oavsiktligt läcker ut. De mest kritiska data har de flesta lager av skydd för att säkerställa att en enskild defekt inte leder till det faktiska eller uppfattas informationsläckor.

## <a name="tenant-separation-for-the-search-index"></a>Klientorganisationsavskiljning för sökindexet

Sökindexet lagras på disken i servrarna som är värd för indexkomponenterna och klientorganisationen delar indexfilerna. En klientorganisations indexerade dokument visas endast för frågor för den klientorganisationen. Tre oberoende mekanismer förhindrar det informationsläckor:

- Filtrering av klientorganisations-ID
- Termprefix för klientorganisations-ID
- ACL-kontroller

Alla tre mekanismerna måste misslyckas för att Sökningen ska returnera dokument till fel klientorganisation.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Filtrering av klientorganisations-ID och termprefix för klientorganisations-ID

Sökprefix för varje term som indexeras i fulltextindexet med klientorganisations-ID: t. Om termen "*foo*" till exempel indexeras för en klientorganisation med ID:t "*123*" är posten i fulltextindex "*123foo.*"

Alla frågor konverteras till att inkludera klientorganisations-ID genom att använda en process som kallas filtrering av klientorganisations-ID. Frågan " foo "*konverteras* till exempel till "<*guid*>. *foo* AND *tenantID*:<*guid*>", där <*guid*> representerar den klientorganisation som utför frågan. Den här frågekonverteringen sker inom varje indexnod och varken frågan eller innehållsbearbetningen kan påverka den. Eftersom klientorganisations-ID läggs till i varje fråga kan frekvensen för en term i andra klientorganisationen inte härledas genom att titta på bästa rangordning i en klientorganisation.

Termprefix för klientorganisations-ID förekommer endast i hela textindexet. Infältade sökningar, till exempel "*titel:foo*", går till ett sökindex för klientorganisation där termer inte föregås av klientorganisations-ID. I stället föregås de infältade sökningarna av fältnamnet. Frågan "*title:foo*" konverteras till exempel till "*fields.title:foo AND fields.tenantID*:<*guid*>". Eftersom frekvensen för en term inte påverkar rangordningen av träffar i det funktionella sökindexet, behöver du inte separera klientorganisationen genom att använda prefix. För en fältad sökning som "*titel:foo*"beror en innehållsavskiljning på klientorganisations-ID:ns filtrering genom frågekonvertering.

## <a name="document-access-control-list-checks"></a>Kontrolllistor för dokumentåtkomst

Sökningen styr åtkomsten till dokument via åtkomstkontrollistor som sparas i sökindexet. Varje objekt indexeras med en uppsättning termer i ett särskilt ACL-fält. ACL-fältet innehåller en term per grupp eller användare som kan visa dokumentet. Varje fråga utökas med en lista över termer för åtkomstkontroll (ACE), en för varje grupp som den autentiserade användaren tillhör.

Till exempel en fråga som "<*guid*>. *foo AND tenantID*:<*guid*>" blir: "<*guid*>. *foo AND tenantID*:<*guid* >  *AND* (*docACL:* < *ace1* >  *OR docACL*:<*ace2* >  *OR docACL*:<*ace3* >  *...*)"

Eftersom identifierare för användare och grupper är unika, ger detta en extra säkerhetsnivå mellan klientorganisationen för dokument som bara är synliga för vissa användare. Samma sak gäller för det särskilda ACE-kortet "Alla utom externa användare" som ger åtkomst till vanliga användare i klientorganisationen. Men eftersom klientorganisationsavskiljning för "Alla" är samma för alla innehavare beror avgränsningen av klientorganisation för offentliga dokument på filtrering av klientorganisations-ID. Deny ACEs stöds också. Vid utrop av fråga läggs en sats till som tar bort ett dokument från resultatet när det finns en matchning med ett nekat ACE.

I Exchange Online är indexet partitionerat för postlåde-ID för enskilda användares postlådor i stället för klientorganisations-ID (prenumerations-ID) som i SharePoint Online. Partitioneringsmekanismen är densamma som för SharePoint Online, men det finns ingen ACL-filtrering.
