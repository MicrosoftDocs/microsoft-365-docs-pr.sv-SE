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
description: Lär dig hur du skapar e-postflödesregler (transportregler) för att identifiera meddelanden och ställa in SCL (Spam Confidence Level) för meddelanden i Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 795347046342ea17870e7758a6327facf51315a4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207210"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Använda e-postflödesregler för att ange konfidensnivån för skräppost (SCL) i meddelanden i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor använder EOP principer för skräppostskydd (kallas även principer för skräppostfilter eller principer för innehållsfilter) för att söka efter skräppost i inkommande meddelanden. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

Om du vill markera vissa meddelanden som skräppost innan de ens har genomsökts genom skräppostfiltrering, eller markera meddelanden så att de hoppar över skräppostfiltrering, kan du skapa e-postflödesregler (kallas även transportregler) för att identifiera meddelandena och ange SCL (Spam Confidence Level). Mer information om SCL finns i [SCL (Spam Confidence Level) i EOP.](spam-confidence-levels.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste ha tilldelats behörigheter i Exchange Online eller Exchange Online Protection innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du rollen **Transportregler,** som är tilldelad rollgrupperna **Organisationshantering,**  Efterlevnadshantering (globala administratörer) och **Hantering** av arkivhandlingar som standard.

  Mer information finns i följande avsnitt:

  - [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Behörigheter i fristående EOP](feature-permissions-in-eop.md)
  - [Använd EAC för att ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Information om hur du öppnar EAC i Exchange Online finns i [Administrationscenter för Exchange i Exchange Online.](/Exchange/exchange-admin-center) Information om hur du öppnar EAC i fristående EOP finns i [Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Mer information om e-postflödesregler i Exchange Online och Exchange Online Protection finns i [E-postflödesregler (transportregler) i Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Använda EAC för att skapa en e-postflödesregel som anger SCL för ett meddelande

1. Gå till E-postflödesregler **i** \> EAC.

2. Klicka **på ikonen** Lägg till lägg till och välj sedan Skapa en ny ![ ](../../media/ITPro-EAC-AddIcon.png) **regel.**

3. På sidan **Ny regel** som öppnas konfigurerar du följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln.

   - Klicka **på Fler alternativ.**

   - **Använd den här regeln om:** Välj ett eller flera villkor för att identifiera meddelanden. Mer information finns i Villkor [för e-postflödesregel och undantag (predikat) i Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

   - **Gör följande:** Välj **Ändra meddelandeegenskaperna** \> **för att ange SCL (Spam Confidence Level).** I dialogrutan **Ange SCL** konfigurerar du något av följande värden:

   - **Kringgå skräppostfiltrering:** Meddelandena hoppar över skräppostfiltrering.

     > [!CAUTION]
     > Var mycket noga med att tillåta meddelanden att hoppa över skräppostfiltrering. Attacker kan använda det här problemet för att skicka nätfiske och andra skadliga meddelanden till organisationen. E-postflödesreglerna kräver mer än bara avsändarens e-postadress eller domän. Mer information finns i Skapa [listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)

   - **0 till 4:** Meddelandet skickas via skräppostfiltrering för ytterligare bearbetning.

   - **5 eller 6:** Meddelandet markeras som **skräppost.** Åtgärden som du har konfigurerat  för skräppostfiltreringsval i dina principer mot skräppost tillämpas på meddelandet (standardvärdet är Flytta meddelandet till mappen **Skräppost).**

   - **7–9:** Meddelandet markeras som Skräppost **med hög konfidens.** Åtgärden som du har konfigurerat  för skräppostfiltrering av hög kvalitet i skräppostprinciperna tillämpas på meddelandet (standardvärdet är Flytta meddelandet till mappen **Skräppost).**

4. Ange ytterligare egenskaper som du vill använda för regeln. Klicka på **Spara** när du är klar.

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrollera att den här proceduren fungerar korrekt genom att skicka ett e-postmeddelande till någon i organisationen och kontrollera att åtgärden som utförts för meddelandet är som förväntat. Om du till exempel anger **SCL (Spam Confidence Level)** som Förbikoppling av **skräppostfiltrering** ska meddelandet skickas till den angivna mottagarens inkorg. Men om du ställer in konfidensnivån för skräppost **(SCL)** på **9** och åtgärden Hög förtroende för skräppostprinciperna för skräppost är att flytta meddelandet till mappen Skräppost ska meddelandet skickas till den angivna mottagarens skräppostmapp. 