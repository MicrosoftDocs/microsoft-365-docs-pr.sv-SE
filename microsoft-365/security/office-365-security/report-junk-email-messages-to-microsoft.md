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
ms.openlocfilehash: 3f8d07a2499fa3c8690393aa444e018b83c632b1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808992"
---
# <a name="report-junk-email-messages-to-microsoft"></a>Rapportera skräppostmeddelanden till Microsoft

Microsofts tillägg för skräppostrapportering för Microsoft Office Outlook innehåller flera sätt att rapportera skräppostmeddelanden:

- Från menyfliksområdet i Outlook

- Från inkorgen

- Inifrån ett öppnat e-postmeddelande

Tillägget Rapportering av skräppost hjälper dig att skicka rapporter till Tjänsten Microsoft Exchange Online Protection (EOP). Om postlådan inte skyddas av tjänsten påverkar inte överföringen av skräppostrapporten dina skräppostfilter skräppostfiltren. Administratörer kan lära sig mer om fler skräppostinställningar som gäller för en hel organisation på [How to prevent good email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md) or [How to reduce spam email in Office 365](reduce-spam-email.md). Dessa är användbara om du har kontroll på administratörsnivå och du vill förhindra falska positiva eller falska negativ.

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

## <a name="for-more-information"></a>Mer information

[Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md)

[Felsöknings- och supportinformation](troubleshooting-and-support-information.md)

[Så här förhindrar du att bra e-post markeras som skräppost i Office 365](prevent-email-from-being-marked-as-spam.md)

[Så här minskar du skräppost i Office 365](reduce-spam-email.md)
