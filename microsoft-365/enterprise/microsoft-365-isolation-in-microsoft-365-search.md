---
title: Klient isolering i Microsoft 365 search
ms.author: josephd
author: JoeDavies-MSFT
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
description: I den här artikeln finns en förklaring av hur klient isolering fungerar för separata innehavaradministration i Microsoft 365 search.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9b204e9c1f3ef459852900f3403a21f7ea40541f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694338"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Klient isolering i Microsoft 365 search

I SharePoint Online search används en modell för företags skiljare som balanserar effektiviteten hos delade data strukturer med skydd mot uppgifter som läcker mellan klient organisationer. Med den här modellen kan vi förhindra Sök funktionerna från:

- Returnera frågeresultat som innehåller dokument från andra klient organisationer
- Visar tillräckligt med information i frågeresultatet att en kunnig användare kan härleda information om andra klient organisationer
- Visar schema eller inställningar från en annan klient organisation
- Mixa analys bearbetnings information mellan innehavare eller lagra resultat i fel klient organisation
- Använda ord listor från en annan klient organisation

För varje typ av klient organisations data använder vi en eller flera skydds nivåer i koden för att förhindra oavsiktlig läckage av information. Den viktigaste informationen har de flesta skydds nivåerna för att se till att ett enskilt fel inte leder till att det finns ett faktiskt eller uppskattat informations läckage.

## <a name="tenant-separation-for-the-search-index"></a>Innehavarens separation för Sök indexet

Sök indexet lagras på hård disken i de servrar där index komponenterna finns och klient organisationerna delar indexfiler. En klient organisations indexerade dokument visas bara för frågor för den innehavaren. Tre oberoende mekanismer förhindrar att information läcker:

- Filter för klient organisations-ID
- Villkor för klient organisations-ID
- ACL-kontroller

Alla tre mekanismerna skulle inte fungera för sökning för att returnera dokument till fel klient organisation.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Villkor för klient organisations-ID och term för klient-ID

Sökprefix varje term som är indexerad i full text index med klient-ID. När termen "*foo*" indexeras för en innehavare med ID "*123*", är posten i full text indexet "*123foo".*

Alla frågor konverteras till att omfatta klient-ID med en process som heter klient-ID-filtrering. Frågan "*foo*" konverteras till exempel till "<*GUID*>. *foo* OCH *tenantID*: <*GUID*> ", där <*GUID*> representerar klient organisationens utförande av frågan. Den här frågans konvertering sker inom respektive indexattribut och varken frågor eller innehålls bearbetning kan påverka den. Eftersom klient-ID läggs till i alla frågor kan inte frekvensen i andra klient organisationer uppskjutas genom att du har en lämplig matchnings rangordning i en klient organisation.

Villkor för innehavaradministration endast i full text indexet. Fältade sökningar, till exempel "*title: foo*", går till ett syntetiskt Sök-index där villkoren inte är fasta efter klient-ID. I stället används fält namnet som prefix. Frågan "*title: foo*" konverteras till exempel till "*fält. title: foo och Fields. tenantID*: <*GUID*>." Eftersom frekvensen för en term inte påverkar rangordningen för träffar i det syntetiska Sök indexet behöver du inte använda funktionen för att skilja på innehavare. För en fälts ökning som "*title: foo*", beror på klientens innehålls skillnad av FRÅGANS ID-filtrering.

## <a name="document-access-control-list-checks"></a>Kontroller av dokument åtkomst kontroll listor

Sök kontrollerar åtkomsten till dokument via ACL-listor som sparas i Sök indexet. Varje objekt indexeras med en uppsättning villkor i ett speciellt ACL-fält. Fältet ACL innehåller en term per grupp eller användare som kan visa dokumentet. Alla frågor utökas med en lista över tilläggs villkor för åtkomst kontroll (ACE), en för varje grupp som den autentiserade användaren tillhör.

En fråga som "<*guid*>. *Foo och tenantID*: <*GUID*> "blir:" <*GUID*>. *Foo och tenantID*: <*GUID* >  *och* (*docACL:* < *ace1* >  *eller docACL*: <*ace2* >  *eller docACL*: <*ace3* >  *...*) "

Eftersom användar-och grupp-ID: n är unika är detta en extra säkerhets nivå mellan innehavare för dokument som bara är synliga för vissa användare. Samma sak gäller för de särskilda "alla utom externa användare" som ger till gång till vanliga användare i klient organisationen. Men eftersom åtkomst till "alla" är samma för alla klient organisationer, beror det på klientens separation för de offentliga dokumenten. Neka åtkomst till ess stöds också. Frågan utökas till en sats som tar bort ett dokument från resultatet när det finns en träff med en nekande ACE.

I Exchange Online search partitioneras indexet på post lådans ID för enskilda användares post lådor i stället för klient organisations-ID: t som i SharePoint Online. Partitionerings funktionen är samma som SharePoint Online, men ingen ACL-filtrering.
