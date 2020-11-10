---
title: 'Hantera din kunskaps Management Network (för hands version) '
description: Så här konfigurerar du kunskaps hantering.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 265816a8d3d04b8d10b529f1ea1a0b658aa2931d
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48989033"
---
# <a name="manage-your-knowledge-management-network-preview"></a>Hantera din kunskaps Management Network (för hands version)

> [!Note] 
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Läs mer om Project Cortex](https://aka.ms/projectcortex).


När du [har konfigurerat kunskaps hanteringen](set-up-topic-experiences.md)kan du när som helst göra ändringar i konfigurations inställningarna via administrations centret för Microsoft 365.

Du kan till exempel behöva justera dina inställningar för något av följande:
- Lägga till nya SharePoint-källor i mina avsnitt.
- Ändra vilka användare som ska ha åtkomst till ämnen.
- Ändra vilka användare som har behörighet att utföra uppgifter i ämnes centret.
- Ändra namnet på ämnes Center


## <a name="requirements"></a>Krav 
Du måste ha global administratör eller administratörs behörighet för SharePoint för att kunna komma åt Microsoft 365 Admin Center och hantera organisationens kunskaps uppgifter.


## <a name="to-access-knowledge-management-settings"></a>Så här använder du inställningar för kunskaps hantering:

1. I administrations centret för Microsoft 365 väljer du **Konfigurera** och sedan avsnittet **organisations** information.
2. I avsnittet **organisationsinformation** klickar du på **Anslut personer till kunskap**.<br/>

    ![Koppla personer till kunskap](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. På sidan **Anslut personer till kunskap** väljer du **Hantera** för att öppna fönstret **kunskaps nätverks inställningar** .<br/>

    ![kunskap – nätverks inställningar](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a>Ändra hur kunskaps nätverket hittar ämnen

Välj fliken **identifiering** om du vill uppdatera dina val för avsnitts källor i SharePoint. Med den här inställningen kan du välja vilka SharePoint-webbplatser i din klient organisation som ska crawlas och mined för avsnitt.

1. På fliken **identifiering** , under **Välj SharePoint-ämnes källor** , väljer du **Redigera**.
2. På sidan **Select SharePoint topic sources** väljer du vilka SharePoint-webbplatser som ska crawlas som källor för dina ämnen under identifiering. Detta inkluderar:</br>
    a. **Alla webbplatser** : alla SharePoint-webbplatser i din klient organisation. Här fångar du aktuella och framtida webbplatser.</br>
    b. **Alla, förutom markerade webbplatser** : Skriv namnen på de webbplatser du vill undanta.  Du kan också ladda upp en lista med webbplatser som du inte vill ska ingå i sökningen. Webbplatser som skapats i framtiden kommer att inkluderas som källor för avsnitts identifiering. </br>
    c. **Endast valda webbplatser** : Skriv in namnen på de webbplatser du vill ta med. Du kan också ladda upp en lista med webbplatser. Webbplatser som skapats i framtiden kommer inte att ingå som källor för identifiering av ämnen. </br>

    ![Välj hur du vill hitta ämnen](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    Om du har ett antal webbplatser som du vill undanta (om du markerar **alla, förutom markerade webbplatser** ) eller inkludera (om du valde **endast markerade webbplatser** ) kan du välja att överföra en CSV-fil med webbplats namn och URL-adresser. Du kan välja **Hämta webbplatsmall. csv** om du vill använda CSV-mallfilen.

3. Välj **Spara**.

##  <a name="change-who-can-see-topics-in-your-organization"></a>Ändra vem som kan se ämnen i din organisation

Välj fliken **identifiering** om du vill uppdatera vem i organisationen kan se upptäckta avsnitt i Sök Resultat och när ämnen markeras i innehåll som SharePoint-sidor.

1. På fliken **identifiering** , under **vem kan se ämnen i kunskaps nätverket** , väljer du **Redigera**.
2. På sidan **vem kan se ämnen i kunskaps nätverk** väljer du vilka som kommer att ha till gång till ämnen, till exempel markerade ämnen, ämnes kort, ämnes svar i sökningar och avsnitts sidor. Du kan välja:</br>
    a. **Alla i organisationen**</br>
    b. **Endast valda personer eller säkerhets grupper**</br>
    c. **Ingen**</br>

    ![Vilka som kan se ämnen](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. Välj **Spara**.  
 
> [!Note] 
> Med den här inställningen kan du välja en användare i organisationen, men endast användare som har kunskaps hanterings licenser tilldelade till dem kan visa ämnen.

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a>Ändra vem som har behörighet att utföra uppgifter i ämnes centret

Välj fliken **behörigheter för ämne** om du vill uppdatera vilka som har behörighet att göra följande på sidan avsnitts Center:

- Vilka användare som kan skapa och redigera ämnen: skapa nya avsnitt som inte hittades under identifiering eller redigera befintliga avsnitts sidor.
- Vilka användare som kan hantera ämnen: bekräfta eller avvisa upptäckta ämnen.

Så här uppdaterar du vilka som har behörighet att skapa och redigera ämnen:

1. På fliken **behörigheter** under **vem kan skapa och redigera ämnen** väljer du **Redigera**.</br>
2. På sidan **vem som kan skapa och redigera ämnen** kan du välja:</br>
    a. **Alla i organisationen**</br>
    b. **Endast valda personer eller säkerhets grupper**</br>

    ![Skapa och redigera ämnen](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. Välj **Spara**.</br>

Så här uppdaterar du vilka som har behörighet att hantera ämnen:

1. Välj **Redigera** under **vilka kan hantera ämnen** på fliken **behörigheter** .</br>
2. På sidan **vem kan hantera ämnen** kan du välja:</br>
    a. **Alla i organisationen**</br>
    b. **Markerade personer eller säkerhets grupper**</br>

    ![Hantera ämnen](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. Välj **Spara**.</br>


##  <a name="update-your-topic-center-name"></a>Uppdatera namnet på ämnes Center

Välj fliken för **avsnitts Center** om du vill uppdatera namnet på ditt ämnes Center. 

1. Välj **Redigera** under **ämnes Center namn** på fliken **ämnes Center** .
2. Skriv det nya namnet på ämnes centret i rutan **namn** på sidan **Redigera ämnes Center namn** .
3. Välj **Spara**

    ![Redigera namn på ämnes Center](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a>Se även



  






