---
title: AADSpnSignInEventsBeta-tabell i det avancerade jakt-schemat
description: Lär dig mer om den information som är kopplad till tabellen för inloggnings händelser för Azure Active Directory-tjänsten och det avancerade Antivirus schema
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, avisering, enheter, bevis, fil, IP-adress, enhet, dator, användare, konto, identitet, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784305"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Gäller för:**

- Microsoft 365 Defender

>[!IMPORTANT]
> `AADSpnSignInEventsBeta`Tabellen finns för närvarande i Beta versionen och erbjuds på ett kortsiktigt sätt så att du kan gå igenom alla inloggnings händelser för Azure Active Directory-tjänsten (AAD) och hanterad identitet. Vi kommer slutligen att flytta all information om inloggnings schema till `IdentityLogonEvents` tabellen.<br><br>
> Kunder som kan komma åt Microsoft 365 Defender via Azure säkerhets centrets integrerade Microsoft Defender för slut punkts lösning, men inte har licenser för Microsoft Defender för Office, Microsoft Defender för identitet eller Microsoft Cloud App Security, kan inte visa detta schema. 



`AADSpnSignInEventsBeta`Tabellen i det avancerade jakt-schemat innehåller information om Azure Active Directory-tjänstens huvud konto och inloggnings uppgifter för hanterade identiteter. Du kan läsa mer om olika typer av inloggnings uppgifter i [Azure Active Directory-inloggnings aktivitets rapporter – för hands version](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Kolumnnamn     | Datatyp | Beskrivning   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Datum och tid när posten skapades                                                                                                     |
| `Application`          | strängvärdet        | Program som utförde den inspelade åtgärden                                                                                                   |
| `ApplicationId`        | strängvärdet        | Unik identifierare för programmet                                                                                                           |
| `IsManagedIdentity`    | returtyp       | Anger om inloggningen initierats av en hanterad identitet                                                                               |
| `ErrorCode`            | signera        | Innehåller felkoden om ett inloggnings fel inträffar. För att hitta en beskrivning av en specifik felkod, gå till <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | strängvärdet        | Unik identifierare för inloggnings händelsen                                                                                                          |
| `ServicePrincipalName` | strängvärdet        | Namnet på tjänstens huvud namn som initierade inloggningen                                                                                        |
| `ServicePrincipalId`   | strängvärdet        | Unik identifierare för tjänstens huvud namn som initierade inloggningen                                                                           |
| `ResourceDisplayName`  | strängvärdet        | Visnings namn för den åtkomst som används för resursen                                                                                                           |
| `ResourceId`           | strängvärdet        | Unik identifierare för den åtkomst som används för resursen                                                                                                      |
| `ResourceTenantId`     | strängvärdet        | Unik identifierare för innehavaren av resursen                                                                                        |
| `IPAddress`            | strängvärdet        | IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation                                                              |
| `CountryCode`          | strängvärdet        | Kod med två bokstäver som anger det land där klient-IP-adressen finns                                                                |
| `State`                | strängvärdet        | Ange var inloggningen inträffar, om den är tillgänglig                                                                                                  |
| `City`                 | strängvärdet        | Ort där konto användaren finns                                                                                                          |
| `Latitude`             | strängvärdet        | Norr till syd-koordinaterna för inloggnings platsen                                                                                          |
| `Longitude`            | strängvärdet        | Östra till väst-koordinater för inloggnings platsen                                                                                            |
| `RequestId`            | strängvärdet        | Unik identifierare för begäran                                                                                                                |
|`ReportId` | strängvärdet | Unik identifierare för händelsen | 

 

## <a name="related-articles"></a>Relaterade artiklar

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [Översikt över avancerad jakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lär dig frågespråket](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Förstå schemat](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

