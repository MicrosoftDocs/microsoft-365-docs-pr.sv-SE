---
title: Utgående skräppostskydd
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om kontrollerna för utgående skräppost i Exchange Online Protection (EOP) och vad de kan göra om du behöver skicka massutskick.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0fb6bfe5d83c551c0a93cc7b453b27a2d7b476bc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538741"
---
# <a name="outbound-spam-protection-in-eop"></a>Skydd mot utgående skräppost i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online postlådor tar vi det allvarliga i hanteringen av utgående skräppost. Även om en kund avsiktligt eller oavsiktligt skickar skräppost från organisationen kan den åtgärden försämra hela tjänstens rykte och påverka e-postleveransen för andra kunder.

I den här artikeln beskrivs de kontroller och meddelanden som är utformade för att förhindra utgående skräppost, och vad du kan göra om du behöver skicka massutskick.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Vad administratörer kan göra för att styra utgående skräppost

- Använda inbyggda meddelanden: När en användare överskrider [](configure-the-outbound-spam-policy.md) gränserna för sändning av tjänsten eller principer för  utgående skräppost och är begränsad från att skicka e-post, skickar standardaviseringsprincipen med namnet Användare begränsad från att skicka **e-post** till medlemmar i **gruppen TenantAdmins** (globala administratörer). [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)  Information om hur du konfigurerar vilka andra som får dessa meddelanden [finns i Kontrollera aviseringsinställningarna för begränsade användare.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Standardprinciperna för avisering med namnet Begränsning för sändning av e-post överskreds och mönster för misstänkta e-postavsändarmeddelanden upptäckte också att skicka e-postmeddelanden till medlemmar i **gruppen TenantAdmins** **(globala** administratörer).   Mer information om aviseringsprinciper finns i [Aviseringsprinciper i Microsoft 365](../../compliance/alert-policies.md).

- Granska skräppostklagomål från tredje parts e-postleverantörer: Många **e-posttjänster** som Outlook.com, Yahoo och AOL ger en feedbackslinga där en användare i sin tjänst markerar ett e-postmeddelande från Microsoft 365 som skräppost och skickas tillbaka till oss för granskning. Mer information om avsändarstöd för Outlook.com finns i <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Hur EOP kontrollerar utgående skräppost

- **Separering av utgående** e-posttrafik: Alla utgående meddelanden som skickas via tjänsten genomsöks efter skräppost. Om meddelandet fastställt vara skräppost, kommer det från en sekundär, mindre känd IP-adresspool som heter _högriskleveranspoolen._ Mer information finns i [Högriskleveranspool för utgående meddelanden.](high-risk-delivery-pool-for-outbound-messages.md)

- **Övervaka vårt rykte för käll-IP-adresser:** Microsoft 365 vi har frågor om olika IP-blockeringslistor från tredje part. En avisering skapas om någon av de IP-adresser som vi använder för utgående e-post visas i dessa listor. Den här kontrollen gör att vi kan reagera snabbt när skräppost har fått vårt rykte att försämras. När en avisering skapas har vi intern dokumentation som beskriver hur du kan ta bort (avlistade) IP-adresser från blockeringslistor.

- **Inaktivera konton** som skickar för mycket skräppost : Även om vi delar upp utgående skräppost i högriskleveranspoolen kan vi inte tillåta att ett konto (ofta ett komprometterat konto) skickar skräppost på obestämd <sup>\*</sup> tid. Vi övervakar konton som skickar skräppost, och när de överskrider en gräns för oupptäckta meddelanden blockeras kontot från att skicka e-post. Det finns olika tröskelvärden för enskilda användare och hela klientorganisationen.

- **Inaktivera konton** som skickar för mycket e-post för snabbt: Utöver de begränsningar som gäller för meddelanden som markeras som skräppost finns det också begränsningar som blockerar konton när de når en gräns för övergripande utgående meddelanden, oavsett vilket skräppostfiltreringsval som gäller för utgående <sup>\*</sup> meddelanden. Ett komprometterat konto kan skicka skräppost som inte har använts på noll dagar och som missas av skräppostfiltret. Eftersom det kan vara svårt att identifiera en legitim massutskickskampanj jämfört med en skräppostkampanj hjälper de här begränsningarna till att minimera potentiella skador.

<sup>\*</sup> Vi annonserar inte de exakta gränserna så skräppostavs spammare kan inte spela systemet, och därför kan vi öka eller minska gränserna efter behov. Gränserna är tillräckligt stora för att hindra en genomsnittlig företagsanvändare från att någonsin överskrida dem, och tillräckligt låga för att hjälpa till att begränsa skada som en spammare orsakar.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Rekommendationer för kunder som vill göra massutskick via EOP

Det är svårt att skapa balans mellan kunder som vill skicka en stor mängd e-post i förhållande till att skydda tjänsten från komprometterade konton och massutskick av avsändare med dåliga metoder för mottagarköp. Kostnaden för en e Microsoft 365 postkälla som ligger på en IP-blockeringslista från tredje part är större än att blockera en användare som skickar för mycket e-post.

Enligt beskrivningen i [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)Tjänstbeskrivning stöds inte användning av tjänsten med EOP för att skicka massutskick och tillåts endast med "bästa möjliga"- användning. För kunder som vill skicka massutskick rekommenderar vi följande lösningar:

- **Skicka massutskick via lokala e-postservrar:** Kunderna har en egen e-postinfrastruktur för massutskick.

- **Använda en tredjepartsleverantör för** massutskick: Det finns flera tredjepartsleverantörer av massutskick som du kan använda för att skicka massutskick. De här företagen har ett intresse av att arbeta med kunder för att säkerställa bra e-postskick.

Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publicerar sin medlemsförteckning på <https://www.maawg.org/about/roster> . Flera stora mängder e-postleverantörer finns med i listan och kan vara ansvariga för internetmeddelare.
