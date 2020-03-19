---
title: Skicka e-post som en distributionslista i Office 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Läs mer om att skicka e-post som en distributionslista i Office 365.
ms.openlocfilehash: 076405b54f2a1521e0d9a1fc54c734b172eb82e8
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809073"
---
# <a name="send-email-as-a-distribution-list-in-office-365"></a>Skicka e-post som en distributionslista i Office 365

I Office 365 kan du skicka e-post som en distributionslista. När en person som är medlem i distributionslistan svarar på ett meddelande som skickas till distributionslistan, verkar e-postmeddelandet komma från distributionslistan, inte från den enskilda användaren. Det här avsnittet visar hur du gör detta.
  
## <a name="send-email-as-a-distribution-list"></a>Skicka e-post som en distributionslista

Innan du utför de här stegen kontrollerar du att du har lagts till i en Distributionslista för Office 365 och att du har beviljats Send som behörighet för den.
  
 **Administratörer**: Kontrollera att du har följt stegen i [Lägg till en Office 365-användare eller kontakt i en lista](../email/add-user-or-contact-to-distribution-list.md) och tillåt medlemmar att skicka [e-post som ett avsnitt i Office 365-gruppen](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) och lagt till rätt personer i distributionslistan.
  
1. Öppna Outlook på webben och gå till inkorgen. 
    
2. Öppna ett meddelande som skickades till distributionslistan. 
    
3. Välj **Svara**. 
    
4. Längst ned i meddelandet väljer du **Mer** \> **Visa från**.<br/> ![Välj Mer och välj sedan Visa från](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)
  
5. Högerklicka på Adressen Från - `Ina@weewalter.me` till exempel - och välj **Ta bort**.<br/> ![Ta bort FROM-aliaset](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)
  
6. Skriv sedan distributionslisteadressen, till exempel support@contoso.com och skicka meddelandet. Nästa gång du svarar från distributionslistan visas dess adress som ett alternativ i listan **Från.**<br/>![Alias för den delade postlådan visas](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)
  

