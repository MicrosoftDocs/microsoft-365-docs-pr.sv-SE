---
title: Använda e-postflödesregler till SCL i meddelanden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Lär dig hur du skapar e-postflödesregler (transportregler) för att identifiera meddelanden och ange SCL (Spam Confidence Level) för meddelanden i Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aa2893214543f77114d517dc38f874d6172a920a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287563"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Använda e-postflödesregler för att ange konfidensnivån för skräppost (SCL) i meddelanden i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor använder EOP principer för skräppostskydd (kallas även principer för skräppostfilter eller innehållfilterprinciper) för att söka igenom inkommande meddelanden efter skräppost. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

Om du vill markera vissa meddelanden som skräppost innan de ens genomsöks av skräppostfiltrering eller markerar meddelanden så att de hoppar över skräppostfiltreringen kan du skapa e-postflödesregler (kallas även transportregler) för att identifiera meddelandena och ange SCL (Spam Confidence Level). Mer information om SCL finns i [SCL (Spam Confidence Level) i EOP.](spam-confidence-levels.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste ha tilldelats behörigheter i Exchange Online eller Exchange Online Protection innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du rollen **Transportregler,** som tilldelas rollgrupperna Organisationshantering, Efterlevnadshantering **(globala** administratörer) och Hantering **av** arkivhandlingar som standard.

  Mer information finns i följande avsnitt:

  - [Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Behörigheter i fristående EOP](feature-permissions-in-eop.md)
  - [Använd EAC för att ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Information om hur du öppnar EAC i Exchange Online finns [i administrationscentret för Exchange i Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center) Information om hur du öppnar EAC i fristående EOP finns i [administrationscentret för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Mer information om e-postflödesregler i Exchange Online och Exchange Online Protection finns i [E-postflödesregler (transportregler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Använda EAC för att skapa en e-postflödesregel som anger SCL för ett meddelande

1. Gå till E-postflödesregler **i** \> EAC.

2. Klicka **på ikonen** Lägg till lägg till och välj sedan Skapa en ny ![ ](../../media/ITPro-EAC-AddIcon.png) **regel.**

3. Konfigurera **följande inställningar** på sidan Ny regel som öppnas:

   - **Namn:** Ange ett unikt, beskrivande namn för regeln.

   - Klicka **på Fler alternativ.**

   - **Använd den här regeln om:** Markera ett eller flera villkor för att identifiera meddelanden. Mer information finns i Villkoren [för e-postflödesregel och undantag (predikat) i Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

   - **Gör följande:** Välj **Ändra meddelandeegenskaperna** \> **som anger skräppostförtroendenivån (SCL).** I dialogrutan **Ange SCL** som visas konfigurerar du något av följande värden:

   - **Kringgå skräppostfiltrering:** Meddelandena hoppar över skräppostfiltrering.

     > [!CAUTION]
     > Var mycket noga med att tillåta att meddelanden hoppar över skräppostfiltrering. Attacker kan använda det här problemet för att skicka nätfiske och andra skadliga meddelanden till organisationen. E-postflödesregler kräver mer än bara avsändarens e-postadress eller domän. Mer information finns i Skapa [listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)

   - **0 till 4:** Meddelandet skickas via skräppostfiltrering för ytterligare bearbetning.

   - **5 eller 6:** Meddelandet markeras som **skräppost.** Åtgärden som du har konfigurerat  för skräppostfiltreringsval i principerna för skräppostskydd tillämpas på meddelandet (standardvärdet är Flytta meddelandet till mappen **Skräppost).**

   - **7 till 9:** Meddelandet markeras som **skräppost med hög konfidens.** Åtgärden som du har konfigurerat  för skräppostfiltrering med hög konfidens i principerna för skräppostskydd tillämpas på meddelandet (standardvärdet är Flytta meddelandet till mappen **Skräppost).**

4. Ange ytterligare egenskaper som du vill använda för regeln. Klicka på **Spara** när du är klar.

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrollera att den här proceduren fungerar korrekt genom att skicka ett e-postmeddelande till någon i organisationen och kontrollera att åtgärden som utförts för meddelandet är som förväntat. Om du till exempel anger att skräppostförtroendenivån **(SCL)** ska kringgå **skräppostfiltrering** ska meddelandet skickas till den angivna mottagarens inkorg. Men om du ställer in skräppostförtroendenivån **(SCL)** på **9** och åtgärden hög konfidens för dina tillämpliga principer för skräppost är att flytta meddelandet till mappen Skräppost, ska meddelandet skickas till den angivna mottagarens skräppostmapp. 
