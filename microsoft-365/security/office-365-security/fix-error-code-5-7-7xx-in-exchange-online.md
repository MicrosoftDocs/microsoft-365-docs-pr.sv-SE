---
title: Åtgärda problem med e-postleverans för felkod 5.7.7xx i Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Läs om hur du åtgärdar e-postproblem för felkod 5.7.7xx i Exchange Online (klienten blockeras från att skicka e-post).
ms.openlocfilehash: e8e134793db946ddfc3ef09d0adc19b2a04df30b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810738"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Åtgärda problem med e-postleverans för felkod 5.7.7xx i Exchange Online

I det här avsnittet beskrivs vad du kan göra om du ser statuskoden 550 5.7.7xx i en rapport om utebliven leverans (kallas även NDR, avvisningsmeddelande, leveransstatusmeddelande eller DSN). Den här automatiska aviseringen visas när din klient är begränsad från att skicka e-post på ett eller annat sätt. Dessa felkoder kommer vanligtvis in som 705 eller 750.

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: Hyresgästen har överskridit tröskelbegränsning: Vad du behöver veta

När användarna (kollektivt, som organisation) skickar en viss mängd misstänkt e-post via tjänsten, kan alla användare hindras från att skicka e-post tills problemet är åtgärdat. Detta är vanligtvis resultatet av en kompromiss (vanligast) eller skicka för mycket massutskick. Användare får en NDR som anger:

`550 5.7.705 Access denied, tenant has exceeded threshold`

I sällsynta fall kan detta också inträffa om du förnyar prenumerationen när den redan har upphört att gälla. Det tar tid för tjänsten att synkronisera den nya prenumerationsinformationen (vanligtvis inte mer än en dag), men din organisation kan blockeras från att skicka e-post under tiden. Det bästa sättet att förhindra detta är att se till att din prenumeration inte upphör att gälla.

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: Oregistrerad domän e-begränsning: Vad du behöver veta

Med Office 365 kan klienter vidarebefordra vissa meddelanden via Exchange Online Protection (EOP). Till exempel:

- En Office 365-postlåda tar emot e-post från en extern avsändare. Vidarebefordring av e-post är konfigurerad i Office 365-postlådan, så meddelandet skickas tillbaka till användarens externa e-postadress. Det här scenariot är vanligast i utbildningsmiljöer där eleverna vill använda sina personliga e-postkonton för att visa skolrelaterade meddelanden.

- Hybridmiljöer som har lokala e-postservrar som skickar utgående e-post via EOP.

### <a name="problems-with-unregistered-domains"></a>Problem med oregistrerade domäner

Problemet är när äventyras lokala e-postservrar vidarebefordra en stor mängd spam via EOP. I nästan alla fall är kopplingarna korrekt inställda, men e-post skickas från oregistrerade (kallas även oetablerade) domäner. Office 365 tillåter en rimlig mängd e-post från oregistrerade domäner, men du bör konfigurera alla domäner som du använder för att skicka e-post som en accepterad domän.

När komprometteras förhindras klienter från att skicka utgående e-post för oregistrerade domäner. Användare får en NDR som anger:

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="unblocking-tenant-in-order-to-send-again"></a>Avblockera klienten för att skicka igen

Det finns flera saker du behöver göra om din klient är blockerad från att skicka e-post:

1. Ändra lösenordet för dina administratörskonton. Om en klient har blockerats från att skicka är det mest troligt att ett administratörskonto komprometterades. Att ändra lösenord är det första steget för att förhindra att angriparen gör mer skada.

2. [Aktivera MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) för alla administratörer i office 365-organisationen.

3. Kontrollera att alla dina e-postdomäner är registrerade. Mer information finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) och Hantera godkända [domäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

4. Leta efter ovanliga [kontakter](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). Skadliga aktörer skapar ofta nya inkommande kopplingar i Office 365-organisationen för att skicka skräppost. Information om hur du visar befintliga kopplingar finns [i Validera kopplingar i Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors).

5. Sök efter komprometterade användare enligt beskrivningen i [Svara på ett komprometterat e-postkonto i Office 365](responding-to-a-compromised-email-account.md).

6. Lås dina lokala e-postservrar och kontrollera att de inte äventyras.

   > [!TIP]
   > Det finns många faktorer här, särskilt om du använder servrar från tredje part. Oavsett måste du kontrollera att din utgående e-post inte innehåller skräppost.

7. Ring Microsoft Support och be att få din klient avblockerad för att skicka e-post igen. Felkoden är användbar, men du måste bevisa att din miljö har säkrats och är oförmögen att skicka skräppost. Information om hur du öppnar ett supportärende finns i [Kontakta support för företagsprodukter - Hjälp om administratörer](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

## <a name="for-more-information"></a>Mer information

[Office 365 email anti-spam protection](anti-spam-protection.md)

[Massutskicksvägledning i avsnittet Sändningsgränser i exchange online-tjänstens beskrivning](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[NDR-rapporter via e-post i Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[Konfigurera vidarebefordran av e-post för en postlåda](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Konfigurera en multifunktionsenhet eller ett multifunktionsprogram för att skicka e-post med hjälp av Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

[Hantera godkända domäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
