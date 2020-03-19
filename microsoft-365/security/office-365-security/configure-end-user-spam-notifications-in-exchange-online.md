---
title: Konfigurera skräppostmeddelanden för slutanvändare i Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: Du kan konfigurera skräppostmeddelanden för slutanvändare för standardprincipen för skräppostfilter för hela företaget eller för anpassade principer för skräppostfilter som tillämpas på domäner.
ms.openlocfilehash: c8690a64e222bca2bbdc6be62d1077a9d361ae85
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/29/2020
ms.locfileid: "42811123"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Konfigurera skräppostmeddelanden för slutanvändare i Exchange Online

> [!IMPORTANT]
> Det här avsnittet är till Exchange Online-kunder som skyddar molnbaserade postlådor. Fristående exchange online protection (EOP) som skyddar lokala postlådor bör läsa följande ämne i stället: [Konfigurera skräppostmeddelanden för slutanvändare i EOP](configure-end-user-spam-notifications-in-eop.md). 
  
Du kan konfigurera skräppostmeddelanden för slutanvändare för standardprincipen för skräppostfilter för hela företaget eller för anpassade principer för skräppostfilter. Genom att aktivera skräppostmeddelanden för slutanvändare kan användarna hantera sina egna skräppost-, mass- och nätfiskemeddelanden i karantän.   
  
Skräppostmeddelanden för slutanvändare innehåller en lista över alla meddelanden som användaren har fått i skräppost i karantän under en tidsperiod som du konfigurerar (du kan ange ett värde mellan 1 och 15 dagar). Du kan också konfigurera det språk som meddelandet skrivs på.
  
När slutanvändarna har fått ett meddelande kan de välja mellan följande alternativ:

**Blockera avsändare** om du vill att Office 365 ska lägga till avsändaren i listan blockerade avsändare.

**Släpp** om meddelandet inte är skräppost och du vill att Office 365 ska skicka meddelandet till postlådan.

**Granska** om du vill navigera till karantänportalen i Security & Compliance Center om du vill vidta andra åtgärder, till exempel Förhandsgranska eller Släpp.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Beräknad tid att slutföra: 2 minuter
  
Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Information om vilka behörigheter du behöver finns i posten "Anti-spam" i [avsnittet Funktionsbehörigheter i Exchange Online.](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) 
  
Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Använda EAC för att konfigurera skräppostmeddelanden för slutanvändare

1. I Administrationscentret för Exchange (EAC) navigerar du till **filtret Skydds** \> **skräppost**.
    
2. Välj den policy för skräppostfilter som du vill aktivera skräppostmeddelanden för slutanvändare (de är inaktiverade som standard).
    
3. Klicka på länken **Konfigurera skräppostmeddelanden** i den högra rutan där sammanfattningsinformationen om din princip visas. 
    
4. I den efterföljande dialogrutan kan du konfigurera följande alternativ:
    
   - **Aktivera skräppostmeddelanden för slutanvändare** Markera den här kryssrutan för att aktivera skräppostmeddelanden för slutanvändare för den här principen. (Om den här principen är aktiverad kan du däremot avmarkera den här kryssrutan för att inaktivera skräppostmeddelanden för slutanvändare för den här principen.) 
    
   - **Skicka skräppostmeddelanden för slutanvändare varje (dagar)** Ange hur ofta slutanvändarnas skräppostmeddelanden ska skickas. Standardvärdet är 3 dagar. Du kan ange mellan 1 och 15 dagar. Om du till exempel anger 7 dagar innehåller meddelandet en lista över alla meddelanden som är avsedda för användaren under de senaste 7 dagarna som har skickats till skräppostkarantänen i stället. 
    
   - **Meddelandespråk** Med listrutan väljer du det språk på vilket du vill skriva skräppostmeddelanden för slutanvändare för den här principen. 
    
   - Klicka på **Spara**. En sammanfattning av dina principinställningar för skräppostfilter, inklusive inställningarna för skräppostmeddelanden för slutanvändare, visas i den högra rutan.
    
> [!NOTE]
>  Skräppostmeddelanden för slutanvändare fungerar bara för principer för skräppostfilter som är aktiverade. > Skräppostmeddelanden för slutanvändare skickas bara en gång per dag. Leveranstiden för meddelandet kan inte garanteras för en viss kund och kan inte konfigureras. 
  
 **Tips:** Om du vill testa skräppostmeddelanden för slutanvändare genom att skicka dem till en begränsad uppsättning användare innan du implementerar dem helt, skapar du en anpassad policy för skräppost för slutanvändare för de domäner där användarna finns. Skapa sedan en regel ** \> **för e-postflöde (kallas även transportregel) i EAC-reglerna för att blockera meddelanden från quarantine@messaging.microsoft.com (e-postadressen som skickar meddelanden) med undantag för de användare som du vill ta emot meddelandena. Följande bild är ett exempel på att skapa ett undantag för två användare (SaraD och AlexD) från domänen Contoso.com: 
  
![Transportregel för att testa skräppostmeddelanden för slutanvändare](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a>Använda SCC för att konfigurera skräppostmeddelanden för slutanvändare

Du kan också använda Security and Compliance Center (SCC) för att konfigurera skräppostmeddelanden för slutanvändare. Följ anvisningarna nedan:

1. Öppna Säkerhets- och efterlevnadscenter, navigera till policy **Policy** \> **mot** https://protection.office.com/antispamskräppost **för hothantering** \> eller använd direktlänken .

2. Klicka på nedpilen bredvid den skräppostfilterprincip som du vill aktivera skräppostmeddelanden för slutanvändare.

3. Klicka på länken **Konfigurera skräppostmeddelanden** för slutanvändare.

4. I den efterföljande dialogrutan kan du konfigurera följande alternativ:
    
   - **Aktivera skräppostmeddelanden för slutanvändare** Markera den här kryssrutan för att aktivera skräppostmeddelanden för slutanvändare för den här principen. (Om den här principen är aktiverad kan du däremot avmarkera den här kryssrutan för att inaktivera skräppostmeddelanden för slutanvändare för den här principen.) 
    
   - **Skicka skräppostmeddelanden för slutanvändare varje (dagar)** Ange hur ofta slutanvändarnas skräppostmeddelanden ska skickas. Standardvärdet är 3 dagar. Du kan ange mellan 1 och 15 dagar. Om du till exempel anger 7 dagar innehåller meddelandet en lista över alla meddelanden som är avsedda för användaren under de senaste 7 dagarna som har skickats till skräppostkarantänen i stället. 
    
   - **Meddelandespråk** Med listrutan väljer du det språk på vilket du vill skriva skräppostmeddelanden för slutanvändare för den här principen. 
    
   - Klicka på **Spara**. En sammanfattning av dina principinställningar för skräppostfilter, inklusive inställningarna för skräppostmeddelanden för slutanvändare, visas i fönstret.

## <a name="for-more-information"></a>Mer information

[Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md)

[Set-hostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)
  
