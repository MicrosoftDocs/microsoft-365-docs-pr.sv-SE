---
title: Microsoft 365 säkerhets plan – främsta prioriteringar
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
description: 'Rekommendationer från Microsofts Cybersecurity-team för implementering av säkerhetsfunktioner för att skydda din Microsoft 365-miljö. '
ms.openlocfilehash: d62db9206a98078ae5adaad220a7c9b53ff116cd
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561705"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Säkerhets plan – de främsta prioriteringarna för de första 30 dagarna, 90 dagar och senare

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I den här artikeln finns rekommendationer från Microsofts Cybersecurity-team för implementering av säkerhetsfunktioner för att skydda din Microsoft 365-miljö. Den här artikeln är anpassad från en Microsoft-session- [säkra Microsoft 365 som en Cybersecurity Pro: Top prioriteringar för de första 30 dagarna, 90 dagar och senare](https://www.youtube.com/watch?v=luignzNyR-o). Denna session har utvecklats och presenter ATS av mark Simos och Matt Kemelhar, Enterprise Cybersecurity Architects.

I den här artikeln:

- [Översikts resultat](security-roadmap.md#Roadmap)
- [30 dagar – kraftfull snabb WINS](security-roadmap.md#Thirdaydays)
- [90 dagar – bättre skydd](security-roadmap.md#Ninetydays)
- [Mottagning](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Översikts resultat
<a name="Roadmap"> </a>

Dessa rekommendationer är mellanliggande i tre faser i en logisk ordning med följande mål.

****

|Tidsram|Resultat|
|---|---|
|30 dagar|Snabb konfiguration: <ul><li>Grundläggande administratörs skydd.</li><li>Loggning och analys.</li><li>Grundläggande identitets skydd.</li></ul> <p> Klient konfiguration. <p> Förbereda intressenterna.|
|90 dagar|Avancerade skydd: <ul><li>Administratörs konton.</li><li>Data-och användar konton.</li></ul> <p> Synlighet för efterlevnad, hot och användar behov. <p> Anpassa och implementera standard principer och skydd.|
|Mottagning|Justera och finslipa viktiga principer och kontroller. <p> Utöka skydd till lokala beroenden. <p> Integrera med affärs-och säkerhets processer (juridik, Insider Threat etc.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 dagar – kraftfull snabb WINS
<a name="Thirdaydays"> </a>

Dessa uppgifter kan utföras snabbt och ha nedsatt påverkan till användarna.

****

|Under|Uppgifter|
|---|---|
|Säkerhetshantering|<ul><li>Kontrol lera säkerhets poängen och ta del av ditt aktuella poäng ( <https://securescore.office.com> ).</li><li>Aktivera gransknings loggning för Office 365. Se [söka i gransknings loggen](../../compliance/search-the-audit-log-in-security-and-compliance.md).</li><li>[Konfigurera Microsoft 365 för ökad säkerhet](tenant-wide-setup-for-increased-security.md).</li><li>Granska regelbundet instrument paneler och rapporter i säkerhets Center för Microsoft 365 och Cloud App Security.</li></ul>|
|Skydd mot hot|[Anslut microsoft 365-säkerheten till Microsoft Cloud App-säkerhet](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) för att börja övervaka användning av standard principer för hot identifiering för avvikande beteenden. Det tar sju dagar att bygga en bas linje för avvikelse identifiering. <p>  Implementera skydd för administratörs konton:<ul><li>Använd dedikerade administratörs konton för administratörs aktivitet.</li><li>Påtvinga multifaktorautentisering (MFA) för administratörs konton.</li><li>Använd en [mycket säker Windows 10-enhet](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) för administratörs aktivitet.</li></ul>|
|Identitets- och åtkomsthantering|<ul><li>[Aktivera Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)-kryptering.</li><li>För federerade identitets miljöer bör du använda konto säkerhet (lösen ord längd, ålder, komplexitet osv.).</li></ul>|
|Informationsskydd|Granska exempel på informations skydds rekommendationer. Informations skydd kräver samordning i hela organisationen. Kom igång med de här resurserna:<ul><li>[Informationsskydd för Office 365 för GDPR](https://aka.ms/o365gdpr)</li><li>[Konfigurera Teams med tre olika skydds nivåer](../../solutions/configure-teams-three-tiers-protection.md) (inklusive delning, klassificering, skydd mot data förlust och Azure information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 dagar – bättre skydd
<a name="Ninetydays"> </a>

Dessa uppgifter tar lite längre tid att planera och implementera men det ökar sedan avsevärt Posture.

****

|Under|Uppgift|
|---|---|
|Säkerhetshantering|<ul><li>Kontrol lera säkerhets poängen för rekommenderade åtgärder för din miljö ( [https://securescore.office.com](https://securescore.office.com) ).</li><li>Fortsätt att regelbundet granska instrument paneler och rapporter 365 i säkerhets Center, Cloud App-säkerhet och SIEM verktyg.</li><li>Leta efter och implementera program uppdateringar.</li><li>Utför angrepps simuleringar för Spear – nätfiske, lösen ords skydd och angrepp med [angrepps Simulator](attack-simulator.md) (ingår i [Office 365 Threat Intelligence](office-365-ti.md)).</li><li>Leta efter risk för delning genom att granska de inbyggda rapporterna i Cloud App Security (på fliken Undersök).</li><li>Kontrol lera status för reglerna som gäller för din organisation (till exempel GDPR, NIST 800-171) genom att granska [överensstämmelse hanteraren](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager) .</li></ul>|
|Skydd mot hot|Implementera utökade skydd för administratörs konton: <ul><li>Konfigurera [behöriga åtkomst arbets stationer](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) för administratörs aktivitet.</li><li>Konfigurera [Azure AD-privilegie rad identitets hantering](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Konfigurera ett verktyg för säkerhets information och Event Management (SIEM) för insamling av loggnings data från Office 365, Cloud App Security och andra tjänster, inklusive AD FS. I gransknings loggen lagras data för endast 90 dagar. Om du fångar in dessa data i SIEM-verktyget kan du lagra data under en längre tid.</li></ul>|
|Identitets- och åtkomsthantering|<ul><li>Aktivera och verkställa MFA för alla användare.</li><li>Implementera en uppsättning [villkor för villkorsstyrd åtkomst och relaterade principer](microsoft-365-policies-configurations.md).</li></ul>|
|Informationsskydd| Anpassa och implementera principer för informations skydd. De här resurserna innehåller exempel: <ul><li>[Informationsskydd för Office 365 för GDPR](https://aka.ms/o365gdpr)</li><li>[Konfigurera Teams med tre skyddsnivåer](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Använd principer för data förlust skydd och övervaknings verktyg i Microsoft 365 för data som lagrats i Microsoft 365 (istället för Cloud App Security). <p> Använd Cloud App Security med Microsoft 365 för avancerade aviserings funktioner (annat än förhindra data förlust).|
|

## <a name="beyond"></a>Mottagning
<a name="Beyond"> </a>

Det här är viktiga säkerhets åtgärder som bygger på tidigare arbete.

****

|Under|Uppgift|
|---|---|
|Säkerhetshantering|<ul><li>Fortsätt planera nästa åtgärd genom att använda säker Poäng ( <https://securescore.office.com> ).</li><li>Fortsätt att regelbundet granska instrument paneler och rapporter 365 i säkerhets Center, Cloud App-säkerhet och SIEM verktyg.</li><li>Fortsätt leta efter och implementera program uppdateringar.</li><li>Integrera eDiscovery i dina process processer för juridiska och hot.</li></ul>|
|Skydd mot hot|<ul><li>Implementera [Secure privilegie rad åtkomst](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (Spa) för identitets komponenter lokalt (AD FS).</li><li>Använd Cloud App Security för att övervaka Insider hot.</li><li>Upptäck skugg programmet SaaS med hjälp av Cloud App Security.</li></ul>|
|Identitets- och åtkomsthantering|<ul><li>Förfina principer och operativa processer.</li><li>Använd Azure AD Identity Protection för att identifiera Insider-hot.</li></ul>|
|Informationsskydd|Förfina informations skydds principer: <ul><li>Microsoft 365-och Office 365-känslighets etiketter och data förlust skydd (DLP) eller Azure information Protection.</li><li>Cloud App-säkerhets principer och-varningar.</li></ul>|
|

Se även: [så här minskar du snabba cyberattacks som Petya och WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
