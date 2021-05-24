---
title: Skapa, redigera eller ta bort en säkerhetsgrupp i Microsoft 365 administrationscenter
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Lär dig att skapa, redigera eller ta bort en säkerhetsgrupp.
ms.openlocfilehash: 7887a6371287ebef3a91cc1a37f2ed696df1948d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624007"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>Skapa, redigera eller ta bort en säkerhetsgrupp i Microsoft 365 administrationscenter

På sidan Microsoft 365 **Grupper** kan du skapa grupper med användarkonton som du kan använda för att tilldela samma behörigheter till i SharePoint Online och CRM Online. En administratör kan till exempel skapa en säkerhetsgrupp för att bevilja en viss grupp personer åtkomst till en SharePoint webbplats. Endast globala administratörer och användarhanteringsadministratörer har behörighet att skapa, redigera eller ta bort säkerhetsgrupper. Mer information om administratörsroller finns i [Tilldela administratörsroller.](../add-users/assign-admin-roles.md) 
  
Det finns även [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som du kan använda för att skicka e-post eller tilldela behörighet till en grupp användare, samt [Grupper i Exchange Online och SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) som används för att bevilja användare behörighet och åtkomst till webbplatser och webbplatssamlingar. 
  
> [!IMPORTANT]
>  Planerar du att använda webbplatspostlådor? Alla användare som läggs till på en e-SharePoint-webbplats via en säkerhetsgrupp i stället för att läggas till individuellt kan endast använda webbplatspostlådan från SharePoint. De här användarna kan inte komma åt webbplatspostlådan från Outlook. Mer information finns i använda [grupper Microsoft 365 i stället för webbplatspostlådor.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b) 
  
## <a name="manage-security-groups-in-the-admin-center"></a>Hantera säkerhetsgrupper i administrationscentret

### <a name="add-a-security-group"></a>Lägga till en säkerhetsgrupp

1. I Microsoft 365 går du till **sidan Grupper**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupper.</a>
  
2. Välj Lägg **till** en grupp **på sidan Grupper.**
    
3. På sidan **Välj en grupptyp** väljer du **Säkerhet**. 
    
4. Följ anvisningarna för att slutföra skapandet av gruppen. 
 
### <a name="add-members-to-a-security-group"></a>Lägga till medlemmar i en säkerhetsgrupp
    
1. Välj namnet på säkerhetsgruppen på **sidan Grupper** och välj **Visa** alla och hantera medlemmar på **fliken Medlemmar.** 
    
2. Välj Lägg till  medlemmar i gruppfönstret och välj personen i listan eller skriv namnet  på den person du vill lägga till i sökrutan och välj sedan **Spara**.
    
    Om du vill ta bort medlemmar väljer du X bredvid namnet. 
  
### <a name="edit-a-security-group"></a>Redigera en säkerhetsgrupp

1. Gå till sidan Grupper i **administrationscentret.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>
  
2. Markera **gruppens** namn på sidan Grupper. 
    
3. I inställningsfönstret väljer du fliken **Allmänt eller** Fliken Medlemmar **för att** redigera antingen gruppinformation eller medlemmar.

### <a name="delete-a-security-group"></a>Ta bort en säkerhetsgrupp

1. Gå till sidan Grupper i **administrationscentret.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>
    
2. Markera **gruppens** namn på sidan Grupper. 
    
3. Välj **Ta bort grupp** (wasetbin-ikon) och bekräfta sedan genom att välja Ta **bort**.
    
    Välj **Stäng** när gruppen har tagits bort. 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Grupper i Exchange Online och SharePoint Online

Om du vill skapa grupper med användare så att du kan skicka e-post till dem samtidigt kan  du göra det i administrationscentret för Exchange genom att gå \> **till Admin Exchange** \> **Recipients** \> **Groups**. Välj sedan **Ny** ![ lägg till och välj den typ av grupp du ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) vill skapa: 
  
- **Distributionsgrupp**: Används för att distribuera meddelanden till en grupp användare. Det kallas även för en *e-postaktiverad distributionsgrupp* eller en *distributionslista.* Mer information finns i [Hantera distributionsgrupper](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).
    
- **Säkerhetsgrupp**: Kan användas för att distribuera meddelanden till en grupp användare och för att bevilja behörighet till resurser. Den här gruppen kallas även för *en e-postaktiverad säkerhetsgrupp.* Mer information finns i Hantera [e-postaktiverade säkerhetsgrupper.](/Exchange/recipients/mail-enabled-security-groups)
    
- **Dynamisk distributionsgrupp:** En typ av distributionsgrupp vars lista över mottagare beräknas om varje gång du skickar ett meddelande baserat på filter och villkor som du anger. Mer information finns i [Hantera dynamiska distributionsgrupper.](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)
    
När du har skapat distributionsgrupper och e-postaktiverade säkerhetsgrupper i Exchange administrationscenter visas deras namn och användarlistor på **sidan Säkerhetsgrupper.** Grupperna kan tas bort på båda platserna, men endast redigeras i administrationscentret för Exchange. Dynamiska distributionsgrupper visas inte på sidan **Säkerhetsgrupper.** 
  
 SharePoint-grupper skapas automatiskt när du skapar en webbplatssamling. De förinställda grupperna har standardbehörighetsnivåerna för användarnas behörighet och åtkomst i SharePoint - de här nivåerna kallas ibland SharePoint-roller. Mer information finns i [Standardgrupper SharePoint i SharePoint Online.](/sharepoint/default-sharepoint-groups)
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>Hur skiljer sig en säkerhetsgrupp från säkerhetsgrupper som jag skapar i SharePoint?

Säkerhetsgrupper kan användas med SharePoint, Exchange, MDM, Windows med mera. En säkerhetsgrupp som du skapar i SharePoint kan endast identifieras i den SharePoint-webbplatssamlingen.
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>Måste jag använda säkerhetsgrupper för min organisation för att vara säker?

Nej. Det här är ett annat sätt som du kan hantera säkerhet för din organisation. Du kan alltid bevilja användarbehörigheter och åtkomst till webbplatser individuellt. Men med säkerhetsgrupper kan du enkelt hantera större grupper med användare.
  
## <a name="can-i-send-email-to-a-security-group"></a>Kan jag skicka e-post till en säkerhetsgrupp?

Ja. Men om du vill använda grupper för e-post och samarbete rekommenderar vi att du [skapar en Microsoft 365 grupp](../create-groups/create-groups.md) i stället. 

## <a name="related-content"></a>Relaterat innehåll

[Skapa en grupp i Microsoft 365 administrationscenter](../create-groups/create-groups.md) (artikel)\
[Förklara Microsoft 365 grupper för användarna](../create-groups/explain-groups-knowledge-worker.md) (artikel)\
[Hantera en grupp i Microsoft 365 administrationscenter](../create-groups/manage-groups.md) (artikel)