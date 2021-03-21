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
ms.openlocfilehash: 8e87f4625e48024cd217ba5c33d345c2422f109c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920330"
---
# <a name="outbound-spam-protection-in-eop"></a>Skydd mot utgående skräppost i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor ser vi allvarligt på hanteringen av utgående skräppost. En kund som avsiktligt eller oavsiktligt skickar skräppost från sin organisation kan försämra ryktet för hela tjänsten, och kan påverka e-postleveransen för andra kunder.

I det här avsnittet beskrivs de kontroller och meddelanden som är utformade för att förhindra utgående skräppost, och vad du kan göra om du behöver skicka massutskick.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Vad administratörer kan göra för att styra utgående skräppost

- Använda inbyggda meddelanden: När en användare överskrider [](configure-the-outbound-spam-policy.md) gränserna för sändning av tjänsten eller principer för  utgående skräppost och är begränsad från att skicka e-post, skickar standardaviseringsprincipen med namnet Användare begränsad från att skicka **e-post** till medlemmar i **gruppen TenantAdmins** (globala administratörer). [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)  Information om hur du konfigurerar vilka andra som får dessa meddelanden [finns i Kontrollera aviseringsinställningarna för begränsade användare.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Standardprinciperna för avisering med namnet Begränsning för sändning av e-post överskreds och mönster för misstänkta e-postavsändarmeddelanden upptäckte också att skicka e-postmeddelanden till medlemmar i **gruppen TenantAdmins** **(globala** administratörer).   Gå till [Varningsregler i Säkerhets- och efterlevnadscentret](../../compliance/alert-policies.md) om du vill ha mer information om varningsprinciper.

- Granska **skräppostklagomål** från tredje parts e-postleverantörer : Många e-posttjänster som Outlook.com, Yahoo och AOL ger en feedbackloop där en användare i sin tjänst markerar ett e-postmeddelande från Microsoft 365 som skräppost, så att meddelandet paketeras och skickas tillbaka till oss för granskning. Mer information om avsändarsupport för Outlook.com finns i <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Hur EOP kontrollerar utgående skräppost

- **Separering av utgående** e-posttrafik: Alla utgående meddelanden som skickas via tjänsten genomsöks efter skräppost. Om meddelandet fastställt vara skräppost, kommer det från en sekundär, mindre känd IP-adresspool som heter _högriskleveranspoolen._ Mer information finns i [Högriskleveranspool för utgående meddelanden.](high-risk-delivery-pool-for-outbound-messages.md)

- **Övervaka vårt rykte för käll-IP-adresser:** Microsoft 365 frågar om olika ip-blockeringslistor från tredje part. En avisering skapas om någon av de IP-adresser som vi använder för utgående e-post visas i dessa listor. Det här gör att vi kan reagera snabbt när skräppost har fått vårt rykte att försämras. När en avisering skapas har vi intern dokumentation som beskriver hur du kan ta bort (avlistade) IP-adresser från blockeringslistor.

- **Inaktivera konton** som skickar för mycket skräppost : Även om vi delar upp utgående skräppost i högriskleveranspoolen kan vi inte tillåta att ett konto (ofta ett komprometterat konto) skickar skräppost på obestämd <sup>\*</sup> tid. Vi övervakar konton som skickar skräppost, och när de överskrider en gräns för oupptäckta meddelanden blockeras kontot från att skicka e-post. Det finns olika tröskelvärden för enskilda användare och hela klientorganisationen.

- **Inaktivera konton** som skickar för mycket e-post för snabbt: Utöver de begränsningar som gäller för meddelanden som markeras som skräppost finns det också begränsningar som blockerar konton när de når en gräns för övergripande utgående meddelanden, oavsett vilket skräppostfiltreringsval som gäller för utgående <sup>\*</sup> meddelanden. Ett komprometterat konto kan skicka skräppost som inte har använts på noll dagar och som missas av skräppostfiltret. Eftersom det kan vara svårt att identifiera en legitim massutskickskampanj jämfört med en skräppostkampanj hjälper de här begränsningarna till att minimera potentiella skador.

<sup>\*</sup> Vi annonserar inte de exakta gränserna så skräppostavs spammare kan inte spela systemet, och därför kan vi öka eller minska gränserna efter behov. Gränserna är tillräckligt stora för att hindra en genomsnittlig företagsanvändare från att någonsin överskrida dem, och tillräckligt låga för att hjälpa till att begränsa skada som en spammare orsakar.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Rekommendationer för kunder som vill göra massutskick via EOP

Det är svårt att skapa balans mellan kunder som vill skicka en stor mängd e-post i förhållande till att skydda tjänsten från komprometterade konton och massutskick av avsändare med dåliga metoder för mottagarköp. Kostnaden för en Microsoft 365-e-postkälla som ligger på en tredje parts IP-blockeringslista är större än att blockera en användare som skickar för mycket e-post.

Enligt beskrivningen i [Tjänstbeskrivning](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)för Exchange Online stöds inte användningen av tjänsten med EOP för att skicka massutskick, och tillåts endast med "bästa möjliga"-användning. För kunder som vill skicka massutskick rekommenderar vi följande lösningar:

- **Skicka massutskick via lokala e-postservrar**: Det innebär att kunderna måste ha en egen e-postinfrastruktur för massutskick.

- **Använda en tredjepartsleverantör för massutskick:** Det finns flera tredjepartsleverantörer av massutskick som du kan använda för att skicka massutskick. De här företagen har ett intresse av att arbeta med kunder för att säkerställa bra e-postskick.

Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publicerar sin medlemsförteckning på <https://www.maawg.org/about/roster> . Flera stora mängder e-postleverantörer finns med i listan och kan vara ansvariga för internetmeddelare.