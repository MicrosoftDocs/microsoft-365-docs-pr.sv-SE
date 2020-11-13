---
title: Hantera tillägg i administrationscentret
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Lär dig mer om hur du använder centraliserade tillägg för att distribuera tillägg till användare och grupper i din organisation.
ms.openlocfilehash: 5521b01e059ca8ae4a97ecb094f9aa1198263701
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071483"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Hantera tillägg i administrationscentret

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Med hjälp av Office-tillägg kan du anpassa dina dokument och förenkla hur du kommer åt informationen på webben (se [börja använda Office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). 

När en administratör distribuerar tillägg för användare i en organisation kan administratören aktivera tillägg eller på, redigera, ta bort och hantera åtkomst till tilläggen.

Mer information om hur du installerar tillägg från administrations centret finns i [distribuera tillägg i administrations centret](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).
  
## <a name="add-in-states"></a>Tilläggs tillstånd

Ett tillägg kan vara i läget **på** eller **av** .
  
|**Sessionsläget**|**Hur tillståndet uppträder**|**Påverkan**|
|:-----|:-----|:-----|
|**Aktiva**  <br/> |Administratören har laddat upp tillägget och tilldelat det till användare eller grupper.  <br/> |Användare och grupper som tilldelats tillägget kan se det i relevanta klienter.  <br/> |
|**Inaktiverat**  <br/> |Administratören har inaktiverat tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> Om tillägget ändras till Active får användarna och grupperna åtkomst till det igen.  <br/> |
|**Deleted**  <br/> |Administratören har tagit bort tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> |
   
Överväg att ta bort ett tillägg om det inte längre används. Om du till exempel inaktiverar ett tillägg kan det vara bra att använda ett tillägg endast under vissa tider på året.

## <a name="delete-an-add-in"></a>Ta bort ett tillägg

Du kan också ta bort ett tillägg som har distribuerats.

1. I administrations centret går du till sidan **Inställningar**  >  **& tillägg** .

     > [!NOTE]
    > Administrations centret uppdateras till distributions miljön med integrerade appar. Om du inte ser ovanstående steg går du till avsnittet centraliserad distribution genom att gå till **Inställningar** för  >  **integrerade appar**. **Välj tillägg** högst upp på sidan för **integrerade appar** .

2. Välj det distribuerade tillägget.

3. Klicka på **ta bort tillägg**. Ta bort knappen tillägg i det nedre högra hörnet.

4. Validera dina val och välj **ta bort tillägg**.

## <a name="edit-add-in-access"></a>Redigera tilläggs åtkomst

Efter distribution kan administratörer även hantera användar åtkomst till tillägg.

1. I administrations centret går du till sidan **Inställningar**  >  **& tillägg** .

     > [!NOTE]
    > Administrations centret uppdateras till distributions miljön med integrerade appar. Om du inte ser ovanstående steg går du till avsnittet centraliserad distribution genom att gå till **Inställningar** för  >  **integrerade appar**. **Välj tillägg** högst upp på sidan för **integrerade appar** .

2. Välj det distribuerade tillägget.

3. Klicka på **redigera** under **vem har åtkomst**.

4. Spara ändringarna.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Förhindra hämtning av tillägg genom att stänga av Office Store på alla klienter (utom Outlook)

> [!NOTE]
> Installation av Outlook-tillägg hanteras av en [annan process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

Som en organisation kanske du vill förhindra nedladdning av nya Office-tillägg från Office Store. Detta kan användas tillsammans med centraliserad distribution för att säkerställa att endast organisations godkända tillägg distribueras till användare inom organisationen.
  
**Så här inaktiverar du tilläggs förvärv**
  
1. I administrationscentret går du till sidan **Inställningar** \> [Tjänster och tillägg](https://go.microsoft.com/fwlink/p/?linkid=2053743).

     > [!NOTE]
    > Administrations centret uppdateras till distributions miljön med integrerade appar. Om du inte ser ovanstående steg går du till avsnittet centraliserad distribution genom att gå till **Inställningar** för  >  **integrerade appar**. **Välj tillägg** högst upp på sidan för **integrerade appar** .
    
3. Välj **ägda appar och tjänster**.
    
4. Avmarkera alternativet för att låta användare komma åt Office Store.

Detta hindrar alla användare från att hämta följande tillägg från Store.
  
- Tillägg för Word, Excel och PowerPoint 2016 från:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Förvärv från **AppSource**
    
- Tillägg i Microsoft 365
    
En användare som försöker nå butiken ser följande meddelande: **Microsoft 365 har kon figurer ATS för att förhindra enskilda köp av Office Store-tillägg.**
  
Stöd för att stänga av Office Store är tillgängligt i följande versioner:
  
- Windows: 16.0.9001-tillgänglig.
    
- Mac: 16.10.18011401-tillgänglig.
    
- iOS: 2.9.18010804-tillgänglig.
    
- Webbplatsen finns för närvarande.
    
Detta förhindrar inte att administratörer använder centraliserad distribution för att tilldela ett tillägg från Office Store.
  
För att förhindra att en användare loggar in med ett Microsoft-konto kan du begränsa inloggningen så att endast organisations kontot används. Mer information finns i [identitet, autentisering och auktorisering i Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).  

> [!NOTE]
> Att förhindra att användare som använder Office Store kan hindra dem från att läsa in [Office-tillägg för testning](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Mer om slut användar upplevelsen med tillägg

När du har distribuerat ett tillägg kan slutanvändarna börja använda det i deras Office-program (se [börja använda Office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Tillägget visas på alla plattformar som stöds av tillägget.
  
Om tillägget har stöd för tilläggs kommandon visas kommandona i menyfliksområdet i Office. I följande exempel visas kommandot **Sök hänvisning** för **käll hänvisning** . 

![Office-menyfliksområde med Sök käll hänvisningar](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Om det distribuerade tillägget inte har stöd för tilläggs kommandon eller om du vill visa alla distribuerade tillägg kan du visa dem via **Mina tillägg**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>I Word 2016, Excel 2016 eller PowerPoint 2016

1. Välj **infoga \> Mina tillägg**. 
    
2. Välj fliken **hanterad administratör** i fönstret Office-tillägg. 
    
3. Dubbelklicka på tillägget du distribuerat tidigare (i det här exemplet **käll hänvisningar** ). <br/>![Fliken hanterad administratör på sidan Office-tillägg](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>I Outlook

1. Välj **Hämta tillägg** **i menyfliksområdet** .<br/>![Knappen lagra i Outlook](../../media/getaddinsicon.png)
  
2. Välj **administrativ hantering** i det vänstra navigerings fältet. 

## <a name="learn-more"></a>Mer information

[Distribuera tillägg i administrations centret för](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

Läs mer om att skapa och skapa [Office-tillägg](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).
  
[Hantera tillägg genom att använda PowerShell-cmdlets för centraliserad distribution](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).
  
[Fel sökning: användaren ser inte tillägg](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Minderåriga och förvärvade tillägg från Microsoft Store](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
