---
title: AADSignInEventsBeta-tabell i det avancerade sökschemat
description: Läs mer om information om tabellen inloggningshändelser för Azure Active Directory i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, fil, IP-adress, enhet, dator, användare, konto, identitet, AAD
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
ms.openlocfilehash: 174db150920d2d95c043bb5d6e5a4593ea1ea39d
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145433"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Gäller för:**

- Microsoft 365 Defender

>[!IMPORTANT]
> Tabellen är för närvarande i betaversion och erbjuds på kort sikt så att du kan jaga via `AADSignInEventsBeta` Azure Active Directory (AAD) inloggningshändelser. Så småningom flyttar vi all information i inloggningsschemat till `IdentityLogonEvents` tabellen.<br><br>
> Kunder som kan komma åt Microsoft 365 Defender via Azure Säkerhetscenters integrerade Microsoft Defender för slutpunktslösning, men inte har licenser för Microsoft Defender för Office, Microsoft Defender för identitet eller Microsoft Cloud App Security, kommer inte att kunna se det här schemat. 

 

Tabellen `AADSignInEventsBeta` i det avancerade utbildningsschemat innehåller information om interaktiva och icke-interaktiva inloggningar i Azure Active Directory. Läs mer om inloggningar i inloggningsrapporter [för Azure Active Directory - förhandsversion.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Använd den här referensen för att skapa frågor som returnerar information från tabellen.
Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)

 

 

| Kolumnnamn                 | Datatyp | Beskrivning          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Datum och tid då posten skapades                                                                                                                                         |
| `Application`                     | sträng        | Program som utförde den inspelade åtgärden                                                                                                                                       |
| `ApplicationId`                   | sträng        | Unikt ID för programmet                                                                                                                                               |
| `LogonType`                       | sträng        | Typ av inloggningssession, specifikt interaktiv, fjärr interaktiv (RDP), nätverk, batch och tjänst                                                                              |
| `ErrorCode`                       | int        | Innehåller felkoden om det uppstår ett inloggningsfel. Gå till en beskrivning av en specifik <https://aka.ms/AADsigninsErrorCodes> felkod.                                     |
| `CorrelationId`                   | sträng        | Unikt ID för inloggningshändelsen                                                                                                                                              |
| `SessionId`                       | sträng        | Unikt nummer som tilldelats en användare av en webbplatsserver under hela besöket eller sessionen                                                                                     |
| `AccountDisplayName`              | sträng        | Namnet på kontoanvändaren som visas i adressboken. Vanligtvis en kombination av ett visst namn eller förnamn, en initial för mellannamn och efternamn eller efternamn.                             |
| `AccountObjectId`                 | sträng        | Unikt ID för kontot i Azure AD                                                                                                                                       |
| `AccountUpn`                      | sträng        | Kontots huvudnamn (UPN)                                                                                                                                            |
| `IsExternalUser`                  | int        | Anger om användaren som loggat in är extern. Möjliga värden: -1 (inte angett) , 0 (inte extern), 1 (extern).                                                                   |
| `IsGuestUser`                     | boolesk       | Anger om användaren som loggat in är gäst i klientorganisationen                                                                                                                  |
| `AlternateSignInName`             | sträng        | Lokalt användarhuvudnamn (UPN) för användaren som loggar in i Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Datum och tid då användaren som loggade in senast ändrade sitt lösenord                                                                                                              |
| `ResourceDisplayName`             | sträng        | Visningsnamn för resursen som har åtkomst                                                                                                                                               |
| `ResourceId`                      | sträng        | Unikt ID för den resurs som används                                                                                                                                          |
| `ResourceTenantId`                | sträng        | Unikt ID för klientorganisationen för resursen som används                                                                                                                            |
| `DeviceName`                      | sträng        | Fullständigt kvalificerat domännamn (FQDN) för datorn                                                                                                                                   |
| `AadDeviceId`                     | sträng   |      Unikt ID för enheten i Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | sträng        | Operativsystemets plattform som körs på datorn. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.  |
| `DeviceTrustType`                 | sträng        | Anger förtroendetypen för den enhet som loggade in. Endast för scenarier med hanterade enheter. Möjliga värden är Workplace, AzureAd och ServerAd.                                     |
| `IsManaged`                       | int       | Anger om enheten som initierade inloggningen är en hanterad enhet (1) eller inte en hanterad enhet (0)                                                                         |
| `IsCompliant`                     | int       | Anger om enheten som initierade inloggningen är kompatibel (1) eller inte (0)                                                                                       |
| `AuthenticationProcessingDetails` | sträng        | Information om autentiseringsprocessorn                                                                                                                                          |
| `AuthenticationRequirement`       | sträng        | Typ av autentisering som krävs för inloggningen. Möjliga värden: multiFactorAuthentication (MFA) och enkelFactorAuthentication (ingen MFA var obligatoriskt).                |
| `TokenIssuerType`                 | int        | Anger om tokenutfärdaren är Azure Active Directory (0) eller Active Directory Federation Services (1)                                                                             |
| `RiskLevelAggregated`                       | int        | Aggregerad risknivå vid inloggning. Möjliga värden: 0 (aggregerad risknivå har inte angetts), 1 (ingen), 10 (låg), 50 (medium) eller 100 (hög).                               |
| `RiskDetails`                      | int        | Information om den riskfyllda statusen för den användare som loggade in                                                                                                                            |
| `RiskState`                       | int        | Anger riskabelt användartillstånd. Möjliga värden: 0 (ingen), 1 (bekräftat kassaskåp), 2 (åtgärdat), 3 (avvisat), 4 (i riskabelt) eller 5 (bekräftad komprometterad).                                |
| `UserAgent`                       | sträng        | Information om användaragenter från webbläsaren eller ett annat klientprogram                                                                                                             |
| `ClientAppUsed`                   | sträng        | Anger klientappen som används                                                                                                                                                       |
| `Browser`                         | sträng        | Information om vilken version av webbläsaren som användes för att logga in                                                                                                                            |
| `ConditionalAccessPolicies`       | sträng        | Information om villkorsstyrda åtkomstprinciper som tillämpas på inloggningshändelsen                                                                                                             |
| `ConditionalAccessStatus`         | int        | Status för villkorsstyrda åtkomstprinciper som tillämpas på inloggningen. Möjliga värden är 0 (principer tillämpade), 1 (försök att använda principer misslyckades) eller 2 (principer tillämpas inte).      |
| `IPAddress`                       | sträng        | IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation                                                                                                  |
| `Country`                     | sträng        | Kod med två bokstäver som anger landet där klient-IP-adressen är geolokal                                                                                                    |
| `State`                           | sträng        | Delstat där inloggningen inträffade, om tillgänglig                                                                                                                                      |
| `City`                            | sträng        | Ort där kontoanvändaren finns                                                                                                                                              |
| `Latitude`                        | sträng        | Koordinaterna för inloggningsplats för nord till syd                                                                                                                              |
| `Longitude`                       | sträng        | Inloggningsplatsens koordinater för öst till väst                                                                                                                                |
| `NetworkLocationDetails`          | sträng        | Information om nätverksplats för autentiseringsprocessorn för inloggningshändelsen                                                                                                       |
| `RequestId`                       | sträng        |  Unik identifierare för begäran                                                                                                                                                   |
|`ReportId` | sträng | Unikt ID för händelsen |

 

 

## <a name="related-articles"></a>Relaterade artiklar

-   [AADSpnSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadspnsignineventsbeta-table)
-   [Översikt över avancerad jakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Lär dig frågespråket](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Förstå schemat](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
