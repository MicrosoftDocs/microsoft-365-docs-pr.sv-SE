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
description: Administratörer och slutanvändare kan lära sig att e-postmeddelanden (bra e-postmeddelanden som markerats som dåliga eller dåliga e-postmeddelanden) till Microsoft för analys.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 98964d17c41222fa708bdf0059c0e67151582ef1
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290375"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Skicka meddelanden till Microsoft manuellt för analys

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter. Mer information finns i Använda [administrationsinskick för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)

Det kan vara frustrerande när användare i organisationen får skräppost (skräppost) eller nätfiskemeddelanden i Inkorgen, eller om de inte får ett legitimt e-postmeddelande eftersom det markeras som skräppost. Vi finjusterar kontinuerligt våra skräppostfilter för att bli mer exakta.

Du och dina användare kan hjälpa till med detta genom att skicka falska positiva meddelanden (bra e-post markerad som dålig), falska negativa meddelanden (felaktig e-post tillåts) och nätfiskemeddelanden till Microsoft för analys.

> [!NOTE]
> På grund av den stora mängden inskickade uppgifter kan vi kanske inte besvara alla förfrågningar om analys.

## <a name="submit-false-negatives-to-microsoft"></a>Skicka falska negativa tal till Microsoft

> [!TIP]
> Istället för att använda följande procedurer för att rapportera falska negativa tal kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tillägget Rapportmeddelande eller tillägget Rapport nätfiske. Mer information om hur du installerar [](enable-the-report-message-add-in.md) och använder de här verktygen finns i Aktivera tillägget Rapportmeddelande och Aktivera tillägget [Rapport nätfiske.](enable-the-report-phish-add-in.md)

Om du får ett meddelande som har passerat skräppostfiltrering som borde ha identifierats som skräppost eller nätfiske kan du skicka meddelandet till Microsofts team för skräppostanalys och Microsofts nätfiskeanalys. Analytikerna granskar meddelandet och lägger till det i filtren för hela tjänsten om det uppfyller klassificeringskriterierna.

1. Skapa ett nytt, tomt e-postmeddelande med någon av följande mottagare:

   - **Skräppost:**`junk@office365.microsoft.com`

   - **Nätfiske:**`phish@office365.microsoft.com`

2. Dra och släpp skräppost- eller nätfiskemeddelandet i det nya meddelandet. Då sparas skräppost- eller nätfiskemeddelandet som en bifogad fil i det nya meddelandet. Kopiera inte och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan granska meddelanderubrikerna).

   > [!NOTE]
   >
   > - Du kan bifoga flera meddelanden i det nya meddelandet. Kontrollera att alla meddelanden har samma typ: nätfiskemeddelanden eller skräppost.
   >
   > - Lämna brödtexten i det nya meddelandet tom.
   >
   > - Använd antingen .msg-format (standardformatet i Outlook) eller .eml-format (standardformatet i Outlook på webben) för bifogade meddelanden.

3. Klicka på Skicka när du är **klar.**

> [!TIP]
> Administratörer kan blockera specifika meddelanden som felaktigt stavas som skräppost på flera olika sätt. Mer information finns i [Skapa listor med spärrade avsändare i EOP.](create-block-sender-lists-in-office-365.md)

## <a name="submit-false-positives-to-microsoft"></a>Skicka falska positiva resultat till Microsoft

> [!TIP]
> I stället för att använda följande procedurer för att rapportera falska positiva resultat kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tillägget Rapportmeddelande eller tillägget Rapport nätfiske. Mer information om hur du installerar [](enable-the-report-message-add-in.md) och använder de här verktygen finns i Aktivera tillägget Rapportmeddelande och Aktivera tillägget [Rapport nätfiske.](enable-the-report-phish-add-in.md)


Om ett meddelande felaktigt identifierats som skräppost kan du skicka meddelandet till Microsofts team för skräppostanalys. Analytikerna kommer att utvärdera meddelandet och (beroende på resultatet av analysen) kan filtren för hela tjänsten justeras så att meddelandet tillåts.

1. Skapa ett nytt, tomt e-postmeddelande `not_junk@office365.microsoft.com` med mottagaren:

2. Dra och släpp det felidentifierade meddelandet i det nya meddelandet. Då sparas det felidentifierade meddelandet som en bifogad fil i det nya meddelandet. Kopiera inte och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan granska meddelanderubrikerna).

   > [!NOTE]
   >
   > - Du kan bifoga flera meddelanden i det nya meddelandet. Kontrollera att alla meddelanden har samma typ: nätfiskemeddelanden eller skräppost.
   >
   > - Lämna brödtexten i det nya meddelandet tom.
   >
   > - Använd antingen .msg-format (standardformatet i Outlook) eller .eml-format (standardformatet i Outlook på webben) för bifogade meddelanden.

3. Klicka på Skicka när du är **klar.**

> [!TIP]
> Administratörer kan tillåta filtrering av skräppost på flera olika sätt. Mer information finns i [Skapa listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Var lagras data från inskickade data till Microsoft?

Data finns i Efterlevnadsgränsen för Office 365 i nordamerikas datacenter. Data granskas av analytiker i teknikteamet för att hjälpa till att göra filtren mer effektiva.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Skapa en e-postflödesregel för att ta emot kopior av meddelanden som rapporterats till Microsoft

Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
