---
title: AADSpnSignInEventsBeta-tabell i den avancerade sökschemat
description: Läs mer om information som är Azure Active Directory huvudnamn för tjänsten och inloggningshändelser för hanterad identitet i tabellen för avancerad sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f74972bcd5d0ddaab58d82b72a55991fda44e3b1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583550"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Gäller för:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Tabellen är för närvarande i betaversion och erbjuds inom kort för att du ska kunna jaga `AADSpnSignInEventsBeta` Azure Active Directory-tjänstens huvudnamn och hanterade identitetsin signeringshändelser. Så småningom flyttar vi all information i inloggningsschemat till `IdentityLogonEvents` tabellen.



Tabellen `AADSpnSignInEventsBeta` i det avancerade sökschemat innehåller information om hur Azure Active Directory huvudnamn och inloggningar av hanterade identiteter. Du kan läsa mer om de olika typerna av inloggningar Azure Active Directory [i inloggningsaktivitetsrapporter – förhandsversion.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)





| Kolumnnamn     | Datatyp | Beskrivning   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Datum och tid då posten skapades                                                                                                     |
| `Application`          | sträng        | Program som utförde den inspelade åtgärden                                                                                                   |
| `ApplicationId`        | sträng        | Unikt ID för programmet                                                                                                           |
| `IsManagedIdentity`    | boolesk       | Anger om inloggningen initierades med en hanterad identitet                                                                               |
| `ErrorCode`            | int        | Innehåller felkoden om ett inloggningsfel uppstår. Gå till för att hitta en beskrivning av en specifik <https://aka.ms/AADsigninsErrorCodes> felkod. |
| `CorrelationId`        | sträng        | Unikt ID för inloggningshändelsen                                                                                                          |
| `ServicePrincipalName` | sträng        | Namnet på tjänstens huvudnamn som startade inloggningen                                                                                        |
| `ServicePrincipalId`   | sträng        | Unikt ID för tjänstens huvudnamn som initierade inloggningen                                                                           |
| `ResourceDisplayName`  | sträng        | Visningsnamn för den resurs som har åtkomst                                                                                                           |
| `ResourceId`           | sträng        | Unikt ID för den resurs som används                                                                                                      |
| `ResourceTenantId`     | sträng        | Unikt ID för klientorganisationen för den resurs som används                                                                                        |
| `IPAddress`            | sträng        | IP-adress tilldelad till slutpunkten och används under relaterad nätverkskommunikation                                                              |
| `Country`          | sträng        | Kod med två bokstäver som anger landet där klientens IP-adress är geolocerad                                                                |
| `State`                | sträng        | Delstat där inloggningen inträffade, om tillgänglig                                                                                                  |
| `City`                 | sträng        | Ort där kontoanvändaren finns                                                                                                          |
| `Latitude`             | sträng        | Koordinaterna för inloggning i nord till syd                                                                                          |
| `Longitude`            | sträng        | Koordinaterna för inloggningsplatsen öst till väst                                                                                            |
| `RequestId`            | sträng        | Unikt ID för begäran                                                                                                                |
|`ReportId` | sträng | Unikt ID för händelsen | 

 

## <a name="related-articles"></a>Relaterade artiklar

-   [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
-   [Översikt över avancerad jakt](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lär dig frågespråket](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Förstå schemat](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)