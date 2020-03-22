---
title: Rapportera skräppostmeddelanden till Microsoft
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 'Microsofts tillägg för skräppostrapportering för Microsoft Office Outlook innehåller flera sätt att rapportera skräppostmeddelanden:'
ms.openlocfilehash: b1ed918e4b954cc7b2d79e52abd6f58a99eda0f0
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895185"
---
# <a name="report-junk-email-messages-to-microsoft"></a>Rapportera skräppostmeddelanden till Microsoft

Microsofts tillägg för skräppostrapportering för Microsoft Office Outlook innehåller flera sätt att rapportera skräppostmeddelanden:

- Från menyfliksområdet i Outlook

- Från inkorgen

- Inifrån ett öppnat e-postmeddelande

Tillägget Rapportering av skräppost hjälper dig att skicka rapporter till Tjänsten Microsoft Exchange Online Protection (EOP). Om postlådan inte skyddas av tjänsten påverkar inte överföringen av skräppostrapporten dina skräppostfilter skräppostfiltren. Administratörer kan läsa mer om fler skräppostinställningar som gäller för en hel organisation på [Skapa listor över säkra avsändare i Office 365](create-safe-sender-lists-in-office-365.md) och Skapa blockerade [avsändarelistor i Office 365](create-block-sender-lists-in-office-365.md). Dessa är användbara om du har kontroll på administratörsnivå och du vill förhindra falska positiva eller falska negativ.

> [!TIP]
> Du kan också skicka skräppostmeddelanden direkt till Microsoft med hjälp av [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) e-postadress och falska positiva meddelanden (icke-skräppost) med hjälp av [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com) e-postadress. Mer information finns i [Skicka meddelanden om skräppost, skräppost och nätfiske till Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

### <a name="to-report-junk-email-messages-from-outlook"></a>Så här anmäler du skräppost från Outlook

[Använda tillägget Rapportmeddelande](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

### <a name="to-report-junk-email-messages-from-your-inbox"></a>Så här anmäler du skräppost från inkorgen

1. Högerklicka på meddelandet eller meddelanden som du vill rapportera som skräppost.

2. Välj **Skräppost** och klicka sedan på **Rapportera skräppost**.
    ![Rapportera skräppost från inkorgen](../../media/EOP-Outlook-Junk-Reporting-Tool-3.jpg)

3. Dialogrutan **Microsoft-skräppostrapportering** öppnas. Om du är säker på att du vill skicka de meddelanden som du har markerat som skräppost klickar du på **Ja**.
    ![Bekräfta rapporten som skräppost](../../media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)

    > [!NOTE]
    > Om du inte vill få det här bekräftelsemeddelandet när du skickar skräppost markerar du **Visa inte det här meddelandet igen**.

De valda meddelandena skickas till Microsoft för analys och flyttas till mappen Skräppost. Om du vill bekräfta att meddelandena har skickats öppnar du mappen **Skickat för** att visa de skickade meddelandena.

### <a name="to-report-a-junk-email-message-from-within-an-opened-message"></a>Så här anmäler du ett skräppostmeddelande inifrån ett öppnat meddelande

1. Klicka på knappen Rapportera **skräppost** i meddelandefliksområdet i ett öppnat meddelande. Klicka till exempel på \> **Skräppostrapport** ![en skräppost från ett meddelande **Junk**](../../media/EOP-Outlook-Junk-Reporting-Tool-4.jpg)

2. Dialogrutan **Microsoft-skräppostrapportering** öppnas. Om du är säker på att du vill skicka meddelandet du valde som skräppost klickar du på **Ja**.
    ![Bekräfta rapporten som skräppost](../../media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)

    > [!NOTE]
    > Om du inte vill få det här bekräftelsemeddelandet när du skickar skräppost markerar du **Visa inte det här meddelandet igen**.

Det valda meddelandet skickas till Microsoft för analys och flyttas till mappen Skräppost. Om du vill bekräfta att meddelandet har skickats öppnar du mappen **Skickat för** att visa det skickade meddelandet.
