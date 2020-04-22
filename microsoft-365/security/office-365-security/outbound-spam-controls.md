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
description: Administratörer kan lära sig mer om hur Microsoft 365 och Exchange Online Protection (EOP) skyddar kunder från utgående skräppost och vad du kan göra om du behöver skicka massutskick.
ms.openlocfilehash: 71fe5d5ba1ffbecc77b646a06c3da4d9681ee3ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634502"
---
# <a name="outbound-spam-protection"></a>Utgående skräppostskydd

Vi tar hanteringen av utgående skräppost på allvar, eftersom Microsoft 365 (Exchange Online eller fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor) är en onlinetjänst där många kunder använder en delad resurspool. En Microsoft 365-kund som avsiktligt eller oavsiktligt skickar skräppost från sin organisation kan försämra hela tjänstens rykte och kan påverka e-postleveransen för andra kunder.

I det här avsnittet beskrivs de kontroller och meddelanden som är utformade för att förhindra skräppost och vad du kan göra om du behöver skicka massutskick.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Vad administratörer kan göra för att kontrollera utgående skräppost

- **Använd inbyggda meddelanden:** När en användare överskrider sändningsgränserna för [tjänsten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) eller [utgående skräppostprinciper](configure-the-outbound-spam-policy.md) och är begränsad från att skicka e-post, skickar standardaviseringsprincipen **användaren begränsad från att skicka e-postmeddelanden** till medlemmar i gruppen **TenantAdmins** (**Global admins**). Information om hur du konfigurerar vem som tar emot dessa meddelanden finns i [Verifiera aviseringsinställningarna för begränsade användare](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Standardvarningsprinciperna **e-postöverföringsgränsen överskreds** och **misstänkta e-postsändningsmönster som upptäckts** skicka e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**Global admins**). Gå till [Varningsregler i Säkerhets- och efterlevnadscentret](../../compliance/alert-policies.md) om du vill ha mer information om varningsprinciper.

- **Granska spam klagomål från tredje part e-postleverantörer:** Många e-posttjänster som Outlook.com, Yahoo och AOL ger en feedback loop där om någon användare i sin tjänst markerar ett e-postmeddelande från Microsoft 365 som spam, meddelandet är förpackat upp och skickas tillbaka till oss för granskning. Mer information om avsändande support för <https://sendersupport.olc.protection.outlook.com/pm/services.aspx>Outlook.com finns i .

## <a name="how-eop-controls-outbound-spam"></a>Så här styr EOP utgående skräppost

- **Segregering av utgående e-posttrafik:** Varje utgående meddelande som skickas via tjänsten genomsöks efter skräppost. Om meddelandet är fast beslutet att vara skräppost levereras det från en sekundär, mindre ansedd IP-adresspool med namnet _högriskleveranspoolen_. Mer information finns i [Högriskleveranspool för utgående meddelanden i Office 365](high-risk-delivery-pool-for-outbound-messages.md).

- **Övervakning av vår källa IP-adress rykte:** Microsoft 365 frågor olika tredje part IP-block listor. En avisering genereras om någon av de IP-adresser som vi använder för utgående e-post visas i dessa listor. Detta gör det möjligt för oss att reagera snabbt när spam har orsakat vårt rykte att försämras. När en avisering genereras har vi intern dokumentation som beskriver hur vi får våra IP-adresser bort (avlistade) från blocklistor.

- **Inaktivera konton som skickar för mycket skräppost:**<sup>\*</sup>Även om vi segregerar utgående skräppost i högriskleveranspoolen kan vi inte tillåta att ett konto (ofta ett komprometterat konto) skickar skräppost på obestämd tid. Vi övervakar konton som skickar skräppost, och när de överskrider en hemlig gräns blockeras kontot från att skicka e-post. Det finns olika tröskelvärden för enskilda användare och hela klienten.

- **Inaktivera konton som skickar för mycket e-post för snabbt:**<sup>\*</sup>Förutom de gränser som letar efter meddelanden som markerats som skräppost, finns det också gränser som blockerar konton när de når en övergripande utgående meddelandegräns, oavsett skräppostfiltreringsutlåtande på utgående meddelanden. Ett komprometterat konto kan skicka nolldags-skräppost (tidigare okänd) som missas av skräppostfiltret. Eftersom det kan vara svårt att identifiera en legitim massutskickskampanj jämfört med en skräppostkampanj, bidrar dessa gränser till att minimera eventuella skador.

<sup>\*</sup>Vi annonserar inte de exakta gränserna så spammare inte kan spela systemet, och så att vi kan öka eller minska gränserna vid behov. Gränserna är tillräckligt höga för att förhindra att en genomsnittlig företagsanvändare någonsin överskrider dem, och tillräckligt låg för att hjälpa till att begränsa de skador som orsakas av en spammare.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Rekommendationer för kunder som vill skicka massutskick via EOP

Det är svårt att hitta en balans mellan kunder som vill skicka en stor mängd e-post kontra skydda tjänsten från komprometterade konton och massavsändare av e-post med dålig praxis för mottagande förvärv. Kostnaden för en Microsoft 365 e-postkälla som landar på en tredje parts IP-blockeringslista är större än att blockera en användare som skickar för mycket e-post.

Som beskrivs i [Exchange Online Service Description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), med hjälp av EOP för att skicka mass-e-post är inte en stöds användning av tjänsten, och är endast tillåtet på en "best-effort" basis. För kunder som vill skicka massutskick rekommenderar vi följande lösningar:

- **Skicka massutskick via lokala e-postservrar**: Det innebär att kunderna måste underhålla sin egen e-postinfrastruktur för massutskick.

- **Använd en tredje part bulk e-postleverantör:** Det finns flera tredje part bulk e-postlösning leverantörer som du kan använda för att skicka massutskick. Dessa företag har ett egenintresse av att arbeta med kunder för att säkerställa god e-post sändning praxis.

Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) <https://www.maawg.org/about/roster>publicerar sitt medlemskap deltagarlistan på . Flera bulk e-postleverantörer är på listan, och är kända för att vara ansvariga Internet medborgare.
