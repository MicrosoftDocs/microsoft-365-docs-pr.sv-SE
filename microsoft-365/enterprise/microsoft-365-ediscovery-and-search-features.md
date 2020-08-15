---
title: Översikt över eDiscovery-och Sök funktioner i Microsoft 365
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
- SPO_Content
f1.keywords:
- NOCSH
description: En översikt över eDiscovery-funktionen och andra Sök funktioner i Microsoft 365 för gransknings användning och transparens.
ms.openlocfilehash: 6a30e1aa687807d61b788bd75fcc63129ff0aa0b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694763"
---
# <a name="microsoft-365-ediscovery-and-search-features-overview"></a>Översikt över eDiscovery-och Sök funktioner i Microsoft 365 

## <a name="ediscovery"></a>eDiscovery

EDiscovery-funktionen gör det enkelt för administratörer, regelefterlevnad och andra behöriga användare att genomföra en omfattande undersökning i Microsoft 365-användare. Säkerhets tjänstemän med lämpliga behörigheter utför sökningar och plats undantag på innehåll. Sök resultaten är samma resultat som du får från en innehålls sökning, utom eDiscovery-ärenden skapas för alla undantag som används. Resultaten från eDiscovery-sökningar krypteras för säkerhet och du kan analysera exporterade data med [Avancerad eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).

## <a name="content-search"></a>Innehålls sökning

[Innehålls sökning](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a) är ett eDiscovery-sökverktyg som ger bättre skalnings-och prestanda kapacitet jämfört med tidigare sökverktyg för eDiscovery. Du använder innehålls sökning för att söka i post lådor, gemensamma mappar, SharePoint Online-webbplatser och OneDrive för företag-platser. Innehålls sökning har stöd för stora sökningar. Det finns inga begränsningar för hur många post lådor och webbplatser du kan söka efter. Det finns inga begränsningar för antalet sökningar som körs samtidigt. När du har kört en sökning visas antalet innehålls källor och ett beräknat antal Sök resultat i informations fönstret på Sök sidan. Du kan förhandsgranska resultaten eller exportera dem till en lokal dator. Om din organisation har ett Microsoft 365 E5-abonnemang kan du [förbereda resultaten](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare) för analys med de kraftfulla analys funktionerna i [Microsoft 365 Avancerad eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).

## <a name="audit-log-search"></a>Gransknings loggs ökning

Förutom spårning av ändringar i Microsoft 365-organisationen kan du Visa gransknings rapporter och exportera gransknings loggar. När granskning har Aktiver ATS för as Microsoft 365-klient organisation registreras användare och administrativa aktiviteter i händelse loggar och är sökbar. Du kan till exempel använda gransknings loggning för post lådor för att spåra åtgärder som utförs på en post låda av andra användare än post lådans ägare. Efterföljandekrav kan använda Sök-och filtrerings funktionerna för specifika användar aktiviteter. Om du till exempel vill identifiera användare som visar eller hämtade ett visst dokument, om administratörer har gjort användar hanterings aktiviteter, eller om du vill visa ändringar i konfigurationen för klient organisationen under de senaste 90 dagarna. Sök Resultat innehåller värdefull Forensic information om specifika aktiviteter som utförs av en användare eller administratör. Se [söka i gransknings loggen](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) efter en beskrivning av de användare och administrativa aktiviteter som loggas i Microsoft 365.

Händelser från SharePoint Online och OneDrive för företag visas i loggen inom 30 minuter. Händelser från Exchange Online visas i gransknings loggar inom 24 timmar. Inloggnings händelser från Azure AD är tillgängliga inom några minuter och andra katalog händelser från Azure AD är tillgängliga inom 24 timmar efter händelsen. Du kan exportera ventilations öppningar i gransknings loggens Sök Resultat för vidare analys. Högst 50 000 poster från enkel gransknings loggs ökning exporteras. Om du vill exportera fler poster med den här gränsen kan du minska datum intervallet eller köra flera gransknings loggar.

Följande tabell visar en del av informationen som visas i aktivitets rapporter. Se de [detaljerade egenskaperna i gransknings loggen](https://docs.microsoft.com/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log) för mer information om egenskaper som samlas in av varje Microsoft 365-arbets belastning.

| Egenskap | Beskrivning |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| Datum | Datum och tid för händelsen |
| Användare | Användare som utförde åtgärden |
| ClientIP | IPv4-eller IPv6-adress för enheten som används när aktiviteten protokollfördes. |
| CreationTime | Datum och tid i UTC (Coordinated Universal Time) när användaren utförde aktiviteten. |
| EventSource | Anger att en händelse inträffade. Möjliga värden är SharePoint och ObjectModel. |
| ET | ID för rapport posten. ID: t identifierar rapport posten unikt. |
| Operativ | Namnet på användaren eller aktiviteten, som motsvarar det värde som valts i visnings resultatet för den här användar aktiviteten. |
| OrganizationId | GUID för organisationens Microsoft 365-tjänst där händelsen inträffade. |
| UserAgent | Information om användarens webbläsare, som tillhandahålls av webbläsaren. |
| Användar | Användare som utförde åtgärden (anges i egenskapen operation) som ledde till att posten loggas. |
| UserType | Typ av användare som utförde åtgärden. Följande värden anger användar typen. |
|  | 0 anger en vanlig användare. |
|  | 2 anger en administratör i din Microsoft 365-organisation. |
|  | 3 anger Microsoft datacenter-administratör eller data Center-systemkonto. |
| Uppgifter | Microsoft 365-tjänst där aktiviteten ägde rum. Möjliga värden för den här egenskapen är: |
|  | Exchange Online |
|  | SharePoint Online |
|  | OneDrive för företag |
|  | Azure Active Directory-rapporter |

Detaljerade anvisningar om hur du söker efter Microsoft 365-gransknings loggar finns i [söka i gransknings loggen i säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="search-unified-audit-log"></a>Sök enhetlig Gransknings logg

Använd funktionen Sök efter sökning för att söka i den enhetliga gransknings loggen. I Microsoft 365 kan du även söka i den här loggen via Remote PowerShell. [Sök-UnifiedAuditLog cmdlet](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps) i Exchange Online PowerShell används för att söka i den enhetliga gransknings loggen för händelser relaterade till användar åtgärder från Exchange Online, SharePoint Online, OneDrive för företag och Azure AD. 

Du kan söka efter alla händelser inom ett visst datum intervall, eller så kan du filtrera resultaten baserat på specifika villkor, till exempel en viss åtgärd, den användare som utförde åtgärden eller målobjektet. Administratörer kan använda upp till tre samtidigt med Exchange Online PowerShell-sessioner för att dela upp stora sökningar i datum intervall.