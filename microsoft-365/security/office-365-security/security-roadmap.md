---
title: Säkerhetsfärdkarta för Office 365 – De viktigaste prioriteringarna för de första 30 dagarna, 90 dagarna och därefter
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'De bästa rekommendationerna från Microsofts cybersäkerhetsteam för implementering av säkerhetsfunktioner för att skydda din Office 365-miljö. '
ms.openlocfilehash: c668bb736e6d9f788fe2c54e8a49adbfd4156f43
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811482"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Säkerhetsfärdkarta för Office 365 – De viktigaste prioriteringarna för de första 30 dagarna, 90 dagarna och därefter

Den här artikeln innehåller de vanligaste rekommendationerna från Microsofts cybersäkerhetsteam för implementering av säkerhetsfunktioner för att skydda din Office 365-miljö. Den här artikeln är anpassad från en Microsoft Ignite-session – [Secure Office 365 som ett cybersäkerhetsproffs: Högsta prioritet för de första 30 dagarna, 90 dagarna och därefter](https://www.youtube.com/watch?v=luignzNyR-o). Denna session har utvecklats och presenterats av Mark Simos och Matt Kemelhar, Enterprise Cybersecurity Architects.

I den här artikeln:

- [Resultat av färdplanen](security-roadmap.md#Roadmap)

- [30 dagar – kraftfulla snabba vinster](security-roadmap.md#Thirdaydays)

- [90 dagar – förbättrat skydd](security-roadmap.md#Ninetydays)

- [Bortom](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultat av färdplanen
<a name="Roadmap"> </a>

Dessa färdplansrekommendationer är iscensatta i tre faser i logisk ordning med följande mål.

|||
|:-----|:-----|
| |Resultat
|30 dagar|Snabb konfiguration:  <br/> • Grundläggande admin skydd  <br/> • Loggning och analys  <br/> • Grundläggande identitetsskydd  <br/> Klientkonfiguration  <br/>  Förbereda intressenter|
|90 dagar|Avancerat skydd:  <br/> • Admin konton  <br/>  • &amp; Data användarkonton  <br/>  Insyn i efterlevnad, hot och användarbehov  <br/>  Anpassa och implementera standardprinciper och standardskydd|
|Bortom|Justera och förfina viktiga principer och kontroller  <br/> Utöka skyddet till lokala beroenden  <br/> Integrera med affärs- och säkerhetsprocesser (juridiska, insiderhot, etc.)|



## <a name="30-days--powerful-quick-wins"></a>30 dagar – kraftfulla snabba vinster
<a name="Thirdaydays"> </a>

Dessa uppgifter kan utföras snabbt och har låg inverkan på användarna.

|||
|:-----|:-----|
|Området|Uppgifter|
|Säkerhetshantering|• Kontrollera secure score och notera[https://securescore.office.com](https://securescore.office.com)din nuvarande poäng ( ).  <br/>  • Aktivera granskningsloggning för Office 365. Se [Sök i granskningsloggen](../../compliance/search-the-audit-log-in-security-and-compliance.md).  <br/> • [Konfigurera office 365-klienten för ökad säkerhet](tenant-wide-setup-for-increased-security.md) .  <br/>  • Granska regelbundet instrumentpaneler och rapporter i Microsoft 365-säkerhetscentret och Cloud App Security.|
|Skydd mot hot|[Anslut Office 365 till Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) för att börja övervaka standardprinciperna för identifiering av hot för avvikande beteenden. Det tar sju dagar att skapa en baslinje för avvikelseidentifiering.  <br><br/>  Implementera skydd för administratörskonton:  <br/> • Använd dedikerade administratörskonton för administratörsaktivitet.  <br/>  • Framtvinga MFA (Multi factor Authentication) för administratörskonton.  <br/>  • Använd en [mycket säker Windows 10-enhet](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) för administratörsaktivitet.|
|Hantering av identitet och åtkomst|• [Aktivera Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).  <br/> • För federerade identitetsmiljöer, genomdriva kontosäkerhet (lösenordslängd, ålder, komplexitet, etc.).|
|Informationsskydd| Granska exempel på informationsskyddsrekommendationer. Informationsskydd kräver samordning i hela organisationen. Kom igång med de här resurserna:  <br/> • [Informationsskydd för Office 365 för GDPR](https://aka.ms/o365gdpr) <br/> • [Säkra SharePoint Online-webbplatser och -filer](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) (inkluderar delning, klassificering, dataförlustskydd och Azure Information Protection)|

## <a name="90-days--enhanced-protections"></a>90 dagar – förbättrat skydd
<a name="Ninetydays"> </a>

Dessa uppgifter tar lite mer tid att planera och genomföra men kraftigt öka din säkerhet hållning.

|||
|:-----|:-----|
|Området|Uppgift|
|Säkerhetshantering|• Kontrollera säker poäng för rekommenderade[https://securescore.office.com](https://securescore.office.com)åtgärder för din miljö ( ).  <br/>  • Fortsätt att regelbundet granska instrumentpaneler och rapporter i Microsoft 365-säkerhetscentret, Cloud App Security och SIEM-verktygen. <br/> • Leta efter och implementera programuppdateringar. <br/> • Utför attacksimuleringar för spjut-phishing, lösenordsspray och brute-force lösenordsattacker med [Attack Simulator](attack-simulator.md) (ingår i [Office 365 Threat Intelligence](office-365-ti.md)).  <br/> • Leta efter delningsrisk genom att granska de inbyggda rapporterna i Cloud App Security (på fliken Undersök). <br/> • Kontrollera [efterlevnadspoängen](https://docs.microsoft.com/microsoft-365/compliance/compliance-score) för att granska status för regler som gäller för din organisation (till exempel GDPR, NIST 800-171).|
|Skydd mot hot| Implementera förbättrade skydd för administratörskonton: <br/> • Konfigurera arbetsstationer för [privilegierad åtkomst](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) för administratörsaktivitet. <br/> • Konfigurera [Azure AD-privilegierad identitetshantering](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure). <br/> • Konfigurera ett SIEM-verktyg (Security Information and Event Management) för att samla in loggningsdata från Office 365, Cloud App Security och andra tjänster, inklusive AD FS. I granskningsloggen för Office 365 lagras data i endast 90 dagar. Genom att samla in dessa data i SIEM-verktyget kan du lagra data under en längre period.|
|Hantering av identitet och åtkomst|• Aktivera och genomdriva MFA för alla användare. <br/> • Genomföra en uppsättning [villkorad tillgång och relaterade principer](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Informationsskydd| Anpassa och genomföra informationsskyddsprinciper. Dessa resurser innehåller exempel: <br/> • [Informationsskydd för Office 365 för GDPR](https://aka.ms/o365gdpr) <br/> • [Säkra SharePoint Online-webbplatser och -filer](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> Använd principer för att förhindra dataförlust och övervakningsverktyg i Office 365 för data som lagras i Office 365 (i stället för Cloud App Security). <br><br>Använd Cloud App Security med Office 365 för avancerade varningsfunktioner (förutom dataförlustskydd).|

## <a name="beyond"></a>Bortom
<a name="Beyond"> </a>

Detta är viktiga säkerhetsåtgärder som bygger på tidigare arbete.

|||
|:-----|:-----|
|Området|Uppgift|
|Säkerhetshantering|• Fortsätt planera nästa åtgärd [https://securescore.office.com](https://securescore.office.com)med hjälp av Secure Score ( ). <br/> • Fortsätt att regelbundet granska instrumentpaneler och rapporter i Microsoft 365-säkerhetscentret, Cloud App Security och SIEM-verktygen. <br/> • Fortsätt att leta efter och implementera programuppdateringar. <br/> • Integrera eDiscovery i dina juridiska och hot svar processer.|
|Skydd mot hot|• Implementera säker privilegierad åtkomst (SPA) för [identitetskomponenter](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) i lokala (AD, AD FS). <br/> • Använd Cloud App Security för att övervaka insiderhot. <br/> • Upptäck skugg-IT SaaS-användning med hjälp av Cloud App Security.|
|Hantering av identitet och åtkomst|• Förfina policyer och operativa processer. <br/> • Använd Azure AD Identity Protection för att identifiera insiderhot.|
|Informationsskydd| Förfina informationsskyddsprinciper: <br/> • Microsoft 365 och Office 365 känslighetsetiketter och dataförlustskydd (DLP) eller Azure Information Protection. <br/> • Säkerhetspolicyer och aviseringar för molnappar.|

Se också: [Hur man kan mildra snabba cyberattacker som Petya och WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
