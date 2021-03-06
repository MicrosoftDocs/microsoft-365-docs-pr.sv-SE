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
ms.openlocfilehash: e6e63f534a9f9516c6e1a87ff82d5b0916d25778
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509332"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Rapportera skräppost och nätfiske i Outlook för iOS och Android i Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller lokala postlådor som använder [modern hybridautentisering](../../enterprise/hybrid-modern-auth-overview.md)kan du skicka falska positiva identifieringar (bra e-post som har markerats som skräppost), falska negativa meddelanden (felaktig e-post tillåts) och nätfiskemeddelanden till Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver du veta innan du börjar

- För bästa användarinskickning rekommenderar vi att du använder rapportmeddelandet och tilläggen för nätfiske. Mer information finns i Aktivera tillägget [Rapportmeddelande](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) och Aktivera tillägget [Rapport](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) nätfiske.

- Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter. Mer information finns i Använda administratörs inskickat material för att skicka misstänkt [skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)

- Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i principer [för användarinskick.](user-submission.md)

- Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Om skräppostrapportering är inaktiverad för Outlook i användarinskickingsprincipen flyttas skräppost- eller nätfiskemeddelanden till mappen Skräppost och rapporteras inte till din administratör eller Microsoft.
