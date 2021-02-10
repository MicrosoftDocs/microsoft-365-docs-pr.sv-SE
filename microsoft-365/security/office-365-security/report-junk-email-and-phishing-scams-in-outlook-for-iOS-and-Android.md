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
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166825"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Rapportera skräppost och nätfiske i Outlook för iOS och Android i Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

I Microsoft 365-organisationer med postlådor i Exchange Online eller lokala postlådor som använder [modern hybridautentisering](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)kan du använda de inbyggda rapporteringsalternativen i Outlook för iOS och Android för att skicka falska positiva identifieringar (bra e-post som har markerats som skräppost), falska negativa identifieringar (felaktig e-post tillåten) och nätfiskemeddelanden till Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver du veta innan du börjar

- Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter. Mer information finns i Använda administratörs inskickat material för att skicka misstänkt [skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)

- Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i principer [för användarinskick.](user-submission.md)

- Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Om skräppostrapportering är inaktiverad för Outlook i användarinskickingsprincipen flyttas skräppost- eller nätfiskemeddelanden till mappen Skräppost och rapporteras inte till din administratör eller Microsoft.

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>Rapportera skräppost och nätfiskemeddelanden i Outlook för iOS och Android

Använd följande steg för att rapportera skräppost och nätfiskemeddelanden för iOS och Android för meddelanden i Inkorgen eller någon annan e-postmapp utom Skräppost:

1. Markera ett eller flera meddelanden.
2. Tryck på de tre lodräta punkterna i det övre högra hörnet. Åtgärdsmenyn öppnas.

   ![Rapportera skräppost och nätfiske i åtgärdsmenyn](../../media/Android-report-as-junk-dialog.png)

3. Tryck **på Rapportera skräppost** och välj sedan **Skräppost** eller **nätfiske.**

   ![Rapportera skräppost och nätfiske](../../media/Android-report-junk-or-phishing.png)

4. I dialogrutan som visas kan du välja Rapport **eller** **Nej tack.** Om du **väljer Nej** tack  flyttas meddelandet till mappen Skräppost om du  trycker på Meddelandet flyttas till mappen Borttaget om du trycker på Nätfiske. Välj **Rapport** för att även skicka en kopia av meddelandet till Microsoft.

   ![Rapportalternativ för skräppost- och nätfiskemeddelanden](../../media/Android-junk-email-reporting-options.png)

Om du ändrar dig väljer du **Ångra i** popup-meddelandet som visas. Meddelandet finns kvar i mappen Inkorgen.

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>Rapportera meddelanden som inte är skräppost från skräppostmappen i Outlook för iOS och Android

Använd följande steg i skräppostmappen för att rapportera skräppost med falska positiva resultat:

1. Markera ett eller flera meddelanden.
2. Tryck på de tre lodräta punkterna i det övre högra hörnet. Åtgärdsmenyn öppnas.

   ![Rapportera inte skräppost från åtgärdsmenyn](../../media/Android-not-junk-email.png)

3. Tryck **på Inte skräppost.**

En avisering visas om att e-postmeddelandet har flyttats till Inkorgen. Om du ändrar dig väljer du Ångra **i** aviseringen. E-postmeddelandet ligger kvar i skräppostmappen.
