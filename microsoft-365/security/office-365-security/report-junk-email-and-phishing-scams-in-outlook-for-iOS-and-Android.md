---
title: Rapportera skräp post och nätfiske i Outlook för iOS och Android
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om de inbyggda skräp posten, inte skräp post och nätfiske-alternativen i Outlook för iOS och Android.
ms.openlocfilehash: 216f60eb168190603c7c9aba58cef27c2bf15b01
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867537"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Rapportera skräp post och nätfiske i Outlook för iOS och Android i Exchange Online

I Microsoft 365-organisationer med post lådor i Exchange Online eller lokala post lådor med [hybrid modern inloggningsautentisering](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview?view=o365-worldwide)kan du använda de inbyggda rapporterings alternativen i Outlook för iOS och Android för att skicka falska positiva (e-postmeddelanden markerade som skräp post), falskt negativ (dålig e-post) och nätfiske-meddelanden till Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver du veta innan du börjar

- Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för säkerhets & efterlevnad. Mer information finns i [använda administratörs överföring för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft](admin-submission.md).

- Du kan konfigurera vilka meddelanden som ska kopieras eller dirigeras om till en post låda som du anger. Mer information finns i [Ange en post låda för användar överföringar av skräp post och nät fiske meddelanden i Exchange Online](user-submission.md).

- Mer information om hur du rapporterar meddelanden till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

  > [!NOTE]
  > Om skräp post rapportering är inaktiverat för Outlook i princip för användar överföring flyttas skräp post eller nätfiske-meddelanden till skräppostmappen och inte rapporteras till din administratör eller Microsoft.

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>Rapportera skräp post och nät fiske meddelanden i Outlook för iOS och Android

Använd följande steg för att rapportera skräp post och nät fiske meddelanden för iOS och Android för meddelanden i Inkorgen, eller annan e-postmapp, utom skräp posten:

1. Markera ett eller flera meddelanden.
2. I det övre högra hörnet trycker du på de tre lodräta punkterna. Åtgärd-menyn öppnas.

   ![Rapportera skräp post eller nätfiske via åtgärd-menyn](../../media/Android-report-as-junk-dialog.png)

3. Tryck på **Rapportera skräp post** och välj sedan **skräp** post eller **nätfiske**.

   ![Rapportera skräp post eller nätfiske](../../media/Android-report-junk-or-phishing.png)

4. I dialog rutan som visas kan du välja **rapport** eller **Nej**. Om du väljer **Nej**, om du tryckte på **skräp** post flyttas meddelandet till mappen skräp post om du tryckte på **nätfiske** flyttas meddelandet till mappen Borttaget. Välj **rapport** om du även vill skicka en kopia av meddelandet till Microsoft.

   ![Rapportera alternativ för skräp post eller nätfiske](../../media/Android-junk-email-reporting-options.png)

Om du ändrar dig väljer du **Ångra** i popup-meddelandet som visas. Meddelandet finns kvar i mappen Inkorgen.

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>Rapportera icke-skräppost meddelanden från mappen skräp post i Outlook för iOS och Android

I mappen skräp post följer du stegen nedan för att rapportera skräp post som falsk.

1. Markera ett eller flera meddelanden.
2. I det övre högra hörnet trycker du på de tre lodräta punkterna. Åtgärd-menyn öppnas.

   ![Rapportera inte skräp post från åtgärd-menyn](../../media/Android-not-junk-email.png)

3. Tryck på **inte skräp post**.

En popup-avisering visas där e-postmeddelandet har flyttats till Inkorgen. Om du ändrar dig väljer du **Ångra** på popup-meddelandet. E-postmeddelandet finns kvar i skräppostmappen.
