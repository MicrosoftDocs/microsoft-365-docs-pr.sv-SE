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
description: Administratörer kan lära sig mer om kontrollerna för utgående skräppost i Exchange Online Protection (EOP) och vad de kan göra om du behöver göra massutskick.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f9d434c858f7c66f82dd4f551bac99458b9e5c8c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287635"
---
# <a name="outbound-spam-protection-in-eop"></a>Skydd mot utgående skräppost i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor tar vi den utgående skräpposten på största allvar. En kund som avsiktligt eller oavsiktligt skickar skräppost från sin organisation kan försämra ryktet för hela tjänsten, och kan påverka e-postleveransen för andra kunder.

I det här avsnittet beskrivs de kontroller och meddelanden som är utformade för att förhindra utgående skräppost, och vad du kan göra om du behöver skicka massutskick.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Vad administratörer kan göra för att kontrollera utgående skräppost

- Använd inbyggda meddelanden: När en användare [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) överskrider sändningsgränserna för tjänsten eller principer för utgående  skräppost och är begränsad från att skicka e-post, skickar standardaviseringsprincipen med namnet Användare begränsad från att skicka **e-postmeddelanden** till medlemmar i gruppen Global **Admins** **(TenantAdmins).** [](configure-the-outbound-spam-policy.md) Information om hur du konfigurerar vilka andra som får dessa meddelanden finns i [Verifiera aviseringsinställningarna för begränsade användare.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Standardaviseringsprinciperna för  e-postavsändargräns har överskridits och avsändarmönster för misstänkta e-postmeddelanden har **upptäckts** för att skicka e-postmeddelanden till medlemmar i **gruppen TenantAdmins** **(globala** administratörer). Gå till [Varningsregler i Säkerhets- och efterlevnadscentret](../../compliance/alert-policies.md) om du vill ha mer information om varningsprinciper.

- Granska **skräppostklagomål** från tredje parts e-postleverantörer: Många e-posttjänster som Outlook.com, Yahoo och AOL ger en feedbackslinga där en användare i sin tjänst markerar ett e-postmeddelande från Microsoft 365 som skräppost, så att meddelandet paketeras och skickas tillbaka till oss för granskning. Mer information om avsändarstöd för Outlook.com finns <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> i.

## <a name="how-eop-controls-outbound-spam"></a>Hur EOP kontrollerar utgående skräppost

- **Separering av utgående** e-posttrafik : Alla utgående meddelanden som skickas via tjänsten genomsöks efter skräppost. Om meddelandet har fastställt att det är skräppost, levereras det från en sekundär, mindre känd IP-adresspool med namnet _högriskleveranspoolen._ Mer information finns i [högriskleveranspool för utgående meddelanden.](high-risk-delivery-pool-for-outbound-messages.md)

- **Övervaka vårt rykte för käll-IP-adressen**: Microsoft 365 frågar olika IP-blockeringslistor från tredje part. En avisering genereras om någon av de IP-adresser som vi använder för utgående e-post visas på dessa listor. Det här gör att vi snabbt kan reagera när skräppost har fått vårt rykte att försämras. När en avisering skapas finns det intern dokumentation som beskriver hur du tar bort våra IP-adresser (avlistade) från blockeringslistor.

- **Inaktivera konton** som skickar för mycket skräppost : Även om vi delar upp utgående skräppost i högriskleveranspoolen kan vi inte tillåta att ett konto (ofta ett komprometterat konto) skickar skräppost på obestämd <sup>\*</sup> tid. Vi övervakar konton som skickar skräppost och när de överskrider en gräns för dataidentifiering blockeras kontot från att skicka e-post. Det finns olika tröskelvärden för enskilda användare och hela klientorganisationen.

- **Inaktivera konton** som skickar för mycket e-post för snabbt: Förutom de begränsningar som gäller för meddelanden som markeras som skräppost finns det också begränsningar som blockerar konton när de når en övergripande gräns för utgående meddelanden, oavsett skräppostfiltrering för utgående <sup>\*</sup> meddelanden. Ett komprometterat konto kan skicka skräppost utan dag (tidigare okänd) som missas av skräppostfiltret. Eftersom det kan vara svårt att identifiera en legitim massutskickskampanj jämfört med en skräppostkampanj hjälper de här begränsningarna till att minimera potentiella skador.

<sup>\*</sup> Vi annonserar inte de exakta gränserna så skräppostavs skräppostavs så att de inte kan spela systemet, och vi kan öka eller minska gränserna efter behov. Gränserna är tillräckligt stora för att hindra en genomsnittlig företagsanvändare från att någonsin överskrida dem, och tillräckligt låga för att hjälpa till att begränsa de skador en spammare orsakar.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Rekommendationer för kunder som vill göra massutskick via EOP

Det är svårt att skapa balans mellan kunder som vill skicka en stor mängd e-post och att skydda tjänsten från komprometterade konton och massutskick av e-post med dåliga metoder för mottagarköp. Kostnaden för att en Microsoft 365-e-postkälla landar på en blockeringslista från tredje part är större än att blockera en användare som skickar för mycket e-post.

Enligt beskrivningen i [tjänstbeskrivningen för Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)stöds inte användningen av tjänsten med EOP för att skicka massutskick, och den tillåts endast med "bästa möjliga" användning. För kunder som vill skicka massutskick rekommenderar vi följande lösningar:

- **Skicka massutskick via lokala e-postservrar:** Det innebär att kunderna måste ha en egen e-postinfrastruktur för massutskick.

- **Använd en tredjepartsleverantör för massutskick:** Det finns flera tredjepartsleverantörer av massutskick som du kan använda för massutskick. Dessa företag har ett intresse av att arbeta med kunder för att säkerställa bra metoder för att skicka e-post.

Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publicerar sin medlemsförteckning <https://www.maawg.org/about/roster> på. Flera massutskick finns med på listan och är kända för att vara ansvariga internetmederare.
