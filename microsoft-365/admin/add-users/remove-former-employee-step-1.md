---
title: Steg 1 – Hindra en anställd från att logga in på Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Blockera en tidigare anställd från att logga in och blockera åtkomst till Microsoft 365 tjänster.
ms.openlocfilehash: 8eb41c3b449e63284371aaf168262307a4c21941
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535956"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>Steg 1 – Förhindra en tidigare anställd från att logga in och blockera åtkomst Microsoft 365 tjänster

Om du omedelbart behöver förhindra en användares inloggningsåtkomst ska du återställa användarens lösenord. I det här steget tvingar du användaren att logga ut från Microsoft 365.

> [!NOTE]
> Du måste vara global administratör för att kunna starta ut logga ut.

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera rutan bredvid användarens namn och välj sedan **Återställ lösenord**.
3. Ange ett nytt lösenord och välj sedan **Återställ**. (Skicka det inte till dem.)
4. Välj användarens namn för att gå till egenskapsfönstret och välj Initiera ut logga **ut på fliken Konto.** 

Inom en timme – eller efter att han eller hon lämnar den Microsoft 365 aktuella sidan de befinner sig på – uppmanas de att logga in igen. En åtkomsttoken är bra i en timme, så tidslinjen beror på hur mycket tid som återstår för den tokenen och om de navigerar från den aktuella webbsidan.
  
> [!IMPORTANT]
> Om användaren är i Outlook på webben, bara klickar runt i postlådan, kanske han/hon inte sparkas ut direkt. Så snart de väljer en annan panel, till OneDrive, eller uppdaterar sin webbläsare initieras ut logga ut.
  
Om du vill använda PowerShell för att logga ut en användare direkt går du till cmdleten [Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)
  
Mer information om hur lång tid det tar att avsluta en persons e-post finns i [Vad du behöver veta om att avsluta en anställds e-postsession](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>Blockera en tidigare anställds åtkomst till Microsoft 365 tjänster

> [!IMPORTANT]
 > Det kan ta upp till 24 timmar innan blockeringen av ett konto verkställs. Om du omedelbart behöver förhindra en användares inloggningsåtkomst följer du stegen ovan och återställer deras lösenord.

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera namnet på den anställda som du vill blockera och välj symbolen för Blockera den här användaren under **användarnamnet.**
3. Välj **Blockera användaren från att logga in** och välj sedan **Spara**.

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Blockera en tidigare anställds åtkomst till e-post (Exchange Online)

Om du har e-post som en del av Microsoft 365-prenumerationen loggar du in på Exchange-administrationscentret och följer de här stegen för att blockera den tidigare anställda från att komma åt sin e-post.
  
1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.
2. I Administrationscenter för Exchange går du till **Mottagare** \> **Postlådor**.
3. Dubbelklicka på användaren och gå till sidan **Postlådefunktioner.** Under **Mobila enheter** väljer du Inaktivera **Exchange ActiveSync** inaktivera **OWA** för enheter och svarar **Ja** på båda när du uppmanas att göra det.
4. Under **E-postanslutning** väljer **du Inaktivera** och svarar Ja **när** du uppmanas att göra det.
