---
title: Skicka meddelanden till Microsoft manuellt för analys
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Administratörer och slutanvändare kan lära sig att e-postmeddelanden (bra e-postmeddelanden som markerats som dåliga eller dåliga e-postmeddelanden tillåtna) till Microsoft för analys.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c3a02c710472a996245a38d996ff4485efd1748
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624031"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Skicka meddelanden till Microsoft manuellt för analys

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Om du är administratör i en organisation med Exchange Online postlådor rekommenderar vi att du använder portalen för sändning i Säkerhets- & efterlevnadscenter. Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)

Det kan vara frustrerande när användare i organisationen tar emot skräppost eller nätfiskemeddelanden i Inkorgen, eller om de inte får ett legitimt e-postmeddelande eftersom det markeras som skräppost. Vi finjusterar ständigt våra skräppostfilter så att de blir mer exakta.

Du och dina användare kan hjälpa till med detta genom att skicka falska positiva meddelanden (bra e-postmeddelande markerat som dåligt), falskt negativa (felaktig e-post tillåts) och nätfiskemeddelanden till Microsoft för analys.

> [!NOTE]
> På grund av den stora mängden inskickade meddelanden kan vi kanske inte besvara alla förfrågningar om analys.

## <a name="submit-false-negatives-to-microsoft"></a>Skicka falska negativa tal till Microsoft

> [!TIP]
> I stället för att använda följande procedurer för att rapportera falska negativa tal kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tilläggen Rapportmeddelande eller Rapportera nätfiske. Mer information om hur du installerar [](enable-the-report-message-add-in.md) och använder dessa verktyg finns i Aktivera tillägget Rapportmeddelande och Aktivera tillägget [Rapportfiske.](enable-the-report-phish-add-in.md)

Om du får ett meddelande som har passerat skräppostfiltrering som borde ha identifierats som skräppost eller nätfiske kan du skicka meddelandet till Microsofts grupper för skräppostanalys och Microsoft-nätfiskeanalys. Analytikerna granskar meddelandet och lägger till det i filtren för hela tjänsten om det uppfyller klassificeringskriterierna.

1. Skapa ett nytt, tomt e-postmeddelande med någon av följande mottagare:

   - **Skräppost:**`junk@office365.microsoft.com`
   - **Nätfiske:**`phish@office365.microsoft.com`

2. Dra och släpp skräppost- eller nätfiskemeddelandet i det nya meddelandet. Då sparas skräppost- och nätfiskemeddelandet som en bifogad fil i det nya meddelandet. Kopiera inte innehållet i meddelandet eller vidarebefordra det (vi behöver det ursprungliga meddelandet så att vi kan kontrollera meddelanderubrikerna).

   > [!NOTE]
   >
   > - Du kan bifoga flera meddelanden i det nya meddelandet. Kontrollera att alla meddelanden har samma typ: antingen nätfiskemeddelanden eller skräppost.
   > - Lämna brödtexten i det nya meddelandet tom.
   > - Använd antingen .msg-format (Outlook) eller .eml-format (Outlook på webben-format) för bifogade meddelanden.

3. När du är klar klickar du på **Skicka**.

> [!TIP]
> Administratörer kan blockera specifika meddelanden som felaktigt kan blockeras som skräppost på flera olika sätt. Mer information finns i [Skapa spärrade avsändarlistor i EOP.](create-block-sender-lists-in-office-365.md)

## <a name="submit-false-positives-to-microsoft"></a>Skicka falska positiva resultat till Microsoft

> [!TIP]
> I stället för att använda följande procedurer för att rapportera falska positiva resultat kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tilläggen Rapportmeddelande eller Rapportera nätfiske. Mer information om hur du installerar [](enable-the-report-message-add-in.md) och använder dessa verktyg finns i Aktivera tillägget Rapportmeddelande och Aktivera tillägget [Rapportfiske.](enable-the-report-phish-add-in.md)

Om ett meddelande felaktigt identifierades som skräppost kan du skicka meddelandet till Microsofts team för skräppostanalys. Analytikerna utvärderar meddelandet och (beroende på resultatet av analysen) kan filtren för hela tjänsten justeras så att meddelandet går att komma igenom.

1. Skapa ett nytt, tomt e-postmeddelande `not_junk@office365.microsoft.com` med som mottagare.

2. Dra och släpp det felidentifierade meddelandet i det nya meddelandet. Det här sparar det felidentifierade meddelandet som en bifogad fil i det nya meddelandet. Kopiera inte innehållet i meddelandet eller vidarebefordra det (vi behöver det ursprungliga meddelandet så att vi kan kontrollera meddelanderubrikerna).

   > [!NOTE]
   >
   > - Du kan bifoga flera meddelanden i det nya meddelandet. Kontrollera att alla meddelanden har samma typ: antingen nätfiskemeddelanden eller skräppost.
   > - Lämna brödtexten i det nya meddelandet tom.
   > - Använd antingen .msg-format (Outlook) eller .eml-format (Outlook på webben-format) för bifogade meddelanden.

3. När du är klar klickar du på **Skicka**.

> [!TIP]
> Administratörer kan tillåta filtrering av skräppost på flera olika sätt. Mer information finns i [Skapa listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Var lagras data från inskickade data till Microsoft?

Data finns i den Office 365 gränsen för efterlevnad i nordamerikas datacenter. Data granskas av analytikerna i teknikteamet för att hjälpa till att göra filtren mer effektiva.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Skapa en e-postflödesregel för att ta emot kopior av meddelanden som rapporterats till Microsoft

Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)
