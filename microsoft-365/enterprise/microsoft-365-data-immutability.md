---
title: Microsoft 365 data immutability
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
description: Lär dig hur Microsoft 365 bevarar data i upptäckbar form för att hantera efterlevnad, interna styr bestämmelser och tvister.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c070eea4498aca89d7cdb8fea233d9b9596491a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694520"
---
# <a name="immutability-in-microsoft-365"></a>Immutability i Microsoft 365

Regler för efterlevnad, interna styr regler och tvister måste organisationerna bevara e-post och associerade data i en identifierbar form. Alla data i systemet måste kunna upptäckas och ingen av dem kan förstöras eller ändras. Den branschbaserade termen för detta är "immutability".

Traditionella metoder för immutability som vanligt vis utförs genom att flytta e-postmeddelanden till en separat, skrivskyddad lagrings plats. Även om sådana system är avsedda att bevara post lådor för identifiering, påverkar de ofta användar gränssnittet genom att ta bort konserverade objekt från det dagliga arbets flödet. För IT-experter kräver den här immutability-lösningen drift sättning och pågående underhåll av en separat server och lagrings infrastruktur. Identifiering utförs med verktyg som inte finns i e-postsystemet och inkluderar tillhör ande distributions-och underhållskostnader.

Genom att arkivera och bevara princip funktioner i Microsoft 365 och dess tjänster kan du bevara och behålla många klasser för inkommande, interna och utgående data. Detta inkluderar:

- Inkommande och utgående e-postkommunikation
- Böcker och poster i e-postformat eller i delade online-dokument
- Mötes förfrågningar
- Fax
- Snabb meddelanden
- Dokument som delas under onlinemöten
- Röst meddelanden

Dessutom har Microsoft utvecklat tilläggs funktioner för att tillåta [arkivering av data](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc) från andra källor genom integrering med data fångst-och hanterings lösningar från tredje part. När du har importerat data från tredje part kan du använda Microsoft 365-efterföljandekrav för data, till exempel:

- [Tvist](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)
- [Lokal eDiscovery och undantag](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)
- [Sökning efter efterlevnad](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)
- [Arkivering på plats](https://docs.microsoft.com/microsoft-365/compliance/enable-archive-mailboxes)
- [Postlådegranskning](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing)
- [Bevarande principer](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

Om till exempel en post låda är placerad i en beställnings medlem sparas data från tredje part. Du kan söka efter data från tredje part med hjälp av en eDiscovery-eller kompatibilitetskontroll. Du kan också använda arkiverings-och bevarande principer för data från tredje part precis som du kan för Microsoft-data. Om du arkiverar data från tredje part i Microsoft 365 blir det lättare för organisationen att hålla sig kompatibel med statliga och rättsliga principer.

Arkivering i Microsoft 365 tillhandahåller regeln för säkerhet och 17a-4-kompatibel lagring. Microsoft 365 bevarar permanent filer av alla data som samlats in i ett icke-omskrivnings bara, icke-raderat, format som använder principer för bevarande och konservering, inklusive konserverings lås.

Verkligen

- Alla poster som lagras med hjälp av bevarande principer ovan behålls i ett dedikerat lagrings område av den vanliga användarens purview. Endast behöriga användare kan komma åt och söka i dessa poster, men de kan inte ändra eller radera dem.
- Metadata för varje objekt innehåller en tidsstämpel som används för att beräkna bevarande varaktighet. Tidsstämplar används när ett nytt objekt tas emot eller skapas och kan inte ändras eller tas bort från metadata.
- Arkivering i Microsoft 365 gör att användare kan kombinera olika bevarande principer och åtgärder för att skapa detaljerade bevarande principer. Dessa principer definierar vilka objekt som ska behållas och hur länge de ska bevaras.
- Med funktionen för konservering av lås kan användare välja om de vill göra principen till en begränsnings princip. En begränsnings princip hindrar alla från att kunna ta bort, inaktivera eller göra ändringar i bevarande principen. Det innebär att när bevara lås är aktive rad kan det inte inaktive ras, och det finns ingen mekanism under vilken data från befintliga Custodians som har samlats in med lagrings principer på plats kan skrivas över, ändras, raderas eller tas bort under den pågående perioden. Dessutom kan spärr perioden som är inställd på bevarande lås inte kortas ner eller minskas. Det kan dock göras om ett juridiskt krav är obligatoriskt för att fortsätta bevara lagrings informationen, enligt ovan. Bevarande lås garanterar att ingen, inte ens administratörer eller de som har viss kontroll åtkomst, ändrar inställningarna eller skriver över eller raderar data som har lagrats, vilket gör att arkivering i Microsoft 365, med den vägledning som anges i 2003 utgivningen av SEC, 17a-4.

Om du vill förstå hur Microsoft 365 hjälper dig att uppfylla villkoren för efterlevnad, särskilt vad gäller regel 17a-4, kan du läsa det [whitepaper](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/2015/11/Microsoft-EOA-White-Paper.pdf) som handlar om Exchange Online-arkivering, SharePoint Online, OneDrive för företag och Skype för företag. I rapporten får du också en djupgående analys av Microsoft 365-sökverktyg och funktioner för de krav under SEC-regeln 17a-4 och som visar reglerade kunder där Microsoft 365-arkiveringen kan göra det möjligt för dem att uppfylla dessa krav.
