---
title: Ge behörigheter för postlådor åt en annan användare – administratörshjälp
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Lär dig hur du ger en användare rätt att komma åt en annan användares postlåda. Då kan användaren läsa e-postmeddelanden och skicka e-postmeddelanden från den andra användarens postlåda. '
ms.openlocfilehash: e6b94d4e24b0ff1d5dc397ccbcfba98929a303f2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925548"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a>Ge behörigheter för postlådor åt en annan användare – administratörshjälp

Som administratör kanske du behöver ge vissa användare åtkomst till andra användares postlåda. Du kanske till exempel vill låta en assistent kunna skicka och läsa e-post från sin chefs postlåda eller ge någon av dina användare möjlighet att skicka e-post åt en annan användare. I det här avsnittet får du se hur du ska göra.
  
Om du letar efter information om att skapa och hantera delade postlådor kan du läsa [Skapa en delad postlåda](../email/create-a-shared-mailbox.md).
    
## <a name="looking-to-set-up-mailbox-permissions"></a>Vill du konfigurera behörigheter till postlådor?

Med behörigheter till postlådor kan du ge en annan användare läs-och skrivbehörighet till en postlåda. Artiklarna nedan kan hjälpa dig att konfigurera och använda den här funktionen:
  
 **Konfigurera behörigheterna:**
  
Det första steget för att ställa in behörigheter är att bestämma vilka åtgärder du vill att andra användare ska kunna vidta i en viss postlåda. Du kan tillåta en användare att läsa e-postmeddelanden från postlådan, skicka e-postmeddelanden för en annan användare och skicka e-postmeddelanden som om de skickades från postlådan. Se följande artiklar om hur du ställer in de olika typerna av behörighet:
  
- [Läsa e-post från en annan användares postlåda](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [Skicka e-post från en annan användares postlåda](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [Skicka e-post åt en annan användare](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **Spridning av ändringar:**
  
När du har konfigurerat behörigheter kan det ta upp till 60 minuter innan ändringarna har spridits i systemet.
  
 **Hur du använder funktionen när behörigheter har konfigurerats:**
  
Det finns några olika sätt att komma åt en postlåda när du har fått åtkomst. Mer information om detta finns i den här artikeln: [Tillgång till en annan persons postlåda](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).

> [!NOTE]
> Behörigheterna kan bara konfigureras i den aktuella organisationens klient organisation. Det är inte möjligt att ställa in brevlådesbehörigheter hos uthyresanvändare.
  
## <a name="send-email-from-another-users-mailbox"></a>Skicka e-post från en annan användares postlåda

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.  
    
2. Välj namnet på användaren (från vilken du vill ge en sändningsbehörighet) för att öppna fönstret Egenskaper.
    
3. På fliken **E-post** väljer du **Hantera postlådebehörigheter**.

4. Bredvid **Skicka som** väljer du **Redigera**. 

5. Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som. 
    
6. Välj **Spara**.
 
::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.  

2. Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.

3. Bredvid **Skicka som** väljer du **Redigera**. 

4. Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som. 
    
5. Välj **Spara**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>. 

2. Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.

3. Bredvid **Skicka som** väljer du **Redigera**. 

4. Välj **Lägg till behörigheter** och välj sedan namnet på den person som du vill att den här användaren ska kunna skicka som. 
    
5. Välj **Spara**.

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a>Läsa e-post i en annan användares postlåda

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.  
    
2. Välj namnet på användaren (vars postlåda ska vara tillåten att läsa) för att öppna fönstret Egenskaper.
    
3. På fliken **E-post** väljer du **Hantera postlådebehörigheter**.
    
4. Bredvid **Läs och hantera** väljer du **Redigera**. 
    
5. Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.

6. Välj **Spara**.


> [!NOTE]
> **Läsa** och **hantera** behörigheter kallas **full åtkomstbehörighet** när de beviljas i Exchange-administratörscentret. Fullständig åtkomst ger inte behörighet att **skicka som** eller **skicka för** behörigheter.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.  
  
2. Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.
    
3. Bredvid **Läs och hantera** väljer du **Redigera**. 
    
4. Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.

5. Välj **Spara**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>. 
  
2. Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.
    
3. Bredvid **Läs och hantera** väljer du **Redigera**. 
    
4. Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att läsa e-post från den här postlådan.

5. Välj **Spara**.

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a>Skicka e-post för en annan användare

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.  

2. Välj namnet på användaren (från vilken du vill ge behörigheten **Skicka för**) för att öppna fönstret Egenskaper.
    
3. På fliken **E-post** väljer du **Hantera postlådebehörigheter**.
    
4. Bredvid **Skicka för** väljer du **Redigera**.

5. Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.

6. Välj **Spara**.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.  

2. Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.

3. Bredvid **Skicka för** väljer du **Redigera**.
    
4. Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.

5. Välj **Spara**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>. 

2. Välj önskad användare, expandera **E-postinställningar** och välj sedan **Redigera** bredvid **Postlådebehörigheter**.

3. Bredvid **Skicka för** väljer du **Redigera**.
    
4. Välj **Lägg till behörigheter** och välj sedan namnet på den eller de användare du vill ge tillåtelse att skicka e-post för den här postlådan.

5. Välj **Spara**.

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a>Skicka och läsa från Outlook och Outlook på webben för företag


Vill du veta hur du skickar e-post från en annan användares postlåda? Läs följande avsnitt:
  
- [Hantera andra personers e-post- och kalenderobjekt](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [Skicka e-post från en annan person eller grupp](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
