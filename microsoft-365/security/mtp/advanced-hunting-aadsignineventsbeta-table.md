---
title: AADSignInEventsBeta-tabell i det avancerade jakt-schemat
description: Lär dig mer om den information som är kopplad till tabellen Azure Active Directory-inloggnings händelser för det avancerade Antivirus schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, fil, IP-adress, enhet, dator, användare, konto, identitet, AAD
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
ms.openlocfilehash: 1830eeec674c4948bd6492780ef8a0a8039111b8
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784293"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Gäller för:**

- Microsoft 365 Defender

>[!IMPORTANT]
> `AADSignInEventsBeta`Tabellen finns för närvarande i Beta versionen och erbjuds på ett kortsiktigt sätt så att du kan gå igenom inloggnings händelser för Azure Active Directory (AAD). Vi kommer slutligen att flytta all information om inloggnings schema till `IdentityLogonEvents` tabellen.<br><br>
> Kunder som kan komma åt Microsoft 365 Defender via Azure säkerhets centrets integrerade Microsoft Defender för slut punkts lösning, men inte har licenser för Microsoft Defender för Office, Microsoft Defender för identitet eller Microsoft Cloud App Security, kan inte visa detta schema. 

 

`AADSignInEventsBeta`Tabellen i det avancerade jakt-schemat innehåller information om aktiva och icke-interaktiva inloggnings uppgifter för Azure Active Directory. Läs mer om inloggning i [Azure Active Directory-inloggnings aktivitets rapporter – för hands version](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Använd den här referensen för att skapa frågor som returnerar information från tabellen.
Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).

 

 

| Kolumnnamn                 | Datatyp | Beskrivning          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Datum och tid när posten skapades                                                                                                                                         |
| `Application`                     | strängvärdet        | Program som utförde den inspelade åtgärden                                                                                                                                       |
| `ApplicationId`                   | strängvärdet        | Unik identifierare för programmet                                                                                                                                               |
| `LogonType`                       | strängvärdet        | Typ av inloggningssession, särskilt interaktivt, interaktivt (RDP), nätverk, batch och tjänst                                                                              |
| `ErrorCode`                       | signera        | Innehåller felkoden om ett inloggnings fel inträffar. För att hitta en beskrivning av en specifik felkod, gå till <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | strängvärdet        | Unik identifierare för inloggnings händelsen                                                                                                                                              |
| `SessionId`                       | strängvärdet        | Unikt nummer som tilldelats en användare via en webbplats server under besöket eller arbets passets varaktighet                                                                                     |
| `AccountDisplayName`              | strängvärdet        | Namnet på kontot som visas i adress boken. Vanligt vis en kombination av ett visst eller förnamn, en mellan initial och ett efter namn eller från gång.                             |
| `AccountObjectId`                 | strängvärdet        | Unik identifierare för kontot i Azure AD                                                                                                                                       |
| `AccountUpn`                      | strängvärdet        | Kontots huvud namn (UPN)                                                                                                                                            |
| `IsExternalUser`                  | signera        | Anger om den användare som är inloggad är extern. Möjliga värden:-1 (inte angivet), 0 (inte externt), 1 (extern).                                                                   |
| `IsGuestUser`                     | returtyp       | Anger om den användare som är inloggad är gäst i klient organisationen                                                                                                                  |
| `AlternateSignInName`             | strängvärdet        | Användarens lokala huvud namn (UPN) för användaren som loggar in i Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Datum och tid när användaren som loggade in senast ändrade sitt lösen ord                                                                                                              |
| `ResourceDisplayName`             | strängvärdet        | Visnings namn för den åtkomst som används för resursen                                                                                                                                               |
| `ResourceId`                      | strängvärdet        | Unik identifierare för den åtkomst som används för resursen                                                                                                                                          |
| `ResourceTenantId`                | strängvärdet        | Unik identifierare för innehavaren av resursen                                                                                                                            |
| `DeviceName`                      | strängvärdet        | Det fullständigt kvalificerade domän namnet (FQDN) för datorn                                                                                                                                   |
| `AadDeviceId`                     | strängvärdet   |      Unik identifierare för enheten i Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | strängvärdet        | Plattformen för det operativ system som körs på datorn. Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.  |
| `DeviceTrustType`                 | strängvärdet        | Anger förtroende typen för enheten som är inloggad. Endast för scenarier med hanterade enheter. Möjliga värden är Workplace, AzureAd och reserverad.                                     |
| `IsManaged`                       | signera       | Anger om enheten som initierade inloggningen är en hanterad enhet (1) eller inte en hanterad enhet (0)                                                                         |
| `IsCompliant`                     | signera       | Anger om enheten som initierade inloggningen är kompatibel (1) eller icke-kompatibel (0)                                                                                       |
| `AuthenticationProcessingDetails` | strängvärdet        | Information om autentiseringsprocessen                                                                                                                                          |
| `AuthenticationRequirement`       | strängvärdet        | Den autentiseringstyp som krävs för inloggningen. Möjliga värden: multiFactorAuthentication (MFA krävs) och singleFactorAuthentication (inga MFA krävs).                |
| `TokenIssuerType`                 | signera        | Anger om token-utgivaren är Azure Active Directory (0) eller Active Directory Federation Services (1)                                                                             |
| `RiskLevelAggregated`                       | signera        | Aggregerad risk nivå vid inloggning. Möjliga värden: 0 (aggregerad risknivå ej angiven), 1 (ingen), 10 (low), 50 (medel) eller 100 (hög).                               |
| `RiskDetails`                      | signera        | Information om risk läget för den användare som är inloggad                                                                                                                            |
| `RiskState`                       | signera        | Anger riskabelt användar tillstånd. Möjliga värden: 0 (inget), 1 (bekräftat Safe), 2 (åtgärdat), 3 (avstängt), 4 (i fara) eller 5 (bekräftat).                                |
| `UserAgent`                       | strängvärdet        | Information om användar agent från webbläsaren eller andra klient program                                                                                                             |
| `ClientAppUsed`                   | strängvärdet        | Anger vilket klient program som används                                                                                                                                                       |
| `Browser`                         | strängvärdet        | Information om vilken version av webbläsaren som användes för att logga in                                                                                                                            |
| `ConditionalAccessPolicies`       | strängvärdet        | Information om principer för villkorlig åtkomst som används för inloggnings händelsen                                                                                                             |
| `ConditionalAccessStatus`         | signera        | Status för principer för villkorsstyrd åtkomst som används för inloggningen. Möjliga värden är 0 (principer tillämpas), 1 (det går inte att tillämpa principer) eller 2 (principer tillämpas inte).      |
| `IPAddress`                       | strängvärdet        | IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation                                                                                                  |
| `CountryCode`                     | strängvärdet        | Kod med två bokstäver som anger det land där klient-IP-adressen finns                                                                                                    |
| `State`                           | strängvärdet        | Ange var inloggningen inträffar, om den är tillgänglig                                                                                                                                      |
| `City`                            | strängvärdet        | Ort där konto användaren finns                                                                                                                                              |
| `Latitude`                        | strängvärdet        | Norr till syd-koordinaterna för inloggnings platsen                                                                                                                              |
| `Longitude`                       | strängvärdet        | Östra till väst-koordinater för inloggnings platsen                                                                                                                                |
| `NetworkLocationDetails`          | strängvärdet        | Nätverks plats information för autentiseringsprocessen för inloggnings händelsen                                                                                                       |
| `RequestId`                       | strängvärdet        |  Unik identifierare för begäran                                                                                                                                                   |
|`ReportId` | strängvärdet | Unik identifierare för händelsen |

 

 

## <a name="related-articles"></a>Relaterade artiklar

-   [AADSpnSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadspnsignineventsbeta-table)
-   [Översikt över avancerad jakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lär dig frågespråket](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Förstå schemat](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
