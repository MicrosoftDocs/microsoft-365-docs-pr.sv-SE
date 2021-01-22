---
title: Tabellen AADSpnSignInEventsBeta i det avancerade sökschemat
description: Läs mer om information som är kopplad till Azure Active Directory-tjänstens huvudnamn och inloggningstabell för hanterade identiteter i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning på cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AviseringInfo, avisering, enheter, bevis, fil, IP-adress, enhet, dator, användare, konto, identitet, AAD
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 172c400df3adea70a2e2d2e37547fa39e0d3b9cf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928624"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Gäller för:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Tabellen är för närvarande i betaversion och erbjuds på kort sikt så att du kan jaga via `AADSpnSignInEventsBeta` AAD-tjänstens huvudnamn (Azure Active Directory) och hanterade identitetsin signeringshändelser. Så småningom flyttar vi all information i inloggningsschemat till `IdentityLogonEvents` tabellen.<br><br>
> Kunder som kan komma åt Microsoft 365 Defender via Azure Säkerhetscenters integrerade Microsoft Defender för slutpunktslösning, men inte har licenser för Microsoft Defender för Office, Microsoft Defender för identitet eller Microsoft Cloud App Security, kommer inte att kunna se det här schemat. 



Tabellen `AADSpnSignInEventsBeta` i det avancerade utbildningsschemat innehåller information om Azure Active Directory-tjänstens huvudnamn och inloggningar för hanterade identiteter. Du kan läsa mer om de olika typerna av inloggningar i [azure Active Directory-inloggningsrapporter](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)– förhandsversion.

Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)





| Kolumnnamn     | Datatyp | Beskrivning   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Datum och tid då posten skapades                                                                                                     |
| `Application`          | sträng        | Program som utförde den inspelade åtgärden                                                                                                   |
| `ApplicationId`        | sträng        | Unikt ID för programmet                                                                                                           |
| `IsManagedIdentity`    | boolesk       | Anger om inloggningen initierades med en hanterad identitet                                                                               |
| `ErrorCode`            | int        | Innehåller felkoden om det uppstår ett inloggningsfel. Gå till en beskrivning av en specifik <https://aka.ms/AADsigninsErrorCodes> felkod. |
| `CorrelationId`        | sträng        | Unikt ID för inloggningshändelsen                                                                                                          |
| `ServicePrincipalName` | sträng        | Namnet på tjänstens huvudnamn som initierade inloggningen                                                                                        |
| `ServicePrincipalId`   | sträng        | Unikt ID för tjänstens huvudnamn som initierade inloggningen                                                                           |
| `ResourceDisplayName`  | sträng        | Visningsnamn för resursen som har åtkomst                                                                                                           |
| `ResourceId`           | sträng        | Unikt ID för den resurs som används                                                                                                      |
| `ResourceTenantId`     | sträng        | Unikt ID för klientorganisationen för resursen som används                                                                                        |
| `IPAddress`            | sträng        | IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation                                                              |
| `CountryCode`          | sträng        | Kod med två bokstäver som anger landet där klient-IP-adressen är geolokal                                                                |
| `State`                | sträng        | Delstat där inloggningen inträffade, om tillgänglig                                                                                                  |
| `City`                 | sträng        | Ort där kontoanvändaren finns                                                                                                          |
| `Latitude`             | sträng        | Koordinaterna för inloggningsplats för nord till syd                                                                                          |
| `Longitude`            | sträng        | Inloggningsplatsens koordinater för öst till väst                                                                                            |
| `RequestId`            | sträng        | Unik identifierare för begäran                                                                                                                |
|`ReportId` | sträng | Unikt ID för händelsen | 

 

## <a name="related-articles"></a>Relaterade artiklar

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [Översikt över avancerad jakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lär dig frågespråket](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Förstå schemat](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

