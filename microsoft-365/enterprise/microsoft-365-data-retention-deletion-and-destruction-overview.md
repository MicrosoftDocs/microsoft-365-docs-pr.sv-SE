---
title: Data lagring, borttagning och destruktion i Microsoft 365
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
description: En översikt över Microsofts principer för Microsoft 365 rörande data lagring, borttagning och destruktion.
ms.openlocfilehash: c522c1a1a4de46a4fc36bd87a031be8b47c5523d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694508"
---
# <a name="data-retention-deletion-and-destruction-in-microsoft-365"></a>Data lagring, borttagning och destruktion i Microsoft 365

Microsoft har en standard policy för data hantering för Microsoft 365 som anger hur långa kunddata behålls efter borttagningen. Det finns vanligt vis två scenarier då kunddata tas bort:

- **Aktiv borttagning**: innehavaren har en aktiv prenumeration och en användare eller administratör tar bort data eller administratörer tar bort en användare.
- **Passiv borttagning**: klient organisationens abonnemang upphör.

## <a name="data-retention"></a>Data lagring

För vart och ett av dessa borttagnings scenarier visar följande tabell den maximala lagrings tiden för data efter data kategori och klassificering:

| Data kategori | Data klassificering | Beskrivning | Exempel | Kvarhållningsperiod |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| Kunddata | Kund innehåll| Innehåll som tillhandahålls/skapas direkt av administratörer och användare <br><br> Inkluderar all text, ljud, video, bildfiler och program vara som skapas och lagras i Microsoft Data Center när du använder tjänsterna i Microsoft 365 | Exempel på de vanligaste Microsoft 365-programmen som gör att användare kan redigera data är Word, Excel, PowerPoint, Outlook och OneNote <br><br> Kund innehållet inkluderar också kundägda/tillhandahållna hemligheter (lösen ord, certifikat, krypterings nycklar, lagrings nycklar) | **Scenario för aktiva borttagning:** högst 30 dagar <br><br> **Passiv borttagnings scenario:** högst 180 dagar |
| Kunddata | Information om identifierbar slutanvändare (EUII) | Data som identifieras eller kan användas för att identifiera användaren av en Microsoft-tjänst. EUII innehåller inte kund innehåll | Användar namnet eller visnings namnet (domän \ användar namn) <br><br> Användarens huvud namn (name@domain) <br><br>  Användarspecifika IP-adresser | **Scenario med aktiva borttagning:** högst 180 dagar (endast en klient administratörs åtgärd) <br><br> **Passiv borttagnings scenario:** högst 180 dagar |
| Person uppgifter <br> (data som inte ingår i kunddata) | Slutanvändarens Pseudonymous-identifierare (EUPI) | En identifierare som Microsoft är knuten till användaren av en Microsoft-tjänst. När EUPI kombineras med annan information, till exempel en mappnings tabell, identifieras slutanvändaren <br><br> EUPI innehåller inte information som laddas upp eller skapades av kunden | GUID, PUIDs eller sid för användare <br><br> Sessions-ID | **Scenario för aktiva borttagning:** högst 30 dagar <br><br> **Passiv borttagnings scenario:** högst 180 dagar |

## <a name="subscription-retention"></a>Bevarande av abonnemang

Under en aktiv prenumeration kan en abonnent komma åt, extrahera eller ta bort kunddata som lagrats i Microsoft 365. Om en betald prenumeration slutar eller avslutas, bevaras de kunddata som lagras i Microsoft 365 på ett begränsat funktions konto för 90 dagar så att abonnenten kan extrahera data. När tids perioden för 90 är slut kan Microsoft inaktivera kontot och ta bort kunddata. Inte mer än 180 dagar efter att ett abonnemang har gått ut eller avslutas till Microsoft 365, inaktiverar Microsoft kontot och tar bort alla kunddata från kontot. När den maximala Retentions tiden för alla data har förflutit, återges inte informationen kommersiellt.

För en kostnads fri utvärderings period flyttas ditt konto till en respittid i 30 dagar i de flesta länder och regioner. Under denna tidsperiod kan du köpa Microsoft 365. Om du bestämmer dig för att inte köpa Microsoft 365 kan du antingen avbryta utvärderingsversionen eller låta respitperioden gå ut och information och data om ditt utvärderingskonto tas bort.

## <a name="expedited-deletion"></a>Snabbare borttagning

För alla prenumerationer kan en abonnent kontakta Microsoft support och begära att de-etableringen unders snabbare. I den här processen raderas alla användar data tre dagar efter att administratören har angett utelåsnings koden från Microsoft. Detta inkluderar data i SharePoint Online och Exchange Online under kvarhållning eller lagring i inaktiva post lådor.

Mer information om hur du påskyndar inetableringen finns i [avbryta prenumerationen](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription).

## <a name="related-links"></a>Relaterade länkar

- [Data förstörelse](microsoft-365-data-destruction.md)
- [Immutability i Office 365](microsoft-365-data-immutability.md)
- [Exchange Online-Databorttagning](microsoft-365-exchange-online-data-deletion.md)
- [SharePoint Online-Databorttagning](microsoft-365-sharepoint-online-data-deletion.md)
- [Data borttagning i Skype för företag](microsoft-365-skype-data-deletion.md)
