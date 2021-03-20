---
title: Sammanfattning av Microsoft 365 för företagssäkerhet för Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Hur Contoso använder säkerhetsfunktionerna i Microsoft 365 för företag.
ms.openlocfilehash: 31baf61011fb67fbe11394718086d73afa2bc680
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907668"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Sammanfattning av Microsoft 365 för företagssäkerhet för Contoso Corporation

För att få godkännande för att distribuera Microsoft 365 för företag utförde Contoso IT-säkerhetsavdelningen en noggrann säkerhetsgranskning. De har identifierat följande säkerhetskrav för molnet:

- Använd de starkaste metoderna för autentisering för anställdas åtkomst till molnresurser.
- Se till att datorer och mobila enheter ansluter och kommer åt program på ett säkert sätt.
- Skydda datorer och e-post från skadlig programvara.
- Behörigheter för molnbaserade digitala tillgångar definierar vem som kan komma åt vad och vad de kan göra, och är utformade för åtkomst med minst behörighet
- Känsliga och högt reglerade digitala tillgångar etiketteras, krypteras och lagras på säkra platser.
- Mycket reglerade digitala tillgångar skyddas med ytterligare kryptering och behörigheter.
- IT-säkerhetspersonalen kan övervaka den aktuella säkerheten från centrala instrumentpaneler och få meddelanden om säkerhetshändelser för snabb respons och minskning.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Contoso-vägen till säkerhetsberedskapen i Microsoft 365

Contoso följde de här stegen för att förbereda säkerheten för distributionen av Microsoft 365 för företag:

1. Begränsa administratörskonton för molnet

   Contoso har gjort en omfattande granskning av sina befintliga AD DS-administratörskonton (Active Directory Domain Services) och ställt in en serie dedikerade molnadministratörskonton och grupper.

2. Klassificera data i tre säkerhetsnivåer

   Contoso har gjort en noggrann granskning och fastställt de tre nivåerna, som användes för att identifiera Microsoft 365 för företag-funktioner för att skydda den mest värdefulla informationen.

3. Fastställa åtkomst-, bevarande- och informationsskyddsprinciper för datanivåer

   Utifrån datanivåer bestämde Contoso detaljerade krav för att kvalificera framtida IT-arbetsbelastningar som flyttas till molnet.

För att följa metodtips för säkerhet och Microsoft 365 för företagsdistributionskrav har Contoso-säkerhetsadministratörerna och DESS IT-avdelningen distribuerat många säkerhetsfunktioner, enligt beskrivningen i följande avsnitt.

## <a name="identity-and-access-management"></a>Identitets- och åtkomsthantering 

- Dedikerade globala administratörskonton med MFA och PIM

  I stället för att tilldela den globala administratörsrollen till vanliga användarkonton skapade Contoso tre dedikerade globala administratörskonton med starka lösenord. Kontona skyddas av Azure AD Multi-Factor Authentication (MFA) och Azure Active Directory (Azure AD) Privileged Identity Management (PIM). *PIM är endast tillgängligt med Microsoft 365 E5.*

  Inloggning med ett globalt administratörskonto utförs endast för specifika administrativa uppgifter. Lösenorden är endast kända för angiven personal och kan endast användas under en tidsperiod som har konfigurerats i Azure AD PIM.

  Contoso-säkerhetsadministratörer som tilldelats mindre administratörsroller till konton som är lämpliga för IT-medarbetarens jobbfunktion.

  Mer information finns i [Om Microsoft 365-administratörsroller](/office365/admin/add-users/about-admin-roles).

- MFA för alla användarkonton

  Med MFA får du ytterligare ett skyddslager i inloggningsprocessen. Användaren måste bekräfta ett telefonsamtal, sms eller appmeddelande på sin smartphone när de har angett sitt lösenord korrekt. Med MFA skyddas Azure AD-användarkonton mot obehörig inloggning, även om ett kontolösenord har komprometterats.

   - För att skydda mot kompromettation av Microsoft 365-prenumerationen kräver Contoso MFA för alla globala administratörskonton.
   - För att skydda mot nätfiskeattacker (där angriparen försöker komma över autentiseringsuppgifterna för en betrodd person i organisationen och sedan skickar skadliga e-postmeddelanden) har Contoso aktiverat MFA för alla användarkonton, inklusive chefernas och ledningens konton.

- Säkrare åtkomst till enheter och program med principer för villkorsstyrd åtkomst

  Contoso använder [principer för villkorsstyrd åtkomst](../security/office-365-security/microsoft-365-policies-configurations.md) för identiteter, enheter, Exchange Online och SharePoint. Principer för villkorsstyrd åtkomst för identiteter omfattar krav på lösenordsändringar för högriskanvändare och appblockering i klienter så att det bara går att använda appar som stöder modern autentisering. Enhetsprinciperna omfattar definiering av godkända appar och krav på kompatibla datorer och mobila enheter. Principer för villkorsstyrd åtkomst för Exchange Online omfattar blockering av ActiveSync-klienter och konfiguration av meddelandekryptering i Office 365. Principer för villkorsstyrd åtkomst för SharePoint omfattar ytterligare skydd för känsliga och strikt reglerade webbplatser.

- Windows Hello för företag

  Contoso distribuerade [Windows Hello för företag](/windows/security/identity-protection/hello-for-business/hello-identity-verification) för att så småningom eliminera behovet av lösenord genom stark tvåfaktorautentisering på datorer och mobila enheter med Windows 10 Enterprise.

- Windows Defender Credential Guard

  För att blockera riktade attacker och skadlig programvara som körs i operativsystemet med administrativ behörighet aktiverar Contoso [Windows Defender Credential Guard](/windows/security/identity-protection/credential-guard/credential-guard) via AD DS-grupprincipen.

## <a name="threat-protection"></a>Skydd mot hot

- Skydd mot skadlig kod med Windows Defender Antivirus

  Contoso använder [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) som skydd mot skadlig kod och hantering av programvara som motverkar skadlig kod för datorer och enheter med Windows 10 Enterprise.

- Säker e-postflödes- och granskningsloggning för postlådor med Microsoft Defender för Office 365 

  Contoso använder Exchange Online Protection och Defender för [Office 365](/office365/securitycompliance/office-365-atp) för att skydda mot okänd skadlig programvara, virus och skadliga URL-adresser som överförs via e-post.

  Contoso aktiverade även granskningsloggning för postlådor för att identifiera vem som loggar in i användarnas postlådor, skickar meddelanden och utför andra aktiviteter som utförs av postlådans ägare, en delegerad användare eller en administratör.

- Övervakning och förebyggande av angrepp med undersökning av hot och åtgärder i Office 365 

  Contoso använder [office 365-undersökning](/office365/securitycompliance/office-365-ti) av hot och svar för att skydda användare genom att göra det enkelt att identifiera och åtgärda attacker och förhindra framtida attacker.

- Skydd mot avancerade attacker med Advanced Threat Analytics

  Contoso använder [Advanced Threat Analytics (ATA)](/advanced-threat-analytics/what-is-ata) för att skydda sig mot avancerade riktade attacker.  ATA identifierar, analyserar och lär sig normalt och onormalt beteende för entiteter (användare, enheter och resurser).

## <a name="information-protection"></a>Informationsskydd

- Skydda känsliga och strikt reglerade digitala tillgångar med Azure Information Protection-etiketter

  Contoso fastställde tre nivåer av dataskydd och distribuerade [Microsoft 365-känslighetsetiketter](../compliance/sensitivity-labels.md) som användarna använder för digitala tillgångar. För dess affärshemligheter och andra immateriella rättigheter använder Contoso känslighetsunderetiketter för starkt reglerade data. Den här processen krypterar innehåll och begränsar åtkomsten till specifika användarkonton och grupper.

- Förhindra dataläckor i intranätet med dataförlustskydd

  Contoso har konfigurerat [principer för dataförlustskydd](../compliance/data-loss-prevention-policies.md) för Exchange Online, SharePoint och OneDrive för företag för att förhindra att användare avsiktligt eller oavsiktligt delar känsliga data.

- Förhindra dataläckor på enheter med Windows Information Protection

  Contoso använder [Windows Information Protection (WIP)](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) för att skydda mot dataläck via internetbaserade appar och tjänster och företagsdata på företagsägda enheter och personliga enheter som anställda använder för att fungera.

- Molnövervakning med Microsoft Cloud App Security

  Contoso använder [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) för att kartlägga molnmiljön, övervaka dess användning och identifiera säkerhetshändelser och incidenter. *Microsoft Cloud App Security är endast tillgängligt med Microsoft 365 E5.*

- Enhetshantering med Microsoft Intune

  Contoso använder [Microsoft Intune](/intune/introduction-intune) för att registrera, hantera och konfigurera åtkomst till mobila enheter och de appar som körs på enheterna. Enhetsbaserade principer för villkorsstyrd åtkomst kräver också godkända appar och kompatibla datorer och mobila enheter.

## <a name="security-management"></a>Säkerhetshantering

- Central säkerhetsinstrumentpanel för IT med Azure Defender

  Contoso använder [Azure Defender](https://azure.microsoft.com/services/security-center/) för att presentera en enhetlig vy över säkerhet- och hotskydd, för att hantera säkerhetsprinciper i arbetsbelastningen och för att svara på cyberattacker.

- Central säkerhetsinstrumentpanel för användare med Windows Defender Säkerhetscenter

  Contoso har distribuerat [Windows-säkerhetsappen](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) till sina datorer och enheter som kör Windows 10 Enterprise, så att användarna snabbt kan se sin säkerhetsstatus och vidta åtgärder.