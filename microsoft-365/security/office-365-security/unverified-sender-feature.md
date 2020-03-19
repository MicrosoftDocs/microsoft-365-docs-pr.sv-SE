---
title: Overifierad avsändare
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Om du vill förhindra att nätfiskemeddelanden når postlådan kontrollerar Outlook.com och Outlook på webben att avsändaren är den de säger att de är och markerar misstänkta meddelanden som skräppost.
ms.openlocfilehash: 513a45594dd41db56abe143ea6edca7074539d2f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805449"
---
# <a name="unverified-sender"></a>Overifierad avsändare

> [!NOTE]
> Dessa uppdateringar lanseras nu och kanske inte är tillgängliga för alla användare. Den här funktionen stöds för företagsanvändare Outlook.com och Enterprise Outlook Win32-skrivbordsanvändare. Den är för närvarande inte tillgänglig för Office 365-användare.

För att förhindra att nätfiskemeddelanden når postlådan verifierar Office 365 att avsändare är de som de säger att de är och markerar misstänkta meddelanden som skräppost.

> [!IMPORTANT]
> När ett meddelande markeras som ett nätfiskebedrägeri visas en varning högst upp på sidan, men alla länkar i meddelandet kan fortfarande öppnas.

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>Hur identifierar jag ett misstänkt meddelande i inkorgen?

Outlook visar indikatorer när avsändaren av ett meddelande antingen inte kan identifieras eller deras identitet skiljer sig från vad du ser i från-adressen.

## <a name="you-see-a--in-the-sender-image"></a>Du ser ett "?" i avsändarbilden

När Office 365 inte kan verifiera avsändarens identitet med hjälp av e-postautentiseringstekniker visas en '?

![Meddelandet skickade inte verifiering](../../media/message-did-not-pass-verification.jpg)

Alla meddelanden som inte autentiseras är inte skadliga. Du bör dock vara försiktig med att interagera med meddelanden som inte autentiserar om du inte känner igen avsändaren. Eller, om du känner igen en avsändare som normalt inte har en "?" i avsändaren bilden, men du plötsligt börjar se det, som kan vara ett tecken avsändaren är spoofed.

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a>Så här hanterar du vilka meddelanden som får den overifierade avsändarens behandling 

Om du är Office 365-kund kan du hantera den här funktionen via Office 365 Security & Compliance Center.

- I Security & Compliance Center kan globala administratörer eller säkerhetsadministratörer aktivera eller inaktivera funktionen genom anti-spoofing-skydd enligt anti-Phish-principen. Dessutom kan du använda cmdleten **Set-AntiPhishPolicy** i Exchange Online PowerShell. Mer information finns [i Skydd mot nätfiske i Office 365](anti-phishing-protection.md) och [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).

    ![Redigera oautentiserade avsändare i det grafiska gränssnittet.](../../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- Om en administratör har identifierat ett falskt positivt, och en avsändare inte ska få den overifierade avsändarenbehandling, kan en av följande åtgärder vidtas för att lägga till avsändaren i spoof Intelligence-parodilistan:

  - Lägg till domänparet via Spoof Intelligence Insight. Mer information finns [i Genomgång: falska underrättelseinsikter](walkthrough-spoof-intelligence-insight.md).

  - Lägg till domänparet via **Cmdlet Set-PhishFilterPolicy** i Exchange Online PowerShell. Mer information finns i [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) och [Konfigurera Office 365 ATP-policyer mot nätfiske och nätfiske](set-up-anti-phishing-policies.md).

Dessutom tillämpar vi inte den overifierade avsändarbehandlingen om meddelandet levererades till inkorgen via regler för e-postflöde (kallas även transportregler) eller safe domain list (anti-spam-policyer).

## <a name="how-to-manage-the-via-tag"></a>Hur man hanterar "via"-taggen 

Om du är Office 365-kund kan du hantera den här funktionen via Office 365 Security & Compliance Center, på samma sätt som du hanterar den overifierade avsändarbehandlingen. Om du lägger till avsändaren i Spoof Intelligence spoof tillåta lista, kommer "via" behandling inte tillämpas.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a>Vilka kriterier använder Outlook.com och Outlook Win32-skrivbordet för att lägga till egenskaperna "?" och "via"- och "via"-egenskaperna?

För avsändarbilden: Outlook.com kräver att meddelandet skickar antingen SPF- eller DKIM-autentisering och tar emot antingen ett dmarc-kort eller ett sammansatt autentiseringspass från Office 365 Spoof Intelligence. Mer information finns i [Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md) och Användning av [DKIM för att validera utgående e-post som skickas från din anpassade domän i Office 365](use-dkim-to-validate-outbound-email.md).

För via-taggen: Om domänen i från-adressen skiljer sig från domänen i DKIM-signaturen eller SMTP-posten FRÅN, visar Outlook.com domänen i ett av dessa två fält (föredrar DKIM-signaturen).

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a>Hur tar jag bort "?" utan att använda Spoof Intelligence parodi tillåta lista?

För "?"- i avsändarbilden: Som avsändare bör du autentisera ditt meddelande med antingen SPF eller DKIM.

För via-taggen: Som avsändare bör du se till att antingen domänen i DKIM-signaturen eller SMTP-posten från är densamma som, eller är en underdomän för, domänen i från-adressen.

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a>Visar Outlook.com och Outlook Win32-skrivbordet detta för alla meddelanden som inte skickar autentisering?

Inte nödvändigtvis. Office 365 kan ha andra egenskaper i meddelandet för att autentisera avsändaren.

## <a name="related-topics"></a>Relaterade ämnen

[Skydda ditt Outlook.com e-postkonto](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[Ta itu med nätfiske eller förfalskning i Outlook.com](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[Filtrera skräppost och skräppost i Outlook på webben](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
