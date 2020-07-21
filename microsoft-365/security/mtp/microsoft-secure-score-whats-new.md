---
title: Nyheter i Microsoft Secure Score
description: I artikeln beskrivs vilka nya ändringar som har hänt microsoft secure score i microsoft 365 security center.
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säker poäng, säkerhetscenter, förbättringsåtgärder
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 4f9f4f40b9cd88cad1676417d467d04367eaa0be
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200170"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Nyheter i Microsoft Secure Score

För att göra Microsoft Secure Score till en bättre representant för din säkerhetsposition har vi gjort vissa ändringar. Mer information om planerade ändringar finns [i Vad som kommer i Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).

## <a name="june-2020"></a>Juni 2020

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Borttagen förbättringsåtgärd för Microsoft Defender Advanced Threat Protection

* Aktivera regler för minskning av attackytan

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Lade till förbättringsåtgärder för Microsoft Defender Advanced Threat Protection

* Blockera Adobe Reader från att skapa underordnade processer
* Använd avancerat skydd mot ransomware
* Blockera alla Office-program från att skapa underordnade processer
* Blockera Office-program från att skapa körbart innehåll
* Blockera JavaScript eller VBScript från att starta nedladdat körbart innehåll
* Blockera körning av potentiellt fördunklade skript
* Blockera körbart innehåll från e-postklient och webbmail
* Blockera Office-kommunikationsprogram från att skapa underordnade processer
* Blockera ej betrodda och osignerade processer som körs från USB
* Blockera persistens genom WMI-händelseprenumeration
* Blockera Office-program från att injicera kod i andra processer
* Blockera körbara filer från att köras om de inte uppfyller ett prevalens-, ålders- eller tillförlitligt listkriterium
* Blockera processskapanden från PSExec- och WMI-kommandon
* Blockera stöld av autentiseringsuppgifter från undersystemet Windows lokala säkerhetsmyndighet (lsass.exe)
* Blockera Win32 API-anrop från Office-makron

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Inkompatibilitet med Identity Secure Score och Graph API

I den senaste versionen av Microsoft Secure Score har en förbättrad poängsättningsmodell släppts. Dessa ändringar möjliggör en mer flexibel och korrekt bild av din säkerhetsposition. Dessa uppdateringar har dock gjort Microsoft Secure Score tillfälligt inkompatibelt med Identity Secure Score och Graph API.

Med tiden antar Identity Secure Score och Graph API den nya bedömningsmodellen. Fram till dess ser kunderna skillnader i poängen som rapporteras av Microsoft Secure Score, Identity Secure Score och Graph API. Vi ber om ursäkt för eventuella besvär detta orsakar, och arbetar för att säkerställa dessa erfarenheter är mer kompatibla i framtiden.

## <a name="updated-improvement-actions"></a>Uppdaterade förbättringsåtgärder

- Lade till förbättringarsåtgärder för Azure Active Directory
- Lade till Azure Advanced Threat Protection improvement-åtgärder
- Stöd för säkerhetsrekommendationer för Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alla utgivna säkerhetsrekommendationer från TVM finns nu tillgängliga

## <a name="updated-interface-and-functionality"></a>Uppdaterat gränssnitt och funktionalitet

* Alla nya statistik- och trendersvyer för CISO- och leadnivådiskussioner
* Nya sätt att spåra och jämföra din poäng
* Bättre spårning och förståelse för poängregressioner
* Filtrera, tagga, söka och gruppera förbättringsåtgärder
* Hantera mot dina framtida mål med hjälp av resultatprognoser och planerade åtgärder
* Och mer!

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har några problem, vänligen meddela oss genom att publicera i [security, privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Vi övervakar samhället och kommer att ge hjälp.

## <a name="related-resources"></a>Relaterade resurser

- [Bedöm din säkerhetsposition](microsoft-secure-score-improvement-actions.md)
- [Spåra din Microsoft Secure Score-historik och uppnå mål](microsoft-secure-score-history-metrics-trends.md)
- [Kommer snart](microsoft-secure-score-whats-coming.md)
