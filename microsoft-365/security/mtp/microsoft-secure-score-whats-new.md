---
title: Nyheter i Microsofts säkra Poäng
description: Här beskrivs vilka nya ändringar som har hänt för säkert Poäng i Microsoft 365 säkerhets Center.
keywords: Microsoft säkra poäng, säkra poäng, Office 365 säkra poäng, Microsoft-säkerhet, Microsoft 365 säkerhets Center
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
ms.openlocfilehash: 4b25f701aca24563dc4f1a15f78a80e1e2064367
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604389"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Nyheter i Microsofts säkra Poäng

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Vi har gjort några ändringar för att göra Microsoft säkert poäng en bättre representant för dina säkerhets Posture. Om du vill veta mer om planerade ändringar kan du läsa [vad som kommer i Microsofts säkra Poäng?](microsoft-secure-score-whats-coming.md)

Microsoft Secure score finns https://security.microsoft.com/securescore i [Microsoft 365 Security Center](overview-security-center.md).

## <a name="november-2020"></a>November 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Tog bort möjligheten att skapa ServiceNow biljetter genom säkra Poäng 

Möjligheten att skapa ServiceNow biljetter genom säkra poäng genom att gå till **dela > ServiceNow** är inte längre tillgänglig. Tack för din feedback och fortsatta support medan vi bestämmer nästa steg.

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>3 tjänster-relaterade förbättrings åtgärder för Microsoft Defender för slut punkten (tidigare Microsoft Defender ATP):

- Åtgärda den icke-citerade tjänst Sök vägen för Windows-tjänster
- Ändra sökvägen till den körbara filen till en gemensam skyddad plats
- Ändra tjänst konto för att undvika cachelagrat lösen ord i Windows-registret

## <a name="october-2020"></a>Oktober 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Ta bort förbättrings åtgärd relaterad till Microsoft Defender för slut punkt

- Ange webb innehålls kontroll för Windows Store-appen för Microsoft Defender SmartScreen

## <a name="august-2020"></a>Augusti 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Uppdaterad förbättrings åtgärd för Azure Active Directory

- Aktivera princip för blockering av bakåtkompatibel-verifikation

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Inkompatibilitet med identitets säkra poäng-och diagram-API

I den senaste versionen av Microsofts säkra poäng är en förbättrad Poäng modell släppt. Dessa ändringar ger en mer flexibel och korrekt översikt av dina säkerhets Posture. Men de här uppdateringarna har gjort Microsoft säker Poäng tillfälligt inkompatibelt med identitets säkra poäng och diagram-API.

I tid kommer identitets säkra poäng och Graph API att anta den nya bedömnings modellen. Till dess kommer kunderna att se skillnaderna i resultaten som rapporter ATS av säkra poäng, identitets säkra poäng och diagram-API. Vi ber om ursäkt för eventuella besvär som det här orsakar och arbetar för att säkerställa att dessa upplevelser är mer kompatibla i framtiden.

## <a name="updated-improvement-actions"></a>Uppdaterade förbättrings åtgärder

- Åtgärder för Azure Active Directory-förbättring har lagts till
- Microsoft Defender för förbättrings åtgärder har lagts till
- Stöd för Microsoft Defender för att skydda slut punkter [&](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) säkerhets rekommendationer
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
