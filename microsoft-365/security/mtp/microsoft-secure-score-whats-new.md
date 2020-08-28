---
title: Nyheter i Microsofts säkra Poäng
description: Här beskrivs vilka nya ändringar som har hänt för säkert Poäng i Microsoft 365 säkerhets Center.
keywords: säkerhet, skadlig program vara, Microsoft 365, M365, säker poäng, säkerhets Center, förbättrings åtgärder
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
ms.openlocfilehash: 8b0fda2d8a0b7d9cb6b2c6a4cca2e8e34a876fec
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289429"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Nyheter i Microsofts säkra Poäng

Vi har gjort några ändringar för att göra Microsoft säkert poäng en bättre representant för dina säkerhets Posture. Om du vill veta mer om planerade ändringar kan du läsa [vad som kommer i Microsofts säkra Poäng?](microsoft-secure-score-whats-coming.md).

## <a name="august-2020"></a>Augusti 2020

### <a name="update-improvement-action-for-azure-active-directory"></a>Uppdaterings åtgärd för Azure Active Directory

- Aktivera princip för blockering av bakåtkompatibel-verifikation

## <a name="july-2020"></a>Juli 2020

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a>Lägga till förbättrings åtgärder för avancerat Azure-skydd

- Sido rörelse banor
- Oskyddade objektattribut
- Aktivera säkerhetsfunktioner för Active Directory-förtroenden
- Ta bort attribut för osäkra SID-historik från enheter

## <a name="june-2020"></a>Juni 2020

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Åtgärd för förbättring av Microsoft Defender Avancerat skydd

* Aktivera regler för reducering av attack ytan

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Förbättrade förbättrings åtgärder för Microsoft Defender Avancerat skydd

* Blockera Adobe Reader från att skapa underordnade processer
* Använd avancerat skydd mot utpressnings tro Jan
* Blockera alla Office-program från att skapa underordnade processer
* Blockera Office-program från att skapa körbart innehåll
* Blockera java script eller VBScript från att starta hämtat körbart innehåll
* Blockera körning av potentiellt Obfuscated-skript
* Blockera körbart innehåll från e-postklient och WebPost
* Blockera Office-kommunikationsprogram från att skapa underordnade processer
* Blockera icke-betrodda och osignerade processer som körs från USB
* Blockera beständighet via WMI-prenumeration
* Blockera Office-program från att injicera kod i andra processer
* Blockera körbara filer från att köras såvida de inte uppfyller villkoren för ett förekomst-, ålder eller betrott lista
* Blockera skapande av processer från PSExec-och WMI-kommandon
* Blockera autentiseringsuppgifter som stjäls från Windows Local Security Authority Subsystem (lsass.exe)
* Blockera Win32 API-samtal från Office-makron

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Inkompatibilitet med identitets säkra poäng-och diagram-API

I den senaste versionen av Microsofts säkra poäng är en förbättrad Poäng modell släppt. Dessa ändringar ger en mer flexibel och korrekt översikt av dina säkerhets Posture. Men de här uppdateringarna har gjort Microsoft säker Poäng tillfälligt inkompatibelt med identitets säkra poäng och diagram-API.

I tid kommer identitets säkra poäng och Graph API att anta den nya bedömnings modellen. Till dess kommer kunderna att se skillnaderna i resultaten som rapporter ATS av säkra poäng, identitets säkra poäng och diagram-API. Vi ber om ursäkt för eventuella besvär som det här orsakar och arbetar för att säkerställa att dessa upplevelser är mer kompatibla i framtiden.

## <a name="updated-improvement-actions"></a>Uppdaterade förbättrings åtgärder

- Åtgärder för Azure Active Directory-förbättring har lagts till
- Förbättrade åtgärder för förbättring av integritets skydd för Azure
- Stöd för Microsoft Defender ATP- [&](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) säkerhets rekommendationer
    - Alla publicerade säkerhets rekommendationer från TVM är nu tillgängliga

## <a name="updated-interface-and-functionality"></a>Uppdaterat gränssnitt och funktioner

* Alla nya mått och trender för diskussioner på CISO och lead-nivå
* Nya sätt att spåra och mäta Poäng
* Bättre spårning och förståelse för resultat regressioner
* Filtrera, tagga, söka och gruppera dina förbättrings åtgärder
* Hantera dina framtida mål med Poäng prognoser och planerade åtgärder
* Och mer!

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har några problem kan du meddela oss genom att publicera det i [säkerhets-, integritets &](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Vi övervakar communityn och ger hjälp.

## <a name="related-resources"></a>Relaterade resurser

- [Utvärdera säkerhets genom övergå molnet](microsoft-secure-score-improvement-actions.md)
- [Spåra din Microsoft säkra Poäng historik och uppfylla målen](microsoft-secure-score-history-metrics-trends.md)
- [Kommer snart](microsoft-secure-score-whats-coming.md)
