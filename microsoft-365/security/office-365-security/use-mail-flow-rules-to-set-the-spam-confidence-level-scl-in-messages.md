---
title: Använd regler för e-postflöde för att ställa in scl (Spam Confidence Level) i meddelanden
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du ställer in SCL för meddelanden i Exchange Online Protection.
ms.openlocfilehash: 10440d5ac8cd57388f4550f21ca72ce7aa1a2745
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806467"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>Använd regler för e-postflöde för att ställa in scl (Spam Confidence Level) i meddelanden

Du kan skapa en regel för e-postflöde (kallas även en transportregel) som anger åtkomstnivån för skräppost (SCL) för ett e-postmeddelande. SCL är ett mått på hur sannolikt ett meddelande är att vara spam. Skräppost är oönskade (och vanligtvis oönskade) e-postmeddelanden. Tjänsten vidtar olika åtgärder på ett meddelande beroende på dess SCL-klassificering. Du kanske till exempel vill kringgå filtrering av skräppostinnehåll för meddelanden som skickas från personer i organisationen eftersom du litar på att ett meddelande som skickas internt från en kollega inte är skräppost. Genom att använda regler för e-postflöde för att ange SCL-värdet för ett meddelande får du ökad kontroll över hanteringen av skräppost.

 **Vad behöver du veta innan du börjar?**

- Beräknad tid för att slutföra denna procedur: 10 minuter.

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Information om vilka behörigheter du behöver finns i posten "E-postflödesregler" i [Funktionsbehörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) eller [Funktionsbehörigheter i EOP](feature-permissions-in-eop.md).

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Så här skapar du en regel för e-postflöde som anger SCL för ett meddelande

1. Välj Regler för **e-postflöde** \> i Administrationscentret för Exchange **.**

2. Välj **Ny**![](../../media/ITPro-EAC-AddIcon.gif)lägg till ikon och välj sedan **Skapa en ny regel**.

3. Ange ett namn för regeln.

4. Välj **Fler alternativ**och ange sedan ett villkor som utlöser åtgärden som du ska ange för den här regeln (som ska anges i SCL-värdet) under Använd den här **regeln**om du anger ett villkor som utlöser den åtgärd som ska utlösas för den här regeln (som ska anges i SCL-värdet).

   Du kan till exempel ange **att avsändaren** \> **är intern/extern**och sedan väljer **du Inuti organisationen**i dialogrutan Välj **avsänaresplats** och väljer **ok**.<br/>
   ![Välj avsändningsplats](../../media/EOP-ETR-SetSCL-1.jpg)

5. Under **Gör följande**väljer du Ändra **meddelandeegenskaperna** \> som **säkerhetsnivå för skräppost (SCL)**.

6. Markera ett av följande värden i rutan **Ange SCL** och välj **OK:**

   - **Bypass spam filtrering:** Detta ställer in SCL till -1, vilket innebär att innehållsfiltrering inte kommer att utföras.

   - **0-4**: Meddelandet skickas vidare till innehållsfiltret för ytterligare bearbetning.

   - **5-6**: Åtgärden som anges för **skräppost** i tillämpliga innehållsfilterpolicyer kommer att tillämpas. Som standard är åtgärden att skicka meddelandet till mottagarens skräppostmapp.

   - **7-9**: Åtgärden som anges för **Skräppost med högt förtroende** i tillämpliga innehållsfilterpolicyer kommer att tillämpas. Som standard är åtgärden att skicka meddelandet till mottagarens skräppostmapp.

   Mer information om hur du konfigurerar innehållsfilterprinciper finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md). Mer information om SCL-värden i tjänsten finns i [Säkerhetsnivåer för skräppost](spam-confidence-levels.md).

7. Ange ytterligare egenskaper för regeln och välj **spara**.

   > [!TIP]
   > Mer information om de ytterligare egenskaper som du kan välja eller ange för den här regeln finns i [Använda EAC för att skapa regler för e-postflöde](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du vill kontrollera att den här proceduren fungerar korrekt skickar du ett e-postmeddelande till någon i organisationen och kontrollerar att åtgärden som utförs i meddelandet är som förväntat. Om du till exempel **ställer in scl (Spam Confidence Level)** på **Kringgå skräppostfiltrering**ska meddelandet skickas till den angivna mottagarens inkorg. Men om du **ställer in spam förtroendenivå (SCL)** till **9**, och **hög förtroende spam** åtgärder för din tillämpliga innehåll filter politik är att flytta meddelandet till mappen Skräppost, då meddelandet ska skickas till den angivna mottagarens skräppostmapp.
