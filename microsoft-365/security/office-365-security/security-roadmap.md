---
title: Microsoft 365 säkerhetsöversikt – främsta prioriteringar
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: De viktigaste rekommendationerna från Microsofts team för cybersäkerhet för att implementera säkerhetsfunktioner för att skydda din Microsoft 365 miljö.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05ea4103abecb10d4eedddf8d5043e339b58804c
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083158"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Säkerhetsöversikt – Högsta prioritet de första 30 dagarna, 90 dagarna och därefter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Den här artikeln innehåller rekommendationer från Microsofts team för cybersäkerhet för att införa säkerhetsfunktioner för att skydda din Microsoft 365 miljö. Den här artikeln är en omarbetad från Microsoft Ignite-session – Secure [Microsoft 365 like a cybersecurity pro: Top priorities for the first 30 days, 90 days, and beyond](https://www.youtube.com/watch?v=luignzNyR-o). Den här sessionen utvecklades och presenterades av Mark Simos och Matt Kemelhar, Enterprise Cybersecurity Architects.

I den här artikeln:

- [Översiktsresultat](security-roadmap.md#Roadmap)
- [30 dagar – kraftfulla snabbvinst](security-roadmap.md#Thirdaydays)
- [90 dagar – bättre skydd](security-roadmap.md#Ninetydays)
- [Vidare](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Översiktsresultat
<a name="Roadmap"> </a>

Rekommendationerna i översikten följer tre faser i en logisk ordning med följande mål.

****

|Tidsram|Resultat|
|---|---|
|30 dagar|Snabb konfiguration: <ul><li>Grundläggande administratörsskydd.</li><li>Loggning och analys.</li><li>Grundläggande identitetsskydd.</li></ul> <p> Klientorganisationskonfiguration. <p> Förbered intressenter.|
|90 dagar|Avancerade skydd: <ul><li>Administratörskonton.</li><li>Data och användarkonton.</li></ul> <p> Insyn i efterlevnad, hot och användarbehov. <p> Anpassa och implementera standardprinciper och skydd.|
|Vidare|Justera och förfina viktiga principer och kontroller. <p> Utöka skyddet till lokala beroenden. <p> Integrera med affärs- och säkerhetsprocesser (juridiska, insider hot osv.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 dagar – kraftfulla snabbvinst
<a name="Thirdaydays"> </a>

De här uppgifterna kan utföras snabbt och påverkar användarna lite.

****

|Område|Uppgifter|
|---|---|
|Säkerhetshantering|<ul><li>Kontrollera Secure Score och notera ditt aktuella poängresultat ( <https://securescore.office.com> ).</li><li>Aktivera granskningsloggning för Office 365. Mer [information finns i Söka i granskningsloggen](../../compliance/search-the-audit-log-in-security-and-compliance.md).</li><li>[Konfigurera Microsoft 365 för ökad säkerhet](tenant-wide-setup-for-increased-security.md).</li><li>Regelbundet granska instrumentpaneler och rapporter på Microsoft 365 Defender och Cloud App Security.</li></ul>|
|Skydd mot hot|[Anslut Microsoft 365 att Microsoft Cloud App Security](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) att börja övervaka med standardprinciper för identifiering av hot för avvikelser. Det tar sju dagar att skapa en baslinje för avvikande identifiering. <p>  Implementera skydd för administratörskonton:<ul><li>Använd dedikerade administratörskonton för administratörsaktivitet.</li><li>Tillämpa multifaktorautentisering (MFA) för administratörskonton.</li><li>Använd en [mycket säker Windows 10 enhet](/windows-hardware/design/device-experiences/oem-highly-secure) för administratörsaktivitet.</li></ul>|
|Identitets- och åtkomsthantering|<ul><li>[Aktivera Azure Active Directory identitetsskydd](/azure/active-directory/active-directory-identityprotection-enable).</li><li>För federerade identitetsmiljöer tillämpar du kontosäkerhet (lösenordslängd, ålder, komplexitet osv.).</li></ul>|
|Informationsskydd|Granska exempelrekommendationer om informationsskydd. Informationsskydd kräver koordination i hela organisationen. Kom igång med de här resurserna:<ul><li>[Informationsskydd för Office 365 för GDPR](/compliance/regulatory/gdpr)</li><li>[Konfigurera Teams med tre nivåer av skydd](../../solutions/configure-teams-three-tiers-protection.md) (inklusive delning, klassificering, skydd mot dataförlust och Azure Information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 dagar – bättre skydd
<a name="Ninetydays"> </a>

De här uppgifterna tar lite mer tid att planera och implementera men ökar säkerheten mycket.

****

|Område|Uppgift|
|---|---|
|Säkerhetshantering|<ul><li>Kontrollera Secure Score för rekommenderade åtgärder för din miljö ( <https://securescore.office.com> ).</li><li>Fortsätt att regelbundet granska instrumentpaneler och rapporter i Microsoft 365 Defender, Cloud App Security och SIEM-verktyg.</li><li>Sök efter och implementera programvaruuppdateringar.</li><li>Genomför attack simuleringar för nätfiske, lösenordsskydd och råstyrt lösenordsattacker med hjälp av utbildning av attack simulering [(ingår](attack-simulation-training.md) [i Office 365 Threat Intelligence](office-365-ti.md)).</li><li>Leta efter delningsrisker genom att granska de inbyggda Cloud App Security (på fliken Granska).</li><li>Kontrollera [efterlevnadshanteraren](../../compliance/compliance-manager.md) för att granska status för bestämmelser som gäller för din organisation (till exempel GDPR, NIST 800-171).</li></ul>|
|Skydd mot hot|Implementera förbättrade skydd för administratörskonton: <ul><li>Konfigurera [arbetsstationer för privilegierad](/security/compass/privileged-access-devices) åtkomst (PAWs) för administratörsaktivitet.</li><li>Konfigurera [Azure AD-Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Konfigurera ett säkerhetsinformations- och händelsehanteringsverktyg (SIEM) för att samla in loggningsdata från Office 365, Cloud App Security och andra tjänster, inklusive AD FS. I granskningsloggen lagras data endast i 90 dagar. Genom att samla in dessa data i SIEM-verktyget kan du lagra data under en längre period.</li></ul>|
|Identitets- och åtkomsthantering|<ul><li>Aktivera och tillämpa MFA för alla användare.</li><li>Implementera en uppsättning [villkorsstyrda åtkomst och relaterade principer.](microsoft-365-policies-configurations.md)</li></ul>|
|Informationsskydd| Anpassa och implementera informationsskyddsprinciper. Dessa resurser innehåller exempel: <ul><li>[Informationsskydd för Office 365 för GDPR](/compliance/regulatory/gdpr)</li><li>[Konfigurera Teams med tre skyddsnivåer](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Använd principer för skydd mot dataförlust och övervakningsverktyg i Microsoft 365 för data som lagras i Microsoft 365 (i stället för Cloud App Security). <p> Använd Cloud App Security med Microsoft 365 för avancerade aviseringsfunktioner (annat än skydd mot dataförlust).|
|

## <a name="beyond"></a>Vidare
<a name="Beyond"> </a>

Det här är viktiga säkerhetsåtgärder som bygger på tidigare arbete.

****

|Område|Uppgift|
|---|---|
|Säkerhetshantering|<ul><li>Fortsätt planera nästa åtgärder med hjälp av Secure Score ( <https://securescore.office.com> ).</li><li>Fortsätt att regelbundet granska instrumentpaneler och rapporter i Microsoft 365 Defender, Cloud App Security och SIEM-verktyg.</li><li>Fortsätt att söka efter och implementera programvaruuppdateringar.</li><li>Integrera eDiscovery i dina processer för juridiska åtgärder och hot.</li></ul>|
|Skydd mot hot|<ul><li>Implementera [säker behörighet för åtkomst](/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) för identitetskomponenter lokalt (AD, AD FS).</li><li>Använd Cloud App Security att övervaka insider hot.</li><li>Upptäck skuggad IT SaaS-användning med hjälp av Cloud App Security.</li></ul>|
|Identitets- och åtkomsthantering|<ul><li>Förfina principer och driftsprocesser.</li><li>Använd Azure AD Identity Protection för att identifiera Insider-hot.</li></ul>|
|Informationsskydd|Förfina principer för informationsskydd: <ul><li>Microsoft 365 och Office 365 känslighetsetiketter och skydd mot dataförlust (DLP) eller Azure Information Protection.</li><li>Cloud App Security principer och aviseringar.</li></ul>|
|

Se även: [Hur du minimerar snabba cyberattacker som Petya och WannaCrypt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
