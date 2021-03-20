---
title: Säkerhet och sekretess för Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Lär dig planera för säkerhet och sekretess i Microsoft Viva Topics
ms.openlocfilehash: 9ac7ea085be115ef06244422713099c01ec50a36
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917350"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Säkerhet och sekretess för Microsoft Viva Topics

Ämnen använder befintliga innehållssäkerhetsfunktioner i Microsoft 365, tillsammans med administrativa kontroller, för att styra vilket AI-genererat innehåll som visas för användarna i organisationen. Det är kombinationen av säkerhetsinställningarna för Microsoft 365 (behörigheter till webbplatser, filer och mappar) och administratörsinställningarna för ämnen som bestämmer vad en viss användare kan se i avsnitten.

När du ställer in ämnen ändras inte befintliga åtkomstkontroller för innehåll i din organisation. Användarna kan bara se det som de redan har åtkomst till.

I den här artikeln beskrivs hur ämnen fungerar ur ett säkerhetsperspektiv och de alternativ som kunskapsadministratörer och kunskapshanterare har för att styra synligheten för ämnen. Läs den här artikeln som en del av [planeringen för ämnen](plan-topic-experiences.md).

Du bör känna till [vad Ämnen är](topic-experiences-overview.md), ämnescentret och hur du arbetar med ämnen i ämnescentret [innan](manage-topics.md) du läser den här artikeln. [](topic-center-overview.md)

## <a name="what-users-can-see-in-topics"></a>Vad användarna kan se i avsnitten

För att kunna se avsnitt måste en användare:

- Ha en Viva Topics-licens
- Vara [ämnesläsare,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [deltagare eller knowledge manager](topic-experiences-user-permissions.md)

De här två sakerna ger användarna tillgång till ämnescentret och låter dem se höjdpunkter och ämneskort.

Ämnesdeltagare har dessutom behörighet [att skapa och redigera](topic-experiences-user-permissions.md) för ämnen, och knowledge managers kan bekräfta eller ta bort ämnen.

När ett ämne först upptäcks kan kunskapshanterare se det i ämnescentret. Beroende på ämnets fullständighet och relevans kan det hända att läsarna ser eller inte ser ämnet som presenteras på ämneskorten.

Ämnen kan innehålla information som genereras av AI och information som lagts till eller redigerats av ämnesdeltagare eller kunskapshanterare.

- Information i ett ämne som har lagts till av AI visas bara för personer som har åtkomst till källinnehållet.
- Text som har lagts till manuellt eller redigerats av en ämnesdeltagare eller knowledge manager är synlig för alla som kan se ämnet.

Ämnes läsare och deltagare kan se listan över bekräftade och publicerade ämnen i ämnescentret, men den ämnesinformation som en viss person kan se beror på vilka behörigheter de har till källmaterial och på om ämnet har redigerats manuellt.

I följande tabell beskrivs vad användare – ämnesanvändare, deltagare och kunskapshanterare – kan se i ett visst ämne baserat på deras behörigheter.

|Ämnesobjekt|Vad användarna kan se|
|:---------|:------------------|
|Ämnesnamn|Användarna kan se ämnesnamnet för alla ämnen i ämnescentret. Vissa ämnen kanske inte visas om de har en låg relevans för användaren.|
|Ämnesbeskrivning|AI-genererade beskrivningar visas endast för användare som har behörighet till källinnehållet. Manuellt angivna eller redigerade beskrivningar visas för alla användare.|
|Kontakter|Fästa personer visas för alla användare. Föreslagna personer visas bara för användare som har behörighet till källinnehållet.|
|Filer|Filer visas bara för användare som har behörighet till källinnehållet.|
|Sidor|Sidor visas bara för användare som har behörighet till källinnehållet.|
|Webbplatser|Webbplatser visas bara för användare som har behörighet till källinnehållet.|

## <a name="best-practices"></a>Metodtips

Ämnen presenterar information för användare baserat på deras befintliga behörigheter till innehåll. I Microsoft 365 finns en mängd olika sätt att säkerställa att känsligt innehåll begränsas till rätt användare. Förutom standardbehörigheter för grupp eller webbplats kan du använda [känslighetsetiketter](../compliance/sensitivity-labels.md) eller skydd mot [dataförlust](../compliance/data-loss-prevention-policies.md) för att begränsa åtkomst till innehåll och åtkomstgranskningar för att regelbundet granska användaråtkomst till känslig information. [](/azure/active-directory/governance/access-reviews-overview)

Vi rekommenderar att du använder de här verktygen för att säkerställa att din innehållsbehörighet anges på rätt sätt i din organisation. Ämnesupplevelser kan sedan ge användarna användbar och lämplig information.

Om det finns ämnen som du vill utesluta helt från ämnesupplevelser kan du även:

- [Undanta känsliga SharePoint-webbplatser från identifiering av ämnen.](topic-experiences-discovery.md#select-sharepoint-topic-sources) Innehållet på de här webbplatserna visas inte i ämnesupplevelser.

- [Utesluta ämnen efter namn](topic-experiences-discovery.md#exclude-topics-by-name). Ämnen som uttryckligen utesluts visas inte i ämnesupplevelser.

- Be kunskapschefer ta bort ämnen i ämnescentret.

Dessutom rekommenderar vi följande metodtips:

- Rekrytering av kunskapschefer från olika områden i organisationen. Att ha kunskapschefer med en mängd olika kunskaper – och åtkomst till det underliggande innehåll som används av AI – kan hjälpa dig att hantera de mest användbara kunskaperna för användarna och ta bort känslig information om de hittas.

- Skapa ett arbetsflöde för att begära ändringar. Knowledge managers or team or site owners should have a process by which they can request exclusion of topics or sites as new projects are started within your organization or if they find content with inappropriate permissions settings.

- Var uppmärksam på målgruppen och hur känslig informationen är när du skapar ämnesbeskrivningar. De här beskrivningarna kan visas för användare som inte har behörighet till ämnets källinnehåll.

Du kan ändra behörigheterna på enskilda ämnessidor för att begränsa åtkomsten till en viss grupp användare, men vi rekommenderar inte den här metoden eftersom det krävs mycket administrativt arbete.

## <a name="see-also"></a>Se även

[Konfigurera Teams med tre skyddsnivåer](../solutions/configure-teams-three-tiers-protection.md)

[Planera ämnesupplevelser](plan-topic-experiences.md)

[Konfigurera ämnesupplevelser](set-up-topic-experiences.md)