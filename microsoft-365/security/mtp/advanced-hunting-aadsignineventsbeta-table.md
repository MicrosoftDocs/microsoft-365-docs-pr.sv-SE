---
title: AADSignInEventsBeta-tabell i det avancerade sökschemat
description: Läs mer om informationen som är kopplad till tabellen för azure Active Directory-inloggningshändelser i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: 50f112f6e7198136171d070dc483ad5f84d20d57
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925768"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Gäller för:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Tabellen är för närvarande i betaversion och erbjuds inom kort för att du ska kunna leta efter inloggningshändelser i `AADSignInEventsBeta` Azure Active Directory (AAD). Så småningom flyttar vi all information i inloggningsschemat till `IdentityLogonEvents` tabellen.<br><br>
> Kunder som har åtkomst till Microsoft 365 Defender via Azure Säkerhetscenters integrerade Microsoft Defender för slutpunktslösning, men inte har licenser för Microsoft Defender för Office, Microsoft Defender för identitet eller Microsoft Cloud App Security, kommer inte att kunna se det här schemat. 

 

Tabellen `AADSignInEventsBeta` i det avancerade sökschemat innehåller information om interaktiva och icke-interaktiva inloggningar i Azure Active Directory. Läs mer om inloggningar i inloggningsaktivitetsrapporter [för Azure Active Directory – förhandsversion.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Använd den här referensen för att skapa frågor som returnerar information från tabellen.
Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)

 

 

| Kolumnnamn                 | Datatyp | Beskrivning          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Datum och tid då posten skapades                                                                                                                                         |
| `Application`                     | sträng        | Program som utförde den inspelade åtgärden                                                                                                                                       |
| `ApplicationId`                   | sträng        | Unikt ID för programmet                                                                                                                                               |
| `LogonType`                       | sträng        | Typ av inloggningssession, specifikt interaktiv, fjärr interaktiv (RDP), nätverk, batch och tjänst                                                                              |
| `ErrorCode`                       | int        | Innehåller felkoden om ett inloggningsfel uppstår. Gå till för att hitta en beskrivning av en specifik <https://aka.ms/AADsigninsErrorCodes> felkod.                                     |
| `CorrelationId`                   | sträng        | Unikt ID för inloggningshändelsen                                                                                                                                              |
| `SessionId`                       | sträng        | Unikt nummer som tilldelats en användare av en webbplatsserver under hela besöket eller sessionen                                                                                     |
| `AccountDisplayName`              | sträng        | Namnet på kontoanvändaren som visas i adressboken. Detta är en kombination av ett givet eller förnamn, en initial för mellannamn och efternamn eller efternamn.                             |
| `AccountObjectId`                 | sträng        | Unikt ID för kontot i Azure AD                                                                                                                                       |
| `AccountUpn`                      | sträng        | Användarkontons huvudnamn (UPN)                                                                                                                                            |
| `IsExternalUser`                  | int        | Anger om användaren som loggat in är extern. Möjliga värden: -1 (inte angett) , 0 (inte extern), 1 (extern).                                                                   |
| `IsGuestUser`                     | boolesk       | Anger om användaren som loggade in är gäst i klientorganisationen                                                                                                                  |
| `AlternateSignInName`             | sträng        | Lokalt användarhuvudnamn (UPN) för användaren som loggar in i Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Datum och tid då användaren som loggade in senast ändrade sitt lösenord                                                                                                              |
| `ResourceDisplayName`             | sträng        | Visningsnamn för den resurs som har åtkomst                                                                                                                                               |
| `ResourceId`                      | sträng        | Unikt ID för den resurs som används                                                                                                                                          |
| `ResourceTenantId`                | sträng        | Unikt ID för klientorganisationen för den resurs som används                                                                                                                            |
| `DeviceName`                      | sträng        | Fullständigt kvalificerat domännamn (FQDN) för datorn                                                                                                                                   |
| `AadDeviceId`                     | sträng   |      Unikt ID för enheten i Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | sträng        | Operativsystemets plattform som körs på datorn. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.  |
| `DeviceTrustType`                 | sträng        | Anger förtroendetypen för den enhet som är inloggad. Endast för scenarier med hanterade enheter. Möjliga värden är Workplace, AzureAd och ServerAd.                                     |
| `IsManaged`                       | int       | Anger om enheten som initierade inloggningen är en hanterad enhet (1) eller inte en hanterad enhet (0)                                                                         |
| `IsCompliant`                     | int       | Anger om enheten som initierade inloggningen är kompatibel (1) eller icke-kompatibel (0)                                                                                       |
| `AuthenticationProcessingDetails` | sträng        | Information om autentiseringsprocessorn                                                                                                                                          |
| `AuthenticationRequirement`       | sträng        | Typ av autentisering som krävs för inloggningen. Möjliga värden: multiFactorAuthentication (MFA var obligatoriskt) och singleFactorAuthentication (ingen MFA krävs).                |
| `TokenIssuerType`                 | int        | Anger om tokenutfärdaren är Azure Active Directory (0) eller Active Directory Federation Services (1)                                                                             |
| `RiskLevelAggregated`                       | int        | Aggregerad risknivå vid inloggning. Möjliga värden: 0 (aggregerad risknivå har inte angetts), 1 (ingen), 10 (låg), 50 (medium) eller 100 (hög).                               |
| `RiskDetails`                      | int        | Information om riskabel status för den användare som loggat in                                                                                                                            |
| `RiskState`                       | int        | Anger riskabel användartillstånd. Möjliga värden: 0 (inget), 1 (bekräftat kassaskåp), 2 (åtgärdat), 3 (avvisat), 4 (i riskabelt) eller 5 (bekräftad komprometterad).                                |
| `UserAgent`                       | sträng        | Information om användaragenter från webbläsaren eller ett annat klientprogram                                                                                                             |
| `ClientAppUsed`                   | sträng        | Anger klientappen som används                                                                                                                                                       |
| `Browser`                         | sträng        | Information om vilken version av webbläsaren som användes för att logga in                                                                                                                            |
| `ConditionalAccessPolicies`       | sträng        | Detaljerad information om principer för villkorsstyrd åtkomst som tillämpas på inloggningshändelsen                                                                                                             |
| `ConditionalAccessStatus`         | int        | Status för de villkorsstyrda åtkomstprinciper som tillämpas på inloggningen. Möjliga värden är 0 (principer tillämpade), 1 (försök att tillämpa principer misslyckades) eller 2 (principer används inte).      |
| `IPAddress`                       | sträng        | IP-adress tilldelad till slutpunkten och används under relaterad nätverkskommunikation                                                                                                  |
| `Country`                     | sträng        | Kod med två bokstäver som anger landet där klientens IP-adress är geolocerad                                                                                                    |
| `State`                           | sträng        | Delstat där inloggningen inträffade, om tillgänglig                                                                                                                                      |
| `City`                            | sträng        | Ort där kontoanvändaren finns                                                                                                                                              |
| `Latitude`                        | sträng        | Koordinaterna för inloggning i nord till syd                                                                                                                              |
| `Longitude`                       | sträng        | Koordinaterna för inloggningsplatsen öst till väst                                                                                                                                |
| `NetworkLocationDetails`          | sträng        | Information om nätverksplats för autentiseringsprocessorn för inloggningshändelsen                                                                                                       |
| `RequestId`                       | sträng        |  Unikt ID för begäran                                                                                                                                                   |
|`ReportId` | sträng | Unikt ID för händelsen |

 

 

## <a name="related-articles"></a>Relaterade artiklar

-   [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
-   [Översikt över avancerad jakt](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lär dig frågespråket](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Förstå schemat](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 