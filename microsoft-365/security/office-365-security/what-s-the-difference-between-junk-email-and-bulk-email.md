---
title: Vad är skillnaden mellan skräppost och massutskick av e-post?
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: I det här avsnittet beskrivs skillnaden mellan skräppost (skräppost) och massutskick av e-post och relaterade kontroller i Office 365.
ms.openlocfilehash: 41dedd02febc40b73dc585961487f89bbc6db54a
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/11/2020
ms.locfileid: "43230962"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>Vad är skillnaden mellan skräppost och massutskick av e-post?

Office 365-kunder med postlådor i Exchange Online eller fristående Exchange Online Protection -kunder utan Exchange Online-postlådor frågar ibland: "Vad är skillnaden mellan skräppost och massutskick av e-post?" Det här avsnittet förklarar skillnaden och beskriver de kontroller som är tillgängliga i EOP.

- **Skräppost** är skräppost, som är oönskade och allmänt oönskade meddelanden (när de identifieras korrekt). Som standard avvisar EOP skräppost baserat på ryktet för käll-e-postservern. Om ett meddelande skickas källa IP-inspektion, det skickas till spam filtrering. Om meddelandet klassificeras som skräppost genom skräppostfiltrering levereras meddelandet (som standard) till de avsedda mottagarna och flyttas till mappen Skräppost.

  - Du kan konfigurera de åtgärder som ska vidtas för att filtrera domar för skräppost. Instruktioner finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).

  - Om du inte håller med om omdömet om skräppostfiltrering kan du rapportera meddelanden som du anser vara skräppost eller icke-skräppost till Microsoft på flera sätt, enligt beskrivningen i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

- **Massutskick av e-post** (kallas även _grå e-post)_ är svårare att klassificera. Medan spam är ett ständigt hot, bulk e-post är ofta engångsannonser eller meddelanden marknadsföring. Vissa användare vill ha massmeddelanden (och i själva verket har de medvetet registrerat sig för att ta emot dem), medan andra användare anser bulk e-post vara spam. Vissa användare vill till exempel ta emot annonsmeddelanden från Contoso Corporation eller inbjudningar till en kommande konferens om cybersäkerhet, medan andra användare anser att samma meddelanden är skräppost.

  Mer information om hur massutskick identifieras finns i [BCL (Bulk complaint level) i Office 365](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Så här hanterar du massutskick av e-post

På grund av den blandade reaktionen på massutskick av e-post finns det inte universell vägledning som gäller för varje organisation.

Anti-spam-policyer har en standard-BCL-tröskel som används för att identifiera massutskick av e-post som skräppost. Administratörer kan öka eller sänka tröskelvärdet. Mer information finns i följande avsnitt:

- [Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).

- [EOP:s policyinställningar för skräppost mot skräppost](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Ett annat alternativ som är lätt att förbise: om en användare klagar över att ta emot mass-e-post, men meddelandena är från välrenommerade avsändare som passerar skräppostfiltrering i EOP, har användaren kontrollera om ett alternativ för att avsluta prenumerationen i massmeddelandet.
