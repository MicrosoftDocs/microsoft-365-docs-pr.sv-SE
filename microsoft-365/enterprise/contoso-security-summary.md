---
title: Sammanfattning av Microsoft 365 för företags säkerhet för Contoso Corporation
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
ms.openlocfilehash: 2244f13f8e8f56edbadd40d1e85cb309d70f7744
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686446"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Sammanfattning av Microsoft 365 för företags säkerhet för Contoso Corporation

En grundlig säkerhets granskning utfördes för att få en genom gång av hur distributionen av Microsoft 365 för IT-avdelningen får logga ut. Här är Contosos säkerhetskrav för molnet:

- De starkaste autentiseringsmetoderna ska användas för medarbetarnas åtkomst till molnresurser
- Datorer och mobila enheten måste kunna ansluta till och komma åt programmen på ett säkert sätt
- Datorer och e-post ska skyddas mot skadlig kod
- Behörigheterna för molnbaserade digitala tillgångar ska definiera vem som har åtkomst till vad och vad de kan göra, och tilldelningen av behörigheterna ska följa principen om minsta möjliga behörighet
- Känsliga och strikt reglerade digitala tillgångar ska etiketteras, krypteras och lagras på säkra platser
- Strikt reglerade digitala tillgångar ska skyddas med ytterligare kryptering och behörigheter
- IT-säkerhetspersonal ska kunna övervaka aktuell säkerhetsstatus från centrala instrumentpaneler och få meddelanden om säkerhetshändelser så att de snabbt kan åtgärda brister och hot

## <a name="contosos-path-to-microsoft-365-security-readiness"></a>Contosos väg till säkerhetsberedskap för Microsoft 365

Contoso har följande steg för att klara deras säkerhet vid distribution av Microsoft 365 för företag:

1. Begränsade administratörskonton för molnet

   Contoso gjorde en omfattande översyn av AD DS-administratörskonton (Active Directory Domain Services) och konfigurerade en serie dedikerade molnadministratörskonton och grupper.

2. Dataklassificeringsanalyser utfördes på tre nivåer

   Contoso har gjort en noggrann recension och fastställt de tre nivåerna, som användes för att fastställa Microsoft 365 för Enterprise-funktioner för att skydda Contosos viktigaste data.

3. Principer för åtkomst, bevarande och informationsskydd fastställdes som datanivåer

   Baserat på datanivåerna ställde Contoso upp detaljerade krav för att kvalificera framtida IT-arbetsbelastningar som flyttas till molnet.

I enlighet med säkerhets rekommendationerna och Microsoft 365 för företags distributions krav har Contosos säkerhets administratörer och IT-avdelningen distribuerat många säkerhetsfunktioner och funktioner enligt beskrivningen i följande avsnitt.

## <a name="identity--access-management"></a>Identitets- och åtkomsthantering 

- Dedikerade globala administratörskonton med MFA och PIM

  I stället för att tilldela den globala administratörsrollen till de vanliga användarkontona skapade Contoso tre dedikerade globala administratörskonton med starka lösenord och skyddade dem med Azure Multi-Factor Authentication (MFA) och Azure Active Directory (Azure AD) Privileged Identity Management (PIM). PIM är endast tillgängligt med Microsoft 365 E5.

  Inloggning med ett globalt administratörskonto görs endast för specifika administrativa uppgifter, lösenorden är endast kända för utsedd personal och kan endast användas inom den tidsram som angetts med Azure AD PIM. 

  Contosos säkerhetsadministratörer har tilldelat administratörsroller med lägre behörighet för konton utifrån IT-medarbetarens jobbfunktion och ansvarsområden.

  Mer information finns i [Om Microsoft 365-administratörsroller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

- MFA för alla användarkonton

  MFA ger ett extra skyddslager för inloggningsprocessen i och med att användarna måste bekräfta ett telefonsamtal, sms eller en avisering via app på sin telefon efter att de angett korrekt lösenord. Med MFA skyddas Azure AD-användarkonton mot obehörig inloggning även om lösenordet för ett konto skulle komprometteras.

   - För att skydda Microsoft 365-prenumerationen mot obehöriga kräver Contoso att MFA tillämpas för alla globala administratörskonton.
   - För att skydda mot nätfiskeattacker (där angriparen försöker komma över autentiseringsuppgifterna för en betrodd person i organisationen och sedan skickar skadliga e-postmeddelanden) har Contoso aktiverat MFA för alla användarkonton, inklusive chefernas och ledningens konton. 

- Säkrare åtkomst till enheter och program med principer för villkorsstyrd åtkomst

  Contoso använder [principer för villkorsstyrd åtkomst](microsoft-365-policies-configurations.md) för identiteter, enheter, Exchange Online och SharePoint. Principer för villkorsstyrd åtkomst för identiteter omfattar krav på lösenordsändringar för högriskanvändare och appblockering i klienter så att det bara går att använda appar som stöder modern autentisering. Enhetsprinciperna omfattar definiering av godkända appar och krav på kompatibla datorer och mobila enheter. Principer för villkorsstyrd åtkomst för Exchange Online omfattar blockering av ActiveSync-klienter och konfiguration av meddelandekryptering i Office 365. Principer för villkorsstyrd åtkomst för SharePoint omfattar ytterligare skydd för känsliga och strikt reglerade webbplatser.

- Windows Hello för företag

  Contoso har distribuerats och kräver [Windows Hello för företag](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) för att ersätta användningen av lösenord med stark tvåfaktorautentisering på datorer och mobila enheter med Windows 10 Enterprise.

- Windows Defender Credential Guard

  För att förhindra att riktade attacker och skadlig kod kan köras med administratörsbehörighet i operativsystemet har Contoso aktiverat [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) via AD DS-grupprincip.

## <a name="threat-protection"></a>Skydd mot hot

- Skydd mot skadlig kod med Windows Defender Antivirus

  Contoso använder [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) som skydd mot skadlig kod och hantering av programvara som motverkar skadlig kod för datorer och enheter med Windows 10 Enterprise.

- Säkert e-postflöde och loggning av postlådegranskning med Office 365 Avancerat skydd 

  Contoso använder Exchange Online Protection och [Office](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) 365 Avancerat skydd som skydd mot okänd skadlig kod, virus och skadliga URL:er som skickas via e-post. 

  Contoso har även aktiverat loggning av postlådegranskning för att ta reda på vem som loggar in i användarnas postlådor, skickar meddelanden och utför andra aktiviteter som postlådans ägare, delegerad användare eller administratör.

- Övervakning och förebyggande av angrepp med undersökning av hot och åtgärder i Office 365 

  Contoso skyddar sina användare med [undersökning av hot och svar i Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-ti). På så sätt kan de enkelt identifiera och åtgärda attacker och förhindra framtida attacker.

- Skydd mot avancerade attacker med Advanced Threat Analytics

  Contoso använder [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) för att skydda sig mot avancerade riktade attacker.  ATA identifierar, analyserar och lär sig normalt och onormalt beteende för entiteter (användare, enheter och resurser). 

## <a name="information-protection"></a>Informationsskydd

- Skydda känsliga och strikt reglerade digitala tillgångar med Azure Information Protection-etiketter

  Contoso fastställde tre nivåer av dataskydd och distribuerade [Microsoft 365-känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) som användarna använder för digitala tillgångar. När det gäller affärshemligheter och andra immateriella egendomar använder Contoso underetiketter för känslighet för strikt reglerade data som krypterar innehåll och begränsar åtkomsten till specifika användarkonton och grupper.

- Förhindra dataläckor i intranätet med dataförlustskydd

  Contoso har konfigurerat principer för [dataförlustskydd](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) för Exchange Online, SharePoint och OneDrive för företag för att hindra användare från att oavsiktligt eller avsiktligt dela känsliga data.

- Förhindra dataläckor på enheter med Windows Information Protection

  Contoso använder [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) som skydd mot dataläckage via Internetbaserade appar och tjänster och via företagsprogram och data på de enheter som företaget äger och de privata enheter som medarbetarna tar med till jobbet.

- Molnövervakning med Microsoft Cloud App Security

  Contoso använder [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) för att kartlägga molnmiljön, övervaka dess användning och identifiera säkerhetshändelser och incidenter. Microsoft Cloud App Security är endast tillgängligt med Microsoft 365 E5.

- Enhetshantering med Microsoft Intune

  Contoso använder [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) för att registrera, hantera och konfigurera åtkomst till mobila enheter och de appar som körs på enheterna. Enhetsbaserade principer för villkorsstyrd åtkomst kräver också godkända appar och kompatibla datorer och mobila enheter.

## <a name="security-management"></a>Säkerhetshantering

- Central säkerhetsinstrumentpanel för IT med Azure Security Center

  Contoso använder [Azure Security Center](https://azure.microsoft.com/services/security-center/) för att hantera säkerhet och skydd mot hot, för att hantera säkerhetsprinciper för olika arbetsbelastningar och för att svara på cyberattacker.

- Central säkerhetsinstrumentpanel för användare med Windows Defender Säkerhetscenter

  Contoso har distribuerat [appen Windows-säkerhet](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) till de datorer och enheter som kör Windows 10 Enterprise, så att användarna snabbt kan se deras säkerhetsstatus och vidta åtgärder.

