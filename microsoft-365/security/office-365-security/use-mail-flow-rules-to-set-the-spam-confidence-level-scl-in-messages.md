---
title: Använda regler för e-postflöde till SCL i meddelanden
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
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du ställer in SCL för meddelanden i Exchange Online Protection.
ms.openlocfilehash: b7ea9a0f046e5a48f0de8d4ac9ae6d53821f03c0
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895101"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>Använd regler för e-postflöde för att ställa in scl (Spam Confidence Level) i meddelanden

Om du är office 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection-kund (EOP) utan Exchange Online-postlådor använder EOP policyer mot skräppost (kallas även principer för skräppostfilter eller innehållsfilterprinciper) för att skanna inkommande meddelanden för skräppost. Mer information finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).

Om du vill markera specifika meddelanden som skräppost innan de ens skannas av skräppostfiltrering eller markera meddelanden så att de hoppar över skräppostfiltrering kan du skapa regler för e-postflöde (kallas även transportregler) för att identifiera meddelandena och ställa in säkerhetsnivån för skräppost (SCL). Mer information om SCL finns [i SCL (Spam Confidence Level) i Office 365](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste tilldelas behörigheter i Exchange Online innan du kan göra dessa procedurer. Du måste ha tilldelats rollen **Transportregler,** som tilldelas rollerna **Organisationshantering,** **Efterlevnadshantering**och **Arkivhandling** som standard. Mer information finns [i Hantera rollgrupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Information om hur du öppnar EAC i Exchange Online finns [i Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Mer information om regler för e-postflöde i Exchange Online finns [i Regler för e-postflöde (transportregler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Använda EAC för att skapa en regel för e-postflöde som anger SCL för ett meddelande

1. Gå till **Regler för** **e-postflöde** \> i EAC .

2. Klicka på](../../media/ITPro-EAC-AddIcon.png) Ikonen Lägg **till** ![och välj sedan Skapa en ny **regel**.

3. Konfigurera följande inställningar på sidan **Ny regel** som öppnas:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln.

   - Klicka på **Fler alternativ**.

   - **Använd den här regeln om**: Välj ett eller flera villkor för att identifiera meddelanden. Mer information finns i [Villkor och undantag för regel för e-postflöde (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Gör följande:** Välj **Ändra meddelandeegenskaperna** \> **ange scl (Spam Confidence Level)**. Konfigurera ett av följande värden i dialogrutan **Ange SCL** som visas:

   - **Bypass spam filtrering:** Detta ställer in SCL till -1, vilket innebär att meddelandena kommer att hoppa över spam filtrering.

     > [!CAUTION]
     > Var mycket försiktig med att tillåta meddelanden att hoppa över skräppostfiltrering. Angripare kan använda det här säkerhetsproblemet för att skicka nätfiske och andra skadliga meddelanden till din organisation. Reglerna för e-postflöde kräver mer än bara avsändarens e-postadress eller domän. Mer information finns [i Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365.md).

   - **0 till 4**: Meddelandet skickas via skräppostfiltrering för ytterligare bearbetning.

   - **5 eller 6**: Meddelandet är markerat som **spam**. Åtgärden som du har konfigurerat för skräppostfiltreringsutslag i dina anti-spam-principer tillämpas på meddelandet (standardvärdet är **Flytta meddelande till mappen Skräppost**). **Spam**

   - **7 till 9:** Meddelandet är markerat som **Hög förtroende spam**. Åtgärden som du har konfigurerat för skräppostfiltreringsdomar med **högt förtroende** i dina anti-spam-principer tillämpas på meddelandet (standardvärdet är **Flytta meddelande till mappen Skräppost).**

4. Ange eventuella ytterligare egenskaper som du vill ha för regeln. Klicka på **Spara** när du är klar.

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du vill kontrollera att den här proceduren fungerar korrekt skickar du ett e-postmeddelande till någon i organisationen och kontrollerar att åtgärden som utförs i meddelandet är som förväntat. Om du till exempel **ställer in scl (Spam Confidence Level)** på **Kringgå skräppostfiltrering**ska meddelandet skickas till den angivna mottagarens inkorg. Men om du **ställer in spam förtroendenivå (SCL)** till **9**, och **hög förtroende spam** åtgärder för din tillämpliga innehåll filter politik är att flytta meddelandet till mappen Skräppost, då meddelandet ska skickas till den angivna mottagarens skräppostmapp.
