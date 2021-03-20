---
title: Rapportera skräppost och nätfiske i Outlook för iOS och Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om de inbyggda alternativen för skräppost, inte skräppost och nätfiske i Outlook för iOS och Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eda0d8d43244834236a70374df6b7d6ccf0b69ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908824"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Rapportera skräppost och nätfiske i Outlook för iOS och Android i Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller lokala postlådor med [modern hybridautentisering](../../enterprise/hybrid-modern-auth-overview.md)kan du skicka falska positiva identifieringar (bra e-post som markerats som skräppost), falska negativa identifieringar (felaktig e-post tillåts) och nätfiskemeddelanden till Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver du veta innan du börjar

- För att du ska kunna skicka in rapporten på bästa sätt rekommenderar vi att du använder tilläggen Rapportmeddelande och Rapport vid nätfiske. Mer information [finns i Aktivera tillägget Rapportmeddelande](./enable-the-report-message-add-in.md) och Aktivera tillägget [Rapportfiske.](./enable-the-report-phish-add-in.md)

- Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för sändning i Säkerhets- och & Efterlevnadscenter. Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)

- Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i Principer [för användarinskick.](user-submission.md)

- Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Om skräppostrapportering är inaktiverat för Outlook i principen för användarinskicking flyttas skräppost- eller nätfiskemeddelanden till mappen Skräppost och rapporteras inte till din administratör eller Microsoft.