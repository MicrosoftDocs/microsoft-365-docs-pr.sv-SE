---
title: Utvärdera dina säkerhets Posture via Microsofts säkra Poäng
description: Här beskrivs hur du utför en åtgärd för att förbättra dina säkra Microsoft-poäng i säkerhets Center för Microsoft 365.
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
ms.openlocfilehash: 3b913b3d53abf8c46fbcc9e053f91f512864c9d8
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315837"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Utvärdera dina säkerhets Posture med Microsofts säkra Poäng

Microsoft Secure score är ett mått på en organisations säkerhets Posture, med ett högre nummer som indikerar fler förbättrings åtgärder. Den finns https://security.microsoft.com/securescore i [säkerhets Center för Microsoft 365](overview-security-center.md).

För att hjälpa dig att hitta den information du behöver snabbare är Microsoft Improvement åtgärder ordnade i grupper:

* Identitet (Azure Active Directory-konton & roller)
* Data (Microsoft Information Protection)
* Enhet (Microsoft Defender ATP, kallas [Microsofts säkra Poäng för enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))
* App (e-post och Cloud-appar, inklusive Office 365 och Microsoft Cloud App Security)
* Infrastruktur (inga förbättrings åtgärder)

>[!NOTE]
>I den senaste versionen av Microsofts säkra poäng har en förbättrad beräknings modell släppts som gjorde den tillfälligt inkompatibel med identitets säkra poäng och diagram-API: t. [Visa information](microsoft-secure-score-whats-new.md)

På sidan Microsofts säkra Poäng översikt kan du se hur Poäng delas mellan dessa grupper och vilka Poäng som är tillgängliga. Du kan också få en hel del av den totala poängen, historisk trenden för dina säkra poäng med benchmark-jämförelser och prioriterade förbättrings åtgärder som kan vidtas för att förbättra din poäng.

![Säkra Poäng start sidan](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Kontrol lera aktuell Poäng

Om du vill kontrol lera din aktuella poäng går du till sidan Microsoft-översikt över säkra poäng och letar efter brickan med **din säkra Poäng**. Poängen visas som en procents ATS, tillsammans med antalet poäng som du har uppnått av totalt antal möjliga poäng.

Om du väljer knappen **Inkludera** bredvid poängen kan du välja olika vyer för poängen. De här vyerna visas i diagrammet på Poäng panelen och diagrammet med punkt diagram.

Här följer resultat som du kan lägga till i din vy av total poängen för att ge dig en fullständig bild av ditt totala poäng värde:

- **Planerat Poäng**: Visa projektschemat när planerade åtgärder är klara
- **Aktuell licens Poäng**: Visa poängen som kan uppnås med din nuvarande Microsoft-licens
- **Möjlig Poäng**: Visa poängen som kan uppnås med Microsoft-licenser och nuvarande risk godkännande

Den här vyn ser ut om du har inkluderat alla möjliga åsikter:

![Din säkra Poäng inklusive planerat poäng, aktuell licens Poäng och möjligt Poäng](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Vidta åtgärder för att förbättra din Poäng

På fliken **förbättrings åtgärder** visas de säkerhets rekommendationer som kan användas för att hantera möjliga attacker. Det inkluderar också deras status (till adress, planerad, risk som accepterats av tredje part, löst via annan åtgärd och ifylld). Du kan söka, filtrera och gruppera alla förbättringar.  

### <a name="ranking"></a>Ranknings

Rangordning baseras på antalet Points kvar för att uppnå, implementera problem, användar påverkan och komplexitet. De högsta åtgärderna för bättre rangordning har ett stort antal Points kvar med nedsatt syn, användar påverkan och komplexitet.

### <a name="view-improvement-action-details"></a>Visa information om förbättrings åtgärder

När du väljer en särskild förbättrings åtgärd visas en hel sida med utfällbar text.  

![Förbättrings instruktionen utfälld exempel ](../../media/secure-score/secure-score-improvement-action-details.png)
 *figur 2: förbättrings åtgärd utfällbar exempel*

Om du vill slutföra åtgärden har du några alternativ:

* Välj **Hantera** för att gå till sidan konfiguration och göra ändringen. Då får du de punkter som åtgärden är värd för, synlig i flyg ut. Det tar vanligt vis ungefär 24 timmar att uppdatera det.

* Välj **dela** för att kopiera den direkta länken till förbättrings åtgärden. Du kan också välja plattformen för att dela länken, till exempel e-post, Microsoft Teams, Microsoft Planner eller ServiceNow. Om du väljer ServiceNow kan du skapa en ändrings biljett som visas i ServiceNow och Microsoft 365 Security Center Home. Mer information finns i [Microsoft 365 Security Center och ServiceNow integration](tickets-security-center.md).

### <a name="choose-an-improvement-action-status"></a>Välj en förbättrings åtgärds status

Välj status och anteckningar för förbättrings åtgärden.

- **Adress** – du känner igen att förbättrings åtgärden är nödvändig och att du planerar att adressera den vid något tillfälle i framtiden. Det här läget gäller även för åtgärder som identifieras som delvis men inte fullständigt slutförda.
- **Planerat** – det finns konkreta planer för att slutföra förbättrings åtgärden.
- **Risk accepterad** – säkerheten bör alltid bal anse ras och inte varje rekommendation fungera för din miljö. I så fall kan du välja att acceptera risken, eller den återstående risken, och inte vidta förbättrings åtgärden. Du får inga poäng, men åtgärden kommer inte längre att synas i listan över förbättrings åtgärder. Du kan visa den här åtgärden i historik eller när som helst.
- **Löstes genom tredje part** och **löses genom den alternativa begränsningen** -åtgärden har redan åtgärd ATS av ett tredjepartsprogram eller program vara från tredje part, eller ett internt verktyg. Du får de punkter som åtgärden är värd för, så din poäng bättre återspeglar ditt totala säkerhets Posture. Om en tredje part eller ett internt verktyg inte längre täcker kontrollen kan du välja en annan status. Kom ihåg att Microsoft inte har någon insyn i fullständig implementering om förbättrings åtgärden är markerad som någon av dessa status värden.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Hot & sårbarhet för hanterings förbättring

För förbättrings åtgärder i kategorin "enhet" kan du inte välja status. I stället dirigeras du om till den associerade [Threat & säkerhets rekommendation för hantering (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) i [Microsoft Defender säkerhets Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) för att vidta åtgärder. Det undantag du väljer och motivering du skriver är specifikt för den portalen. Det finns inte på Microsofts säkra Poäng-Portal.

#### <a name="completed-improvement-actions"></a>Slutförda förbättrings åtgärder

Förbättrings åtgärder har statusen "slutfört" när alla möjliga poäng för förbättrings åtgärden har uppnåtts. Slutförda förbättrings åtgärder bekräftas, men du kommer inte att kunna ändra den.

### <a name="assess-information-and-review-user-impact"></a>Utvärdera information och granska användar påverkan

I det avsnitt som heter kan du berätta för dig kategorin, angripna den **för** att skydda mot och produkten.

**Användarens påverkan** visar vad användarna kommer att uppleva om förbättrings åtgärden utförs, och användare som **påverkas** av din upplevelse.

### <a name="implement-the-improvement-action"></a>Implementera förbättrings åtgärden

I **implementerings** avsnittet visas eventuella förutsättningar för att förbättra förbättrings åtgärden, steg för steg-steg och anvisningar för förbättrings åtgärden.

Förutsättningar innehåller alla licenser som måste erhållas eller åtgärder som måste slutföras innan förbättrings åtgärden åtgärdas. Kontrol lera att du har tillräckligt många platser i din licens för att slutföra förbättrings åtgärden och att dessa licenser tillämpas på de användare som behövs.  

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har några problem kan du meddela oss genom att publicera det i [säkerhets-, integritets &](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Vi övervakar communityn och ger hjälp.

## <a name="related-resources"></a>Relaterade resurser

- [Översikt över Microsofts säkra Poäng](microsoft-secure-score.md)
- [Spåra din Microsoft säkra Poäng historik och uppfylla målen](microsoft-secure-score-history-metrics-trends.md)
- [Kommer snart](microsoft-secure-score-whats-coming.md)
- [Vad är det senaste](microsoft-secure-score-whats-new.md)