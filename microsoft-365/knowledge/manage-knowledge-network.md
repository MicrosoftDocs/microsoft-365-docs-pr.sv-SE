---
title: 'Hantera kunskapshanteringsnätverket(Förhandsgranska) '
description: Så här ställer du in Knowledge Management.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: 87275dba78ab402a9ea9553198ce1a84072e3351
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540124"
---
# <a name="manage-your-knowledge-management-network-preview"></a>Hantera ditt kunskapshanteringsnätverk (förhandsversion)

> [!Note] 
> Innehållet i den här artikeln är för Project Cortex Private Preview. [Läs mer om Project Cortex](https://aka.ms/projectcortex).


När du [har konfigurerat kunskapshantering](set-up-knowledge-network.md)kan en administratör när som helst efteråt göra justeringar i konfigurationsinställningarna via administrationscentret för Microsoft 365.

Du kan till exempel behöva justera inställningarna för något av följande:
- Lägg till nya SharePoint-källor i mina ämnen.
- Ändra vilka användare som ska ha åtkomst till ämnen.
- Ändra vilka användare som har behörighet att utföra uppgifter i ämnescentret.
- Ändra namnet på ditt ämnescenter


## <a name="requirements"></a>Krav 
Du måste ha behörigheten Global admin eller SharePoint för att kunna komma åt Microsoft 365-administrationscentret och hantera organisatoriska kunskapsuppgifter.


## <a name="to-access-knowledge-management-settings"></a>Så här kommer du åt kunskapshanteringsinställningarna:

1. I administrationscentret för Microsoft 365 väljer du **Installationsprogrammet**och visar sedan avsnittet **Organisationskunskap.**
2. Klicka på Anslut personer **till kunskap**i avsnittet **Organisationskunskap.**<br/>

    ![Koppla personer till kunskap](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. På sidan **Anslut personer till kunskap** väljer du **Hantera** för att öppna fönstret Inställningar **för kunskapsnätverk.**<br/>

    ![inställningar för kunskapsnätverk](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a>Ändra hur kunskapsnätverket kan hitta ämnen

Välj fliken **Ämnesidentifiering** om du vill uppdatera dina alternativ för SharePoint-ämneskällor. Med den här inställningen kan du välja de SharePoint-platser i din klientorganisation som ska genomsökas och brytas för ämnen.

1. Välj **Redigera**under **Välj SharePoint-ämneskällor**på fliken **Ämnesidentifiering** .
2. På sidan **Välj SharePoint-ämneskällor** väljer du vilka SharePoint-webbplatser som ska genomsökas som källor för dina ämnen under identifieringen. Detta inkluderar:</br>
    a. **Alla webbplatser:** Alla SharePoint-webbplatser i din klientorganisation. Detta fångar nuvarande och framtida webbplatser.</br>
    b. **Alla, utom valda platser:** Skriv namnen på de webbplatser som du vill utesluta.  Du kan också ladda upp en lista över webbplatser som du vill välja bort från identifiering. Webbplatser som skapas i framtiden kommer att inkluderas som källor för ämnesidentifiering. </br>
    c. **Endast valda platser:** Skriv namnen på de platser som du vill inkludera. Du kan också ladda upp en lista över webbplatser. Webbplatser som skapas i framtiden kommer inte att inkluderas som källor för ämnesidentifiering. </br>

    ![Välj hur du hittar ämnen](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    Om du har ett antal webbplatser som du vill utesluta (om du väljer **Alla, utom valda webbplatser)** eller inkluderar (om du har valt **Endast valda webbplatser)** kan du välja att ladda upp en CSV-fil med webbplatsnamn och webbadresser. Du kan välja **Hämta webbplatsmall .csv** om du vill använda CSV-mallfilen.

3. Välj **Spara**.

##  <a name="change-who-can-see-topics-in-your-organization"></a>Ändra vem som kan se ämnen i organisationen

Välj fliken **Ämnesidentifiering** om du vill uppdatera vem i organisationen som kan se upptäckta ämnen i sökresultaten och när ämnen markeras i innehåll som SharePoint-sidor.

1. Välj **Redigera**under **Vem kan se ämnen i kunskapsnätverket**på fliken **Ämnesidentifiering** .
2. På sidan Vem kan se ämnen på sidan **kunskapsnätverk** väljer du vem som ska ha tillgång till ämnesinformation, till exempel markerade ämnen, ämneskort, ämnessvar i sök- och ämnessidor. Du kan välja:</br>
    a. **Alla i organisationen**</br>
    b. **Endast markerade personer eller säkerhetsgrupper**</br>
    c. **Ingen**</br>

    ![Vem kan se ämnen](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. Välj **Spara**.  
 
> [!Note] 
> Med den här inställningen kan du välja en användare i organisationen, men endast användare som har kunskapshanteringslicenser som tilldelats dem kan visa ämnen.

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a>Ändra vem som har behörighet att utföra uppgifter i ämnescentret

Välj fliken **Ämnesbehörigheter** om du vill uppdatera vem som har behörighet att göra följande på ämnescentrets sida:

- Vilka användare kan skapa och redigera ämnen: Skapa nya ämnen som inte hittades under identifieringen eller redigera befintlig information om ämnessidan.
- Vilka användare kan hantera ämnen: Bekräfta eller avvisa identifierade ämnen.

Så här uppdaterar du vem som har behörighet att skapa och redigera ämnen:

1. Välj **Redigera**under Vem **kan skapa och redigera ämnen**på fliken **Ämnesbehörigheter** .</br>
2. På sidan **Vem kan skapa och redigera ämnen** kan du välja:</br>
    a. **Alla i organisationen**</br>
    b. **Endast markerade personer eller säkerhetsgrupper**</br>

    ![Skapa och redigera ämnen](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. Välj **Spara**.</br>

Så här uppdaterar du vem som har behörighet att hantera ämnen:

1. Välj **Redigera**under Vem **kan hantera ämnen**på fliken **Ämnesbehörigheter.**</br>
2. På sidan **Vem kan hantera ämnen** kan du välja:</br>
    a. **Alla i organisationen**</br>
    b. **Utvalda personer eller säkerhetsgrupper**</br>

    ![Hantera ämnen](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. Välj **Spara**.</br>


##  <a name="update-your-topic-center-name"></a>Uppdatera namn på ämnescenter

Välj fliken **Ämnescenter** om du vill uppdatera namnet på ämnescentret. 

1. Välj **Redigera**under **Namnet Ämnescenter**på fliken **Ämnescenter** .
2. Skriv det nya namnet för ämnescentret i **namnrutan För ämnescenter** på **namnsidan** Redigera ämnescenter.
3. Välj **Spara**

    ![Redigera namn på ämnescenter](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a>Se även



  






