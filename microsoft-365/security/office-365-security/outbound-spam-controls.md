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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa om utgående skräp post kontroller i Exchange Online Protection (EOP) och vad du kan göra om du behöver skicka mass utskick.
ms.openlocfilehash: 1097b768b955f2fa99c552ceda7564bef33a1aa7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202393"
---
# <a name="outbound-spam-protection-in-eop"></a>Utgående skräp post skydd i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kan vi hantera utgående skräp post. En kund som avsiktligt eller oavsiktligt skickar skräp post från sin organisation kan försämra tjänstens rykte och kan påverka e-postleveransen för andra kunder.

I det här avsnittet beskrivs de kontroller och meddelanden som är avsedda att förhindra utgående skräp post och vad du kan göra om du behöver skicka mass utskick.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Vilka administratörer kan göra för att kontrol lera utgående skräp post

- **Använda inbyggda aviseringar**: när en användare överskrider begränsningen för [tjänsten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) eller [utgående skräp post principer](configure-the-outbound-spam-policy.md) och begränsas från att skicka e-post skickar e-postaviseringar till medlemmar i gruppen **TenantAdmins** (**globala administratörer**) till användare som är **begränsade** till att skicka e-post. Information om hur du konfigurerar vilka andra som får dessa meddelanden finns i [Verifiera aviserings inställningarna för användare med begränsad åtkomst](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Dessutom är standard principerna för meddelanden om att **skicka e-post överskridit** och **misstänkt e-post skickar mönster** för att skicka e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**globala administratörer**). Gå till [Varningsregler i Säkerhets- och efterlevnadscentret](../../compliance/alert-policies.md) om du vill ha mer information om varningsprinciper.

- **Granska skräp inlägg från tredje part e-postleverantörer**: många e-posttjänster som Outlook.com, Yahoo och AOL ger en feedback om en användare i sin tjänst markerar ett e-postmeddelande från Microsoft 365 som skräp post, så paketeras meddelandet och skickas tillbaka till oss för granskning. Om du vill veta mer om stöd för avsändare för Outlook.com går du till <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Så här styr EOP utgående skräp post

- **Åtskillnad av utgående e-posttrafik**: alla utgående meddelanden som skickas via tjänsten avsöks för skräp post. Om meddelandet identifieras som skräp post skickas det från en sekundär, mindre känd IP-adresspool som heter _högrisk leverans_. Mer information finns i [poolen högrisk leveranser för utgående meddelanden](high-risk-delivery-pool-for-outbound-messages.md).

- **Övervakning av Källans IP-adress rykte**: Microsoft 365 frågar om olika IP-listor från tredje part. En avisering genereras om någon av de IP-adresser som används för utgående e-post visas i dessa listor. Detta gör att vi kan reagera snabbt när skräp posten har orsakat att vårt rykte försämras. När en avisering genereras innehåller vi intern dokumentation som visar hur du får upp våra IP-adresser (avlistaade) från blockeringslistan.

- **Inaktivera konton som skickar för mycket skräp post** <sup>\*</sup> : även om vi angriper utgående skräp post i poolen med högrisk samtal, kan vi inte tillåta att ett konto (oftare) skickar skräp post. Vi övervakar konton som skickar skräp post och när de överskrider en icke offentliggjord begränsning hindras kontot från att skicka e-post. Det finns olika tröskelvärden för enskilda användare och hela innehavaren.

- **Inaktivera konton som skickar för mycket e-post för snabbt** <sup>\*</sup> : utöver de begränsningar som gäller för meddelanden som marker ATS som skräp post är det också begränsningar för att blockera konton när de når en total gräns för utgående meddelanden, oberoende av skräp post filtrering Verdict för utgående meddelanden. Ett komprometterat konto kan skicka noll (tidigare okänd) skräp post som missas av skräp post filtret. Eftersom det kan vara svårt att identifiera en legitim Mass utskick av e-post jämfört med en spams kampanj kan de här gränserna minimera eventuella potentiella skador.

<sup>\*</sup> Vi annonserar inte de exakta gränserna så att skräp post systemen inte kan spela det och så kan vi öka eller minska gränserna när så behövs. Gränserna är tillräckligt höga för att förhindra att en genomsnittlig företags användare någonsin överskrider dem och är tillräckligt liten för att hjälpa till att få den skada som orsakas av skräp post.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Rekommendationer för kunder som vill skicka mass utskick genom EOP

Det är svårt att göra en avvägning mellan kunder som vill skicka en stor mängd e-post eller att skydda tjänsten från intrång i konton och Mass utskick via e-post med hjälp av dålig mottagnings metod. Kostnaden för en Microsoft 365-e-postkälla från tredje part är större än att blockera en användare som skickar för mycket e-post.

Enligt beskrivningen i [tjänst beskrivningen för Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)kan du inte använda EOP för att skicka mass utskick och får bara en "bästa ansträngning". För kunder som vill skicka mass utskick via e-post rekommenderar vi följande:

- **Skicka mass utskick via e-post via lokala e-postservrar**: det innebär att kunder måste ha sina egna e-postinfrastrukturer för utskick.

- **Använd en tredjeparts Mass utskick av e-** post: du kan skicka mass utskick via e-post från tredje part. Dessa företag har fått en intresse rad av att arbeta med kunderna för att säkerställa god sändning av e-post.

Arbets gruppen för meddelanden, mobiler, skadlig program vara (MAAWG) publicerar sin medlemskaps lista på <https://www.maawg.org/about/roster> . Flera e-postleverantörer finns på listan och är kända för att vara ansvariga för Internet.
