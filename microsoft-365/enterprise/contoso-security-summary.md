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
ms.openlocfilehash: 5c951a973fbebeff92040f9411ad2c81788f920a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558400"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Sammanfattning av Microsoft 365 för företags säkerhet för Contoso Corporation

För att få godkännande för att distribuera Microsoft 365 för företag har den contoso IT-säkerhetsavdelningen en grundlig säkerhets recension. De har identifierat följande säkerhets krav för molnet:

- Använd de starkaste autentiseringsmetoderna för åtkomst till moln resurser för anställda.
- Se till att datorer och mobila enheter ansluter och kommer åt program på säkra sätt.
- Skydda datorer och e-post från skadlig program vara.
- Behörigheter för molnbaserade digital till gångar definierar vem som kan komma åt vad och vad de kan göra, och det är utformat för åtkomst med tillstånd för användare med tillstånd
- Känslig och högreglerade digitala till gångar kallas, är krypterade och lagras på säkra platser.
- Högreglerade digital till gångar skyddas med ytterligare kryptering och behörigheter.
- IT-säkerhetspersonalen kan övervaka den aktuella säkerhets Posture från Central instrument paneler och få meddelanden om säkerhets händelser för snabba svar och mildrande åtgärder.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Contoso-sökvägen till Microsoft 365-säkerhets beredskap

Contoso följer de här stegen för att förbereda sin säkerhet för distribution av Microsoft 365 för företag:

1. Begränsa administratörs konton för molnet

   Contoso gjorde en omfattande recension av sina befintliga Active Directory Domain Services (AD DS)-administratörs konton och har konfigurerat en serie med dedikerade moln administratörs konton och grupper.

2. Klassificera data i tre säkerhets nivåer

   Contoso gjorde en noggrann recension och fastställde de tre nivåerna, som användes för att identifiera Microsoft 365 för Enterprise-funktioner för att skydda den mest värdefulla informationen.

3. Bestämma åtkomst, bevarande och informations skydds principer för data nivåer

   Baserat på data nivåerna fastställdes contoso detaljerade krav för att kvalificera framtida IT-arbetsbelastningar som flyttas till molnet.

Om du vill följa säkerhets praxis och Microsoft 365 för företags distributions krav kan Contosos säkerhets administratörer och IT-avdelningen distribuera många säkerhetsfunktioner och funktioner enligt beskrivningen i följande avsnitt.

## <a name="identity-and-access-management"></a>Identitets- och åtkomsthantering 

- Dedikerade globala administratörskonton med MFA och PIM

  I stället för att tilldela rollen global administratör till vardagliga användar konton, har contoso tre dedikerade globala administratörs konton med starka lösen ord. Kontona skyddas av Azure AD Multi-Factor inloggningsautentisering (MFA) och Azure Active Directory (Azure AD) privilegierad identitets hantering (PIM). *PIM är endast tillgängligt med Microsoft 365 E5.*

  Det är bara att logga in med ett globalt administratörs konto för specifika administrativa uppgifter. Lösen orden är bara kända för den avsedda personalen och kan endast användas inom en tids period som är konfigurerad i Azure AD PIM.

  Contoso-säkerhetsadministratörer har tilldelat färre administratörs roller till konton som är lämpliga för arbets uppgiftens jobb funktion.

  Mer information finns i [Om Microsoft 365-administratörsroller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

- MFA för alla användarkonton

  MFA lägger till ytterligare ett skydds lager för inloggnings processen. För att användare ska kunna bekräfta ett telefonsamtal, SMS eller ett program meddelande på deras mobil telefon när du har angett lösen ordet korrekt. Med MFA skyddas Azure AD-användarkonton mot obehörig inloggning, även om ett konto lösen ord äventyras.

   - Contoso kräver MFA för alla globala administratörs konton för att skydda mot problem med Microsoft 365-prenumerationen.
   - För att skydda mot nätfiskeattacker (där angriparen försöker komma över autentiseringsuppgifterna för en betrodd person i organisationen och sedan skickar skadliga e-postmeddelanden) har Contoso aktiverat MFA för alla användarkonton, inklusive chefernas och ledningens konton.

- Säkrare åtkomst till enheter och program med principer för villkorsstyrd åtkomst

  Contoso använder [principer för villkorsstyrd åtkomst](../security/office-365-security/microsoft-365-policies-configurations.md) för identiteter, enheter, Exchange Online och SharePoint. Principer för villkorsstyrd åtkomst för identiteter omfattar krav på lösenordsändringar för högriskanvändare och appblockering i klienter så att det bara går att använda appar som stöder modern autentisering. Enhetsprinciperna omfattar definiering av godkända appar och krav på kompatibla datorer och mobila enheter. Principer för villkorsstyrd åtkomst för Exchange Online omfattar blockering av ActiveSync-klienter och konfiguration av meddelandekryptering i Office 365. Principer för villkorsstyrd åtkomst för SharePoint omfattar ytterligare skydd för känsliga och strikt reglerade webbplatser.

- Windows Hello för företag

  Contoso distribuerade [Windows Hello för företag](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) för att eliminera behovet av lösen ord via starkt tvåfaktorautentisering på datorer och mobila enheter som kör Windows 10 Enterprise.

- Windows Defender Credential Guard

  För att blockera riktade attacker och skadlig program vara som körs i operativ systemet med administratörs behörighet, contoso-aktiverad [Windows Defender-Autentiseringshanteraren](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) genom AD DS-Grupprincip.

## <a name="threat-protection"></a>Skydd mot hot

- Skydd mot skadlig kod med Windows Defender Antivirus

  Contoso använder [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) som skydd mot skadlig kod och hantering av programvara som motverkar skadlig kod för datorer och enheter med Windows 10 Enterprise.

- Skydda e-postflöde och gransknings loggning med Microsoft Defender för Office 365 

  Contoso använder Exchange Online Protection och [Defender för Office 365 för](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) att skydda mot okända skadlig program vara, virus och illasinnade webb adresser.

  Contoso har också aktiverat gransknings loggning för post lådor för att identifiera vem som loggar in i en användares post låda, skickar meddelanden och andra aktiviteter som utförs av post lådans ägare, en delegerad användare eller administratör.

- Övervakning och förebyggande av angrepp med undersökning av hot och åtgärder i Office 365 

  Contoso använder [Office 365 hot-undersökning och-svar](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) för att skydda användare genom att göra det lätt att identifiera och rikta mot attacker och förhindra framtida attacker.

- Skydd mot avancerade attacker med Advanced Threat Analytics

  Contoso använder [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) för att skydda sig mot avancerade riktade attacker.  ATA identifierar, analyserar och lär sig normalt och onormalt beteende för entiteter (användare, enheter och resurser).

## <a name="information-protection"></a>Informationsskydd

- Skydda känsliga och strikt reglerade digitala tillgångar med Azure Information Protection-etiketter

  Contoso fastställde tre nivåer av dataskydd och distribuerade [Microsoft 365-känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) som användarna använder för digitala tillgångar. För dess affärs hemligheter och andra immateriella rättigheter använder contoso känslighets under etiketter för data med hög reglering. Den här processen krypterar innehåll och begränsar åtkomsten till specifika användar konton och grupper.

- Förhindra dataläckor i intranätet med dataförlustskydd

  Contoso-konfigurerade principer för [skydd mot data förlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) för Exchange Online, SharePoint och OneDrive för företag för att förhindra att användare oavsiktligt eller avsiktligt delar känslig information.

- Förhindra dataläckor på enheter med Windows Information Protection

  Contoso använder [Windows informations skydd (RIA)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) för att skydda mot data läckage via Internet-baserade appar och tjänster och företags program och data på företagsägda enheter och personliga enheter som de anställda kan arbeta med.

- Molnövervakning med Microsoft Cloud App Security

  Contoso använder [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) för att kartlägga molnmiljön, övervaka dess användning och identifiera säkerhetshändelser och incidenter. *Microsoft Cloud App Security är endast tillgängligt med Microsoft 365 E5.*

- Enhetshantering med Microsoft Intune

  Contoso använder [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) för att registrera, hantera och konfigurera åtkomst till mobila enheter och de appar som körs på enheterna. Enhetsbaserade principer för villkorsstyrd åtkomst kräver också godkända appar och kompatibla datorer och mobila enheter.

## <a name="security-management"></a>Säkerhetshantering

- Central säkerhets instrument panel för den med Azure Defender

  Contoso använder [Azure Defender](https://azure.microsoft.com/services/security-center/) för att presentera en enhetlig vy över säkerhets-och hot skydd, för att hantera säkerhets principer för dess arbets belastningar och för att svara på cyberattacks.

- Central säkerhetsinstrumentpanel för användare med Windows Defender Säkerhetscenter

  Contoso distribuerade [säkerhets programmet Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) till sina datorer och enheter som kör Windows 10 Enterprise så att användarna kan se deras säkerhets Posture snabbt och enkelt vidta åtgärder.
