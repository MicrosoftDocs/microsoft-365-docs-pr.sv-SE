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
description: Administratörer kan lära sig mer om skillnaderna mellan skräppost och massutskick (grå e-post) i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290651"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Vad är skillnaden mellan skräppost och massutskick i EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor frågar kunderna ibland: "Vad är skillnaden mellan skräppost och massutskick?" I det här avsnittet beskrivs skillnaden och de kontroller som är tillgängliga i EOP.

- **Skräppost är** skräppost, som är oönskade och oönskade oönskade meddelanden (när de identifieras korrekt). Som standard avvisas skräppost av EOP baserat på ryktet hos käll-e-postservern. Om ett meddelande klarar käll-IP-kontrollen skickas det till skräppostfiltrering. Om meddelandet klassificeras som skräppost med hjälp av skräppostfiltrering levereras meddelandet (som standard) till de avsedda mottagarna och flyttas till mappen Skräppost.

  - Du kan konfigurera åtgärderna för filtrering av skräppost. Instruktioner finns i Konfigurera [principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)

  - Om du inte är nöjd med skräppostfiltreringen kan du rapportera meddelanden som du anser vara skräppost eller icke-skräppost till Microsoft på flera olika sätt, enligt beskrivningen i Rapportera meddelanden och filer till [Microsoft.](report-junk-email-messages-to-microsoft.md)

- **Massutskick** (kallas även _grå post)_ är svårare att klassificera. Skräppost är ett konstant hot, men massutskick är ofta bara en gång reklam- eller marknadsföringsmeddelanden. Vissa användare vill att stora e-postmeddelanden (och faktiskt avsiktligt har registrerat sig för att ta emot dem), medan andra användare anser att massutskick är skräppost. Vissa användare vill till exempel få reklammeddelanden från Contoso Corporation eller inbjudningar till en kommande konferens om cybersäkerhet, medan andra användare ser samma meddelanden som skräppost.

  Mer information om hur massutskick identifieras finns i Nivå för gruppklagomål [(BCL) i EOP.](bulk-complaint-level-values.md)

## <a name="how-to-manage-bulk-email"></a>Hantera massutskick

På grund av den blandade reaktionen mot massutskick finns det inte någon universell vägledning som gäller för varje organisation.

Skräppostskyddsprinciper har en standardtröskel för BCL som används för att identifiera massutskick som skräppost. Administratörer kan öka eller minska tröskelvärdet. Mer information finns i följande avsnitt:

- [Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)

- [Principinställningar för EOP-skydd mot skräppost](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Ett annat alternativ som är lätt att missat: om en användare klagar på att få massutskick av e-post, men meddelandena kommer från betrodda avsändare som klarar skräppostfiltreringen i EOP, kan du be användaren att avregistrera sig från prenumerationen i massmeddelandet.
