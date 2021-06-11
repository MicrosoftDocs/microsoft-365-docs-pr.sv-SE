---
title: Vad &apos; är skillnaden mellan skräppost och massutskick?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan ta reda på skillnaderna mellan skräppost och massutskick (grå e-post) i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207553"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Vad är skillnaden mellan skräppost och massutskick i EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan kunderna ibland fråga: "Vad är skillnaden mellan skräppost och massutskick?" I det här avsnittet beskrivs skillnaden och de kontroller som är tillgängliga i EOP.

- **Skräppost är** skräppost, som är oönskade och oönskade oönskade meddelanden (när de identifieras korrekt). Som standard avvisar EOP skräppost baserat på ryktet hos käll-e-postservern. Om ett meddelande klarar käll-IP-kontrollen skickas det till skräppostfiltrering. Om meddelandet klassificeras som skräppost av skräppostfiltrering levereras meddelandet (som standard) till de avsedda mottagarna och flyttas till mappen Skräppost.

  - Du kan konfigurera åtgärderna för filtrering av skräppost. Anvisningar finns i Konfigurera [principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)

  - Om du inte håller med om skräppostfiltreringens bedömning kan du rapportera meddelanden som du anser vara skräppost eller icke-skräppost till Microsoft på flera olika sätt, enligt beskrivningen i Rapportera meddelanden och filer till [Microsoft.](report-junk-email-messages-to-microsoft.md)

- **Massutskick** (kallas även _grå e-post_) är svårare att klassificera. Skräppost är ett konstant hot, men massutskick är ofta bara reklam- eller marknadsföringsmeddelanden. Vissa användare vill ha massutskick av e-postmeddelanden (och faktiskt avsiktligt registrerat sig för att ta emot dem), medan andra användare anser att massutskick är skräppost. Vissa användare vill till exempel få reklammeddelanden från Contoso Corporation eller inbjudningar till en kommande konferens om cybersäkerhet, medan andra användare ser samma meddelanden som skräppost.

  Mer information om hur massutskick identifieras finns i Nivå för mass klagomål [(BCL) i EOP.](bulk-complaint-level-values.md)

## <a name="how-to-manage-bulk-email"></a>Hantera massutskick

På grund av den blandade reaktionen på massutskick finns det inte någon universell vägledning som gäller för alla organisationer.

Skräppostskyddsprinciper har en standardtröskel för BCL som används för att identifiera massutskick som skräppost. Administratörer kan öka eller minska tröskelvärdet. Mer information finns i följande avsnitt:

- [Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)

- [Principinställningar för skydd mot skräppost i EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

Ett annat alternativ som är lätt att missat: om en användare klagar på att få massutskick av e-post, men meddelandena kommer från betrodda avsändare som klarar skräppostfiltreringen i EOP, bör du be användaren att kontrollera prenumerationen i e-postmeddelandet med massutskick.
