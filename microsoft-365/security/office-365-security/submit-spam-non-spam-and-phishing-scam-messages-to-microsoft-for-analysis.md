---
title: Skicka meddelanden till Microsoft för analys manuellt
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Administratörer och slutanvändare kan läsa mer om hur man skickar meddelanden (god e-post markerat som dålig eller dålig e-post) till Microsoft för analys.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94747b1d0a1aef746a63abada977aa47270ae4e2
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865086"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Skicka meddelanden till Microsoft för analys manuellt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för säkerhets & efterlevnad. Mer information finns i [använda administratörs överföring för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft](admin-submission.md).

Det kan vara frustrerande när användare i din organisation får skräp post eller nätfiske-meddelanden i sin inkorg, eller om de inte får ett legitimt e-postmeddelande eftersom det är markerat som skräp post. Vi kan alltid finjustera våra skräp post filter så att de blir mer korrekta.

Du och dina användare kan hjälpa till med den här processen genom att skicka falsk identifiering (god e-post markerat som dåligt), falskt negativ (dålig e-post) och nätfiske-meddelanden till Microsoft för analys.

> [!NOTE]
> På grund av de stora mängder som vi tar emot kanske vi inte kan besvara alla förfrågningar om analys.

## <a name="submit-false-negatives-to-microsoft"></a>Skicka falska negativa negativ till Microsoft

> [!TIP]
> I stället för att använda följande procedurer för att rapportera falska negativa tal, kan användare i Outlook och Outlook på webben (tidigare Outlook Web App) använda tillägget rapport meddelande eller rapport-nätfiske. Information om hur du installerar och använder de här verktygen finns i [aktivera tillägget rapportera meddelande](enable-the-report-message-add-in.md) och [aktivera tillägget Rapportera nätfiske](enable-the-report-phish-add-in.md).

Om du får ett meddelande som skickas via skräp post filter som skulle ha identifierats som skräp post eller nätfiske kan du skicka meddelandet till Microsoft spam och Microsoft Phishing Analysis Teams. Analyserna granskar meddelandet och lägger till det i tjänstens globala filter om det uppfyller klassificerings villkoren.

1. Skapa ett nytt, tomt e-postmeddelande med någon av följande mottagare:

   - **Skräp post**: `junk@office365.microsoft.com`

   - **Nätfiske**: `phish@office365.microsoft.com`

2. Dra och släpp skräp post eller nätfiske till det nya meddelandet. Detta sparar skräp post-eller nät fiske meddelandet som en bifogad fil i det nya meddelandet. Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra det (vi behöver det ursprungliga meddelandet så att vi kan kontrol lera meddelande huvudena).

   > [!NOTE]
   >
   > - Du kan bifoga flera meddelanden i det nya meddelandet. Kontrol lera att alla meddelanden är av samma typ: antingen nät fiske meddelanden och skräp post.
   >
   > - Lämna bröd texten i det nya meddelandet tomt.
   >
   > - Använd antingen. msg (standard Outlook-format) eller. eml (standard i Outlook på webb format) format för bifogade meddelanden.

3. När du är klar klickar du på **Skicka**.

> [!TIP]
> Administratörer har flera olika sätt att blockera specifika meddelanden som identifieras som skräp post. Mer information finns i [skapa spärrade avsändare i EOP](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Skicka falsk positiv till Microsoft

> [!TIP]
> I stället för att använda följande procedurer för att rapportera falsk identifiering kan användare i Outlook och Outlook på webben (tidigare Outlook Web App) använda tillägget rapport meddelande eller rapport-nätfiske. Information om hur du installerar och använder de här verktygen finns i [aktivera tillägget rapportera meddelande](enable-the-report-message-add-in.md) och [aktivera tillägget Rapportera nätfiske](enable-the-report-phish-add-in.md).


Om ett meddelande felaktigt har identifierats som skräp post kan du skicka meddelandet till Microsoft spam-gruppen. Analyserna utvärderar meddelandet och (beroende på analys resultaten) kan de globala filtren justeras så att de tillåter meddelandet.

1. Skapa ett nytt, tomt e-postmeddelande med `not_junk@office365.microsoft.com` som mottagare:

2. Dra och släpp det felidentifierade meddelandet i det nya meddelandet. Detta sparar det felidentifierade meddelandet som en bifogad fil i det nya meddelandet. Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra det (vi behöver det ursprungliga meddelandet så att vi kan kontrol lera meddelande huvudena).

   > [!NOTE]
   >
   > - Du kan bifoga flera meddelanden i det nya meddelandet. Kontrol lera att alla meddelanden är av samma typ: antingen nät fiske meddelanden och skräp post.
   >
   > - Lämna bröd texten i det nya meddelandet tomt.
   >
   > - Använd antingen. msg (standard Outlook-format) eller. eml (standard i Outlook på webb format) format för bifogade meddelanden.

3. När du är klar klickar du på **Skicka**.

> [!TIP]
> Administratörer har flera olika sätt att tillåta vissa meddelanden att hoppa över filtrering av skräp post. Mer information finns i [skapa säkra avsändar listor i EOP](create-safe-sender-lists-in-office-365.md).

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Var lagras data från inlägg till Microsoft?

Informationen finns i begränsningen för Office 365-kompatibilitet i Nord amerikanska data Center. Informationen granskas av analytiker på ingenjörs avdelningen för att förbättra filterens effektivitet.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Skapa en regel för e-postflöde för att ta emot kopior av meddelanden som rapporteras till Microsoft

Anvisningar finns i [använda e-postflödes regler för att se vad användarna rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
