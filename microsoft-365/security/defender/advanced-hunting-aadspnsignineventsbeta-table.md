---
title: AADSpnSignInEventsBeta-tabell i den avancerade sökschemat
description: Läs mer om informationen som är kopplad till tabellen för azure Active Directory-tjänstens huvudnamn och inloggning av hanterade identiteter i det avancerade sökschemat
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
ms.openlocfilehash: 984e945107b6e0b41459659a7f2e9f649981e4b5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932601"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Gäller för:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Tabellen är för närvarande i betaversion och erbjuds inom kort för att du ska kunna leta igenom AAD-tjänstens huvudnamn och inloggningshändelser för hanterade identiteter i `AADSpnSignInEventsBeta` Azure Active Directory. Så småningom flyttar vi all information i inloggningsschemat till `IdentityLogonEvents` tabellen.<br><br>
> Kunder som har åtkomst till Microsoft 365 Defender via Azure Defenders integrerade Microsoft Defender för slutpunktslösning, men inte har licenser för Microsoft Defender för Office, Microsoft Defender för identitet eller Microsoft Cloud App Security, kommer inte att kunna se det här schemat. 



Tabellen `AADSpnSignInEventsBeta` i det avancerade schemat för sökning innehåller information om Azure Active Directory-tjänstens huvudnamn och inloggning av hanterade identiteter. Du kan läsa mer om de olika typerna av inloggningar i [Azure Active Directory-inloggningsaktivitetsrapporter – förhandsversion.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

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