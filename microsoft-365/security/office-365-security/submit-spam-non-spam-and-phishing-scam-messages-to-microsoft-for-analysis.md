---
title: Skicka meddelanden manuellt till Microsoft för analys
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Du och dina användare kan skicka falska negativa och falska positiva skräppostmeddelanden till Microsoft för analys. '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7fc26e1cba976e68b8dcfee5ec8b4fe366b8c47
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035242"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Skicka meddelanden manuellt till Microsoft för analys

> [!NOTE]
> Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inlämningar i Security & Compliance Center. Mer information finns i [Använda administratörsöverföring för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft](admin-submission.md).

Det kan vara frustrerande när användare i organisationen får skräppost eller nätfiskemeddelanden i inkorgen, eller om de inte får ett legitimt e-postmeddelande eftersom det är markerat som skräppost. Vi finjusterar ständigt våra skräppostfilter för att vara mer exakta.

Du och dina användare kan hjälpa den här processen genom att skicka in falska positiva identifieringar (bra e-post markerad som dålig), falska negativ (felaktig e-post tillåten) och nätfiskemeddelanden till Microsoft för analys.

> [!NOTE]
> På grund av den stora mängden inlagor som vi får kanske vi inte kan svara på alla förfrågningar om analys.

## <a name="submit-false-negatives-to-microsoft"></a>Skicka falska negativ till Microsoft

> [!TIP]
> I stället för att använda följande procedurer för att rapportera falska negativ kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tillägget Rapportmeddelande för Microsoft Outlook. Information om hur du installerar och använder det här verktyget finns [i Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md).

Om du får ett meddelande som skickades genom skräppostfiltrering som borde ha identifierats som skräppost eller nätfiske kan du skicka meddelandet till microsofts team för skräppostanalys och Microsofts nätfiskeanalys efter behov. Analytikerna granskar meddelandet och lägger till det i de serviceomfattande filtren om det uppfyller klassificeringskriterierna.

1. Skapa ett nytt, tomt e-postmeddelande med någon av följande mottagare:

   - **Skräp:**`junk@office365.microsoft.com`

   - **Nätfiske:**`phish@office365.microsoft.com`

2. Dra och släpp skräppost- eller nätfiskemeddelandet i det nya meddelandet. Detta sparar skräppost- eller nätfiskemeddelandet som en bifogad fil i det nya meddelandet. Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan inspektera meddelanderubrikerna).

   > [!NOTE]
   > <ul><li>Du kan bifoga flera meddelanden i det nya meddelandet. Kontrollera att alla meddelanden är av samma typ: antingen meddelanden om nätfiske eller skräppost.</li><li>Lämna brödtexten i det nya meddelandet tom.</li><li>Använd antingen MSG-format (standardformatet Outlook) eller .eml (standardformatet Outlook på webben) för de bifogade meddelandena.</li></ul>

3. När du är klar klickar du på **Skicka**.

> [!TIP]
> Administratörer har flera olika sätt att blockera specifika meddelanden som felidentifieras som skräppost. Mer information finns [i Skapa blockerade avsändarelistor i Office 365](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Skicka falska positiva identifieringar till Microsoft

> [!TIP]
> I stället för att använda följande procedurer för att rapportera falska positiva identifieringar kan användare i Outlook och Outlook på webben använda tillägget Rapportmeddelande för Microsoft Outlook. Information om hur du installerar och använder det här verktyget finns [i Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md).

Om ett meddelande har identifierats felaktigt som skräppost kan du skicka meddelandet till Microsoft Spam Analysis Team. Analytikerna kommer att utvärdera meddelandet, och (beroende på resultaten av analysen) kan de serviceomfattande filtren justeras så att meddelandet går igenom.

1. Skapa ett nytt, tomt `not_junk@office365.microsoft.com` e-postmeddelande med som mottagare:

2. Dra och släpp det felidentifierade meddelandet i det nya meddelandet. Då sparas det felidentifierade meddelandet som en bifogad fil i det nya meddelandet. Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan inspektera meddelanderubrikerna).

   > [!NOTE]
   > <ul><li>Du kan bifoga flera meddelanden i det nya meddelandet. Kontrollera att alla meddelanden är av samma typ: antingen nätfiskemeddelanden eller skräppostmeddelanden.</li><li>Lämna brödtexten i det nya meddelandet tom.</li><li>Använd antingen MSG-format (standardformatet Outlook) eller .eml (standardformatet Outlook på webben) för de bifogade meddelandena.</li></ul>

3. När du är klar klickar du på **Skicka**.

> [!TIP]
> Administratörer har flera olika sätt att tillåta specifika meddelanden att hoppa över skräppostfiltrering. Mer information finns [i Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Skapa en regel för e-postflöde för att ta emot kopior av meddelanden som rapporteras till Microsoft

Instruktioner finns i [Använda regler för e-postflöde för att se vad användarna rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
