---
title: Vad &apos; är skillnaden mellan skräp post och Mass utskick?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om skillnaderna mellan skräp post och Mass utskick (Gråskala) i Exchange Online Protection (EOP).
ms.openlocfilehash: 17e6223175013678f389c0d7624cc4e4f4476f98
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826735"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Vad är skillnaden mellan skräp post och Mass utskick i EOP?

I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor ber kunderna dig ibland: "Vad är skillnaden mellan skräp post och Mass utskick?" I det här avsnittet beskrivs skillnaden och beskriver de kontroller som är tillgängliga i EOP.

- **Skräp posten** är skräp post, som inte är efterfrågad och är universellt oönskade (när den identifieras korrekt). Som standard avvisar EOP inte skräp post baserat på e-postserverns rykte. Om ett meddelande skickar en käll-IP-kontroll skickas det till skräp post filtrering. Om meddelandet klassificeras som skräp post genom filtrering av skräp post är meddelandet (som standard) levererat till mottagarna och flyttas till mappen skräp post.

  - Du kan konfigurera åtgärderna så att de tas med i spam verdicts. Anvisningar finns i [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).

  - Om du inte samtycker till Verdict spam kan du rapportera meddelanden som du anser vara skräp post eller icke-skräp post till Microsoft på flera sätt, enligt beskrivningen i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

- **Mass utskick via e-post** (kallas även _grå e-post_) är svårare att klassificera. Skräp post är ett konstant hot, Mass utskick är ofta en engångs annonsering eller marknadsförings meddelande. Vissa användare vill ha Mass utskick av e-post (och faktiskt har de tagit emot dem) medan andra användare anser att Mass utskick av e-post. Vissa användare vill till exempel ta emot reklam meddelanden från Contoso Corporation eller inbjudningar till en kommande konferens på cyberterrorism säkerhet, medan andra användare anser att samma meddelande ska vara skräp post.

  Mer information om hur Mass utskick identifieras finns i bulk- [nivå (BCL) i EOP](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Hantera Mass utskick

På grund av den blandade högreaktioner till Mass utskick av e-post är det inte till hjälp för varje organisation.

Skydd mot skräp post har en standard tröskel för BCL som används för att identifiera Mass utskick via e-post. Administratörer kan öka eller minska tröskelvärdet. Mer information finns i följande avsnitt:

- [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).

- [EOP princip inställningar för skräp post](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Ett annat alternativ som är lätt att missa: om en användare klagande tar emot Mass utskick, men meddelanden kommer från välkända avsändare som skickar skräp post filtrering i EOP, måste användaren kontrol lera om det finns ett alternativ för att avbryta prenumerationen i e-postmeddelandet.
