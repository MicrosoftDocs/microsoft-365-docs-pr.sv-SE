---
title: Utvärdera din säkerhetsposition via Microsoft Secure Score
description: I artikeln beskrivs hur du vidtar åtgärder för att förbättra Microsoft Secure Score i microsoft 365-säkerhetscentret.
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
ms.openlocfilehash: 469056bbae4627e0b013bfc0f2e965586fd15175
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200068"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Utvärdera din säkerhetsposition med Microsoft Secure Score

Microsoft Secure Score är ett mått på en organisations säkerhetsposition, med ett högre antal som anger fler förbättringsåtgärder som vidtas. Den finns https://security.microsoft.com/securescore på i Microsoft [365 security center](overview-security-center.md).

För att hjälpa dig den information du behöver snabbare är Microsofts förbättringsåtgärder organiserade i grupper:

* Identitet (Azure AD-konton & roller)
* Data (Microsofts informationsskydd)
* Enhet (Microsoft Defender ATP, känd som [konfigurationspoäng)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score)
* App (e-post- och molnappar, inklusive Office 365 och Microsoft Cloud App Security)
* Infrastruktur (inga förbättringsåtgärder för tillfället)

>[!NOTE]
>I den senaste versionen av Microsoft Secure Score har en förbättrad poängsättningsmodell släppts som gjorde Microsoft Secure Score tillfälligt inkompatibelt med Identity Secure Score och Graph API. [Visa information](microsoft-secure-score-whats-new.md)

På översiktssidan för Microsoft Secure Score kan du se hur poäng delas mellan dessa grupper och vilka punkter som är tillgängliga. Översiktssidan är också platsen för att få en helhetsbild av den totala poängen, historisk trend för din säkra poäng med jämförelsemål och prioriterade förbättringsåtgärder som kan vidtas för att förbättra din poäng.

![Startsida för säkra poäng](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Kontrollera din aktuella poäng

Om du vill kontrollera din aktuella poäng går du till översiktssidan för Microsoft Secure Score och letar efter panelen där det står **Din säkra poäng**. Din poäng kommer att visas i procent, tillsammans med antalet poäng du har uppnått av totalt möjliga poäng.

Om du väljer knappen **Inkludera** bredvid din poäng kan du dessutom välja olika vyer av dina poäng. Dessa olika poängvyer visas i diagrammet på poängpanelen och punktfördelningsdiagrammet.

Följande är poäng som du kan lägga till i din syn på din totala poäng för att ge dig en fylligare bild av din totala poäng:

- **Planerad poäng:** Visa beräknad poäng när planerade åtgärder slutförs
- **Aktuell licenspoäng:** Visa poäng som kan uppnås med din nuvarande Microsoft-licens
- **Uppnåelig poäng:** Visa poäng som kan uppnås med dina Microsoft-licenser och nuvarande riskacceptans

Så här kommer det att se ut om du har inkluderat alla möjliga poängvyer:

![Din säkra poäng inklusive planerad poäng, aktuell licenspoäng och uppnåelig poäng](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Vidta åtgärder för att förbättra din poäng

På fliken **Förbättringsåtgärder** visas de säkerhetsrekommendationer som åtgärdar möjliga angreppsytor, tillsammans med deras status (för att ta itu med, planerade, risk accepterade, lösas via tredje part, lösas genom alternativ begränsning och slutförd). Du kan söka, filtrera och gruppera alla förbättringsåtgärder.  

### <a name="ranking"></a>Ranking (ranking)

Rankningen baseras på antalet återstående poäng kvar att uppnå, implementeringssvårigheter, användarpåverkan och komplexitet. De högst rankade förbättringsåtgärderna har ett stort antal punkter kvar med låg svårighet, användarpåverkan och komplexitet.

### <a name="view-improvement-action-details"></a>Visa information om förbättringsåtgärder

När du väljer en viss förbättringsåtgärd visas ett utfällbart utfällbart helsidesutfällbart resultat.  

![Utfällbart exempel på förbättringsåtgärd ](../../media/secure-score/secure-score-improvement-action-details.png)
 *Bild 2: Exempel på utfällbara förbättringar*

För att slutföra åtgärden har du några alternativ:

* Välj **Hantera** om du vill gå till konfigurationsskärmen och göra ändringen. Du kommer då att få de poäng som åtgärden är värd, synlig i flyga ut. Poäng tar i allmänhet ca 24 timmar att uppdatera.

* Välj **Dela** om du vill kopiera den direkta länken till förbättringsåtgärden eller välj den plattform som du vill dela länken som e-post, Microsoft Teams, Microsoft Planner eller ServiceNow. Genom att välja ServiceNow kan du skapa en ändringsbiljett som visas i ServiceNow och Microsoft 365 security center home. Mer information finns i [Microsoft 365 security center och ServiceNow-integrering](tickets-security-center.md).

### <a name="choose-an-improvement-action-status"></a>Välj status för förbättringsåtgärder

Välj alla statusar och spela in anteckningar som är specifika för förbättringsåtgärden. De statyer du kan välja är följande:

* **För att ta itu med** - Du inser att förbättringen åtgärder är nödvändiga och planerar att ta itu med det någon gång i framtiden. Det här tillståndet gäller även åtgärder som identifieras som delvis, men inte helt slutförda.
* **Planerad** – Det finns konkreta planer för att slutföra förbättringsåtgärderna.
* **Risk accepteras** - Säkerhet bör alltid balanseras med användbarhet, och inte varje rekommendation kommer att fungera för din miljö. När så är fallet kan du välja att acceptera risken, eller den återstående risken, och inte anta förbättringsåtgärden. Du kommer inte att få några poäng, men åtgärden kommer inte längre att vara synlig i listan över förbättringsåtgärder. Du kan visa den här åtgärden i historiken eller ångra den när som helst.
* **Löst via tredje part** och **löst genom alternativ begränsning** – Förbättringsåtgärden har redan åtgärdats av ett program eller program från tredje part, eller ett internt verktyg. Du kommer att få de poäng som åtgärden är värd, så din poäng bättre återspeglar din totala säkerhet hållning. Om en tredje part eller ett internt verktyg inte längre täcker kontrollen kan du välja en annan status. Tänk på att Microsoft inte har någon insyn i implementeringens fullständighet om förbättringsåtgärden markeras som någon av dessa statusar.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Åtgärder för förbättring av hot & sårbarhetshantering

För förbättringsåtgärder i kategorin "Enhet" kan du inte välja status. I stället dirigeras du till den tillhörande [& säkerhetsproblemshantering (TVM) i](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) för att vidta åtgärder. Det undantag du väljer och motiveringen som du skriver är specifikt för portalen och finns inte på portalen Microsoft Secure Score.

#### <a name="completed-improvement-actions"></a>Slutförda förbättringsåtgärder

Förbättringsåtgärder har en "slutförd" status när alla möjliga punkter för förbättringsåtgärderna har uppnåtts. Slutförda förbättringsåtgärder bekräftas genom Microsoft-data och du kommer inte att kunna ändra status.

### <a name="assess-information-and-review-user-impact"></a>Utvärdera information och granska användarnas påverkan

I avsnittet **Vid en överblick** visas kategorin, attacker som den kan skydda mot och produkten.

**Användareffekten** visar vad användarna kommer att uppleva om förbättringsåtgärden har antagits och **användare som påverkas** visar vem som kommer att uppleva det.

### <a name="implement-the-improvement-action"></a>Genomföra förbättringsåtgärderna

Avsnittet **Implementering** visar eventuella förutsättningar, steg för steg nästa steg för att slutföra förbättringsåtgärden, den aktuella implementeringsstatusen för förbättringsåtgärden och eventuella fler länkar.

Förutsättningar kommer att vara alla licenser som måste erhållas eller åtgärder som måste slutföras innan förbättringsåtgärden åtgärdas. Se till att du har tillräckligt med platser i din licens för att slutföra förbättringsåtgärden och att dessa licenser tillämpas på nödvändiga användare.  

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har några problem, vänligen meddela oss genom att publicera i [security, privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Vi övervakar samhället och kommer att ge hjälp.

## <a name="related-resources"></a>Relaterade resurser

- [Översikt över Microsoft Secure Score](microsoft-secure-score.md)
- [Spåra din Microsoft Secure Score-historik och uppnå mål](microsoft-secure-score-history-metrics-trends.md)
- [Kommer snart](microsoft-secure-score-whats-coming.md)
- [Nyheter](microsoft-secure-score-whats-new.md)