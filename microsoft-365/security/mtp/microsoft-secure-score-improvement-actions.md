---
title: Utvärdera säkerheten genom Microsoft Secure Score
description: Här beskrivs hur du kan vidta åtgärder för att förbättra Microsoft Secure Score i Säkerhetscenter för Microsoft 365.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8cf416e773abc6cbe1fd891fcec9f02a5011c413
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930648"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Utvärdera din säkerhetssäkerhet med Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score är ett mått på en organisations säkerhetssäkerhet, med ett högre tal som anger fler förbättringsåtgärder som vidtas. Den finns på Microsoft https://security.microsoft.com/securescore [365 säkerhetscenter.](overview-security-center.md)

För att hjälpa dig att få den information du behöver snabbare är Microsofts förbättringsåtgärder organiserade i grupper:

* Identitet (Azure Active Directory-konton & roller)
* Enhet (Microsoft Defender för Slutpunkt, som kallas [Microsoft Secure Score för enheter)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)
* App (e-post och molnprogram, inklusive Office 365 och Microsoft Cloud App Security)

>[!NOTE]
>I den senaste versionen av Microsoft Secure Score har en förbättrad poängmodell släppts som gjort Microsoft Secure Score tillfälligt inkompatibelt med Identity Secure Score och Graph API. [Visa information](microsoft-secure-score-whats-new.md)

På översiktssidan i Microsoft Secure Score kan du se hur punkterna är uppdelade mellan grupperna och vilka poäng som är tillgängliga. Du kan också få en fullständig bild av totalresultatet, en historisk trend av säker poäng med jämförelse av prestandavärden och prioriterade förbättringsåtgärder som kan vidtas för att förbättra ditt resultat.

![Startsida för Secure Score](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Kontrollera ditt aktuella poängresultat

Om du vill kontrollera ditt aktuella resultat går du till översiktssidan för Microsoft Secure Score och letar efter panelen där det står **Ditt säkra resultat.** Poängen visas som en procentsats, tillsammans med antalet poäng du har uppnått av det totala antalet möjliga poäng.

Om du väljer knappen **Inkludera** bredvid resultatet kan du dessutom välja olika vyer av resultatet. De här olika poängvyerna visas i diagrammet på panelen poäng och i punktfördelningsdiagrammet.

Följande är resultat som du kan lägga till i vyn över ditt övergripande resultat för att ge dig en mer fullständig bild av helhetsresultatet:

- **Planerat resultat:** Visa projekterat resultat när planerade åtgärder har slutförts
- **Aktuellt licensresultat:** Visa poäng som kan uppnås med din nuvarande Microsoft-licens
- **Uppnåbart resultat: Visa** poäng som kan uppnås med dina Microsoft-licenser och aktuellt riskgodkännande

Den här vyn ser ut så här om du har tagit med alla möjliga poängvyer:

![Ditt säkra resultat, inklusive planerat poäng, aktuellt licensresultat och uppnåbart resultat](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Vidta åtgärder för att förbättra ditt resultat

Fliken **För förbättringsåtgärder** innehåller säkerhetsrekommendationer som åtgärdar möjliga attackytor. Den omfattar även deras status (för att hantera, planerade, godkända risker, lösas genom tredje part, lösas genom alternativ minskning och slutföras). Du kan söka, filtrera och gruppera alla förbättringsåtgärder.  

### <a name="ranking"></a>Rangordning

Rangordningen baseras på antalet punkter som återstår att uppnå, implementeringssvårigheter, påverkan på användare och komplexitet. De högst rankade förbättringsåtgärderna har ett stort antal punkter kvar med låg komplexitet, påverkan på användare och komplexitet.

### <a name="view-improvement-action-details"></a>Visa information om åtgärder för förbättring

När du väljer en specifik förbättringsåtgärd visas en fullständig sida.  

![Utfällt exempel på åtgärd för förbättring](../../media/secure-score/secure-score-improvement-action-details.png)

Det finns några alternativ för att slutföra åtgärden:

- Välj **Hantera** för att gå till konfigurationsskärmen och göra ändringen. Du får sedan de poäng som åtgärden är värd, synlig i flyg ut. Det brukar ta ungefär 24 timmar innan poäng har uppdaterats.

- Välj **Dela** för att kopiera direktlänken till förbättringsåtgärden. Du kan också välja plattformen för att dela länken, till exempel e-post, Microsoft Teams, Microsoft Planner eller ServiceNow. Om du väljer ServiceNow kan du skapa en ändrings biljett som visas i ServiceNow och på startsidan för Säkerhetscenter för Microsoft 365. Mer information finns i [Microsoft 365 säkerhetscenter och ServiceNow-integrering.](tickets-security-center.md)

Lägg **till anteckningar** för att hålla reda på förloppet eller något annat du vill kommentera. Om du lägger till egna **taggar** i förbättringsåtgärden kan du filtrera efter de taggarna.

### <a name="choose-an-improvement-action-status"></a>Välj status för en förbättringsåtgärd

Välj valfri status och spela in anteckningar som är specifika för förbättringsåtgärden.

- **För att** åtgärda – du känner igen att förbättringsåtgärden är nödvändig och planerar att åtgärda den vid något tillfälle i framtiden. Det här läget gäller även för åtgärder som identifieras som delvis, men inte helt slutförda.
- **Planerat** – Det finns betongplaner för att slutföra förbättringsåtgärden.
- **Accepterad** risk – Säkerheten bör alltid balanseras med användbarheten och alla rekommendationer fungerar inte för din miljö. När så är fallet kan du välja att acceptera risken eller den återstående risken och inte vidta någon förbättringsåtgärd. Du får inga poäng, men åtgärden visas inte längre i listan över förbättringsåtgärder. Du kan visa den här åtgärden i historiken eller ångra den när som helst.
- **Löst via tredje part** **och Löst** genom alternativ minskning - förbättringsåtgärden har redan åtgärdats av ett program eller en programvara från tredje part eller ett internt verktyg. Du får poäng som åtgärden är värd så att poängen bättre speglar den övergripande säkerhetsåtgärden. Om ett tredjepartsverktyg eller ett internt verktyg inte längre täcker kontrollen kan du välja en annan status. Kom ihåg att Microsoft inte har någon insyn i implementeringens fullständighet om förbättringsåtgärden markeras som någon av dessa statusar.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Åtgärder & för att förbättra säkerhetshanteringen

För förbättringsåtgärder i kategorin "Enhet" kan du inte välja status. I stället hänvisas du till [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) rekommendationen om hantering av hot och sårbarhetssäkerhet i [Microsoft Defender Säkerhetscenter för](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) att vidta åtgärder. Det undantag som du väljer och justering som du skriver kommer att vara specifikt för den portalen. Den finns inte i Microsoft Secure Score-portalen.

#### <a name="completed-improvement-actions"></a>Slutförda förbättringsåtgärder

Förbättringsåtgärder har statusen "slutförd" när alla möjliga punkter för förbättringsåtgärden har uppnåtts. Slutförda förbättringsåtgärder bekräftas via Microsoft-data och du kan inte ändra status.

### <a name="assess-information-and-review-user-impact"></a>Utvärdera information och granska användarnas påverkan

I avsnittet med **en kort översikt** får du veta kategorin, attacker den kan skydda mot och produkten.

**Användar påverkan** är vad användarna kommer att uppleva om  förbättringsåtgärden vidtas och användare som påverkas är de personer som kommer att påverkas.

### <a name="implement-the-improvement-action"></a>Implementera förbättringsåtgärden

**Implementeringsavsnittet** visar eventuella krav, stegvisa nästa steg för att slutföra förbättringsåtgärden, aktuell implementeringsstatus för förbättringsåtgärden och eventuella ytterligare länkar.

Förutsättningarna är bland annat de licenser som krävs eller åtgärder som ska slutföras innan förbättringsåtgärden åtgärdas. Se till att du har tillräckligt med platser i licensen för att slutföra förbättringsåtgärden och att licenserna tillämpas på de nödvändiga användarna.  

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har problem kan du meddela oss genom att publicera i [communityn för säkerhet, & sekretess och](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) efterlevnad. Vi övervakar communityn och hjälper till.

## <a name="related-resources"></a>Relaterade resurser

- [Översikt över Microsoft Secure Score](microsoft-secure-score.md)
- [Spåra din Microsoft Secure Score-historik och uppfylla mål](microsoft-secure-score-history-metrics-trends.md)
- [Kommer snart](microsoft-secure-score-whats-coming.md)
- [Nyheter](microsoft-secure-score-whats-new.md)
