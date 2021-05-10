---
title: Rapportera falska positiva och falska negativa i Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Lär dig hur du rapporterar falska positiva och falska negativa Outlook i funktionen Rapportmeddelande.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e848595035501f5da7b6099efd2700ebac6f17e3
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291169"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>Rapportera falska positiva och falska negativa i Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Om du är administratör i en Microsoft 365 organisation med Exchange Online postlådor rekommenderar vi att du använder portalen för inskickade inskickade material i Säkerhets- & efterlevnadscenter. Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller lokala postlådor med modern hybridautentisering kan du skicka falska positiva identifieringar (bra e-postmeddelanden som har blockerats eller skickats till skräppostmappen) och falska negativa identifieringar (oönskad e-post eller nätfingr som skickats till inkorgen) till Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- För bästa möjliga användarinskickning använder du tilläggen Rapportmeddelande eller Rapport nätfiske.

- Observera att det här tillägget fungerar för Outlook plattformar – på webben, iOS, Android och skrivbordet.

- Om du är administratör i en organisation med Exchange Online postlådor använder du portalen för inskickade inskickade uppgifter i säkerhets- & efterlevnadscenter. Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)

- Du kan konfigurera så att meddelanden skickas direkt till Microsoft, en postlåda som du anger eller båda. Mer information finns i Principer [för användarinskick.](user-submission.md)

- Mer information om hur du hämtar och aktiverar rapportmeddelandet eller tilläggen för rapportfiske finns i Aktivera rapportmeddelandet eller tilläggen för [rapportfiske.](enable-the-report-message-add-in.md)

- Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-report-message-feature"></a>Använda funktionen Rapportmeddelande

### <a name="report-junk-and-phishing-messages"></a>Rapportera skräppost och nätfiskemeddelanden

För meddelanden i Inkorgen eller någon annan e-postmapp utom Skräppost använder du följande metod för att rapportera skräppost och nätfiske:

1. Klicka på **ellipsen** Fler åtgärder längst upp till höger  i det markerade meddelandet, klicka på Rapportera meddelande i den nedrullningsbara menyn och välj sedan **Skräppost** eller **Nätfiske.**
  
   > [!div class="mx-imgBorder"]
   > ![Rapportmeddelande – fler åtgärder](../../media/report-message-more-actions.png)

   > [!div class="mx-imgBorder"]
   > ![Rapportmeddelande – skräppost och nätfiske](../../media/report-message-junk-phishing.png)

2. De valda meddelandena skickas till Microsoft för analys och:

   - Flyttades till mappen Skräppost om den rapporterades som skräppost.

   - Borttagna om det har rapporterats som nätfiske.
   
### <a name="report-messages-that-are-not-junk"></a>Rapportera meddelanden som inte är skräppost

1. Klicka på **ellipsen** Fler åtgärder i det övre högra  hörnet av det markerade meddelandet, klicka på Rapportera meddelande i den nedrullningsbara menyn och klicka sedan **på Inte skräppost.**  

   > [!div class="mx-imgBorder"]
   > ![Rapportmeddelande – fler åtgärder](../../media/report-message-more-actions.png)

   > [!div class="mx-imgBorder"]
   > ![Rapportmeddelande – inte skräppost](../../media/report-message-not-junk.png)

2. Det markerade meddelandet skickas till Microsoft för analys och flyttas till Inkorgen eller någon annan angiven mapp.

## <a name="view-and-review-reported-messages"></a>Visa och granska rapporterade meddelanden

Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:

- Använd portalen för administrationsinskick. Mer information finns i [Visa användarinskick till Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)

- Skapa en e-postflödesregel (kallas även transportregel) för att skicka kopior av rapporterade meddelanden. Anvisningar finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)