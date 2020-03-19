---
title: Konfigurera skräppostmeddelanden från slutanvändare i EOP
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
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: Du kan konfigurera skräppostmeddelanden för slutanvändare för standardprincipen för företagsomfattande innehållsfilter eller för anpassade innehållsfilterprinciper som tillämpas på domäner.
ms.openlocfilehash: 6ac43ee3419e7b768312b6826994a5b8f5e4a231
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808622"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a>Konfigurera skräppostmeddelanden från slutanvändare i EOP
  
> [!IMPORTANT]
> Det här avsnittet gäller fristående Exchange Online Protection (EOP) som skyddar lokala postlådor. Exchange Online-kunder som skyddar molnbaserade postlådor bör läsa följande ämne i stället: [Konfigurera skräppostmeddelanden för slutanvändare i Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 
  
Du kan konfigurera skräppostmeddelanden för slutanvändare för standardprincipen för skräppostfilter för hela företaget eller för anpassade principer för skräppostfilter. Genom att aktivera meddelanden om skräppost från slutanvändaren kan användarna hantera sina egna meddelanden om skräppost, bulk och nätfiske i karantän. 
  
Skräppostmeddelanden från slutanvändare innehåller en lista över alla meddelanden om skräppost i karantän som slutanvändaren har fått under en tidsperiod som du konfigurerar (du kan ange ett värde mellan 1 och 15 dagar). Du kan också konfigurera det språk på vilket meddelandet skrivs.
  
När slutanvändarna har fått ett meddelande kan de välja mellan följande alternativ:

**Blockera avsändare** om du vill att Office 365 ska lägga till avsändaren i listan över blockerade avsändare.

**Släpp** om meddelandet inte är skräppost och du vill att Office 365 ska skicka meddelandet till postlådan.

**Granska** för att navigera till karantänportalen i Säkerhets- och efterlevnadscenter om du vill vidta andra åtgärder, till exempel Förhandsgranska eller Släpp.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?
<a name="sectionSection0"> </a>

Beräknad tid att slutföra: 5 minuter
  
Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Om du vill se vilka behörigheter du behöver läser du posten "Anti-spam" i [funktionsbehörigheterna i EOP-avsnittet.](feature-permissions-in-eop.md) 
  
Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i [Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Använd EAC för att konfigurera skräppostmeddelanden från slutanvändare

1. I Exchange Admin Center (EAC) navigerar du till > **skräppostfiltret**. **Protection**
    
2. Välj den innehållsfilterprincip som du vill aktivera skräppostmeddelanden från slutanvändare (de inaktiveras som standard).
    
3. Klicka på länken **Konfigurera skräppostmeddelanden** för slutanvändare i det högra fönstret, där sammanfattningsinformationen om din policy visas. 
    
4. I den efterföljande dialogrutan kan du konfigurera följande alternativ:
    
1. **Aktivera skräppostmeddelanden från slutanvändare** Markera den här kryssrutan för att aktivera skräppostmeddelanden från slutanvändaren för den här principen. (Omvänt, om den här principen är aktiverad, kan du avmarkera den här kryssrutan för att inaktivera skräppostmeddelanden för slutanvändare för den här principen.) 
    
2. **Skicka skräppostmeddelanden för slutanvändare varje (dagar)** Ange hur ofta skräppostmeddelanden ska skickas. Standardär 3 dagar. Du kan ange mellan 1 och 15 dagar. Om du till exempel anger 7 dagar innehåller meddelandet en lista över alla meddelanden som är avsedda för användaren under de senaste 7 dagarna som skickades till skräppostkarantänen i stället. 
    
3. **Meddelandespråk** Med hjälp av listrutan väljer du det språk på vilket du vill skriva skräppostmeddelanden för slutanvändaren för den här principen. 
    
5. Klicka på **Spara**. En sammanfattning av inställningarna för innehållsfilter, inklusive inställningarna för skräppostmeddelanden från slutanvändaren, visas i den högra rutan.
    
> [!NOTE]
>  Skräppostmeddelanden från slutanvändare fungerar bara för innehållsfilterprinciper som är aktiverade. > slutanvändare sa skräppostmeddelanden endast en gång per dag. Leveranstiden för meddelandet kan inte garanteras för någon specifik kund och kan inte konfigureras. 
  
 **Tips:** Om du vill testa skräppostmeddelanden från slutanvändare genom att skicka dem till en begränsad uppsättning användare innan de implementeras fullt ut skapar du en policy för anpassat innehållsfilter som gör det möjligt för skräppostmeddelanden från slutanvändaren för de domäner där användarna finns. Skapa sedan en regel ** \> **för e-postflöde (kallas även en transportregel) i EAC-flödesreglerna för att blockera meddelanden från quarantine@messaging.microsoft.com (e-postadressen som skickar meddelanden) med undantag för de användare som du vill ta emot meddelandena. Följande bild är ett exempel på att skapa ett undantag för två användare (SaraD och AlexD) från domän Contoso.com: 
  
![Transportregel för att testa skräppostmeddelanden för slutanvändare](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>Mer information

[Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md)
  
