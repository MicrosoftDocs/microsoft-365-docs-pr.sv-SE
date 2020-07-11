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
description: Lär dig att distribuera tillägg till användare och grupper i organisationen med hjälp av Centraliserad distribution i administrationscentret.
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103117"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Hantera tillägg i administrationscentret

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Office-tillägg hjälper dig att anpassa dina dokument och effektivisera ditt sätt att komma åt information på webben (se [Börja använda office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). 

När en administratör har distribuerat tillägg för användare i en organisation kan administratören inaktivera eller aktivera tillägg, redigera, ta bort och hantera åtkomst till tilläggen.

Mer information om hur du installerar tillägg från administrationscentret finns [i Distribuera tillägg i administrationscentret](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).
  
## <a name="add-in-states"></a>Tilläggstillstånd

Ett tillägg kan vara i läget **På** eller **Av.**
  
|**Statligt**|**Hur tillståndet inträffar**|**Effekt**|
|:-----|:-----|:-----|
|**Aktiva**  <br/> |Admin laddade upp tillägget och tilldelade det till användare eller grupper.  <br/> |Användare och grupper som tilldelats tillägget ser det i relevanta klienter.  <br/> |
|**Avstängd**  <br/> |Admin har inaktiverat tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> Om tilläggstillståndet ändras till Aktiv har användarna och grupperna åtkomst till det igen.  <br/> |
|**Deleted**  <br/> |Admin har tagit bort tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> |
   
Överväg att ta bort ett tillägg om ingen längre använder det. Det kan till exempel vara meningsfullt att inaktivera ett tillägg om ett tillägg bara används under vissa tider på året.

## <a name="delete-an-add-in"></a>Ta bort ett tillägg

Du kan också ta bort ett tillägg som har distribuerats.

1. Gå till sidan **Settings**  >  **Inställningarstjänster & tillägg i administrationscentret.**

2. Välj det distribuerade tillägget.

3. Klicka på **Ta bort tillägget**. Ta bort knappen Tillägg i det nedre högra hörnet.

4. Validera dina val och välj **Ta bort tillägget**.

## <a name="edit-add-in-access"></a>Redigera tilläggsåtkomst

Efter distribution, administratörer kan också hantera användaråtkomst till tillägg.

1. Gå till sidan **Settings**  >  **Inställningarstjänster & tillägg i administrationscentret.**

2. Välj det distribuerade tillägget.

3. Klicka på **Redigera** under **Vem har Access**.

4. Spara ändringarna.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Förhindra hämtningar av tillägg genom att stänga av Office Store för alla klienter (utom Outlook)

> [!NOTE]
> Outlook-tilläggsinstallation hanteras av en [annan process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

Som organisation kanske du vill förhindra hämtning av nya Office-tillägg från Office Store. Detta kan användas tillsammans med centraliserad distribution för att säkerställa att endast organisationsgodkända tillägg distribueras till användare inom organisationen.
  
**Så här inaktiverar du tilläggsförvärv**
  
1. I administrationscentret går du till sidan **Inställningar** \> [Tjänster och tillägg](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Välj **Användarindagna appar och tjänster**.
    
4. Avmarkera alternativet om du vill att användarna ska kunna komma åt Office-arkivet.

Detta förhindrar att alla användare hämtar följande tillägg från butiken.
  
- Tillägg för Word, Excel och PowerPoint 2016 från:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Förvärv som startar inom **AppSource**
    
- Tillägg i Microsoft 365
    
En användare som försöker komma åt arkivet ser följande meddelande: **Tyvärr har Microsoft 365 konfigurerats för att förhindra individuellt förvärv av Office Store-tillägg.**
  
Stöd för att stänga av Office Store finns i följande versioner:
  
- Windows: 16.0.9001 - För närvarande tillgänglig.
    
- Mac: 16.10.18011401 - För närvarande tillgänglig.
    
- iOS: 2.9.18010804 - För närvarande tillgänglig.
    
- Webben - För närvarande tillgänglig.
    
Detta hindrar inte en administratör från att använda centraliserad distribution för att tilldela ett tillägg från Office Store.
  
Om du vill förhindra att en användare loggar in med ett Microsoft-konto kan du begränsa inloggningen så att den bara använder organisationskontot. Mer information finns [i Identitet, autentisering och auktorisering i Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).  

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Mer om slutanvändarens upplevelse med tillägg

När du har distribuerat ett tillägg kan slutanvändarna börja använda det i sina Office-program (se [Börja använda Office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Tillägget visas på alla plattformar som tillägget stöder.
  
Om tillägget stöder tilläggskommandon visas kommandona i menyfliksområdet i Office. I följande exempel visas kommandot **Sökcitning** för tillägget **Källhänvisning.** 

![Menyfliksområdet i Office med sökhänvisning](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Om det distribuerade tillägget inte stöder tilläggskommandon eller om du vill visa alla distribuerade tillägg kan du visa dem via **Mina tillägg**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>I Word 2016, Excel 2016 eller PowerPoint 2016

1. Välj **Infoga \> mina tillägg**. 
    
2. Välj fliken **Administratörshanterad** i fönstret Office-tillägg. 
    
3. Dubbelklicka på det tillägg som du distribuerade tidigare (i det här exemplet **Citat** ). <br/>![Fliken Hanterad administratör på sidan Office-tillägg](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>I Outlook

1. I **menyfliksområdet Hem** väljer du **Hämta tillägg**.<br/>![Knappen Butik i Outlook](../../media/getaddinsicon.png)
  
2. Välj **Admin-hanterad** i den vänstra navigeringsfältet. 

## <a name="learn-more"></a>Mer information

[Distribuera tillägg i administrationscentret](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

Läs mer om hur du skapar och skapar [Office-tillägg](https://go.microsoft.com/fwlink/p/?linkid=846362).
  
[Använd centraliserade PowerShell-cmdlets för att hantera tillägg](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).
  
[Felsöka: Användaren ser inte tillägg](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Minderåriga och förvärva tillägg från Microsoft Store](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)