---
title: Hantera tillägg i administrationscentret
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Läs mer om hur du använder centraliserade tillägg för att distribuera tillägg till användare och grupper i organisationen.
ms.openlocfilehash: ed9086c77cdf10435bae09f76493af6058d2d758
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314394"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Hantera tillägg i administrationscentret

Office tillägg hjälper dig att anpassa dina dokument och förenkla åtkomsten till information på webben (se Börja använda [Office tillägg).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 

När en administratör har distribuerat tillägg för användare i en organisation kan administratören aktivera eller inaktivera tillägg, redigera, ta bort och hantera åtkomst till tilläggen.

Mer information om hur du installerar tillägg från administrationscentret finns [i Distribuera tillägg i administrationscentret.](./manage-deployment-of-add-ins.md)
  
## <a name="add-in-states"></a>Tilläggsstater

Ett tillägg kan vara antingen i läget **På** **eller Av.**
  
| Region | Hur tillståndet uppstår | Påverkan |
|:-----|:-----|:-----|
|**Aktiv**  <br/> |Administratören har laddat upp tillägget och tilldelat det till användare eller grupper.  <br/> |Användare och grupper som tilldelats tillägget kan se det i relevanta klienter.  <br/> |
|**Inaktiverad**  <br/> |Administratören har inaktiverat tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> Om tilläggstillståndet ändras till Aktivt får användare och grupper åtkomst till det igen.  <br/> |
|**Borttagen**  <br/> |Administratören har tagit bort tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> |
   
Överväg att ta bort tillägg som ingen använder längre. Det kan vara bra att stänga av ett tillägg om ett tillägg bara används under vissa tider på året.

## <a name="delete-an-add-in"></a>Ta bort ett tillägg

Du kan också ta bort ett tillägg som har distribuerats.

1. I administrationscentret går du till **sidan Inställningar** tjänster  >  **& tillägg.**

    > [!NOTE]
    > Administrationscentret uppdateras för användning av integrerade appar. Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till avsnittet **Inställningar**  >  **Integrerade appar.** Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**

2. Välj det distribuerade tillägget.

3. Klicka **på Ta bort tillägg.** Ta bort knappen Tillägg längst ned till höger.

4. Validera dina val och välj **Ta bort tillägg**.

## <a name="edit-add-in-access"></a>Redigera åtkomst till tillägg

Efter distributionen kan administratörer också hantera användaråtkomst till tillägg.

1. I administrationscentret går du till **sidan Inställningar** tjänster  >  **& tillägg.**

    > [!NOTE]
    > Administrationscentret uppdateras för användning av integrerade appar. Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till avsnittet **Inställningar**  >  **Integrerade appar.** Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**

2. Välj det distribuerade tillägget.

3. Klicka på **Redigera** under **Vem har Access.**

4. Spara ändringarna.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Förhindra nedladdningar av tillägg genom att inaktivera Office Store i alla klienter (utom Outlook)

> [!NOTE]
> Outlook tilläggsinstallation hanteras av en [annan process.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)

Som organisation kanske du vill förhindra nedladdning av Office tillägg från Office Store. Det kan användas tillsammans med centraliserad distribution för att säkerställa att endast av organisationen godkända tillägg distribueras till användare inom organisationen.
  
**Så här inaktiverar du datainsamling av tillägg**
  
1. I administrationscentret går du till sidan **Inställningar** \> [Tjänster och tillägg](https://go.microsoft.com/fwlink/p/?linkid=2053743).

    > [!NOTE]
    > Administrationscentret uppdateras för användning av integrerade appar. Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till avsnittet **Inställningar**  >  **Integrerade appar.** Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**
    
3. Välj **Användarägda appar och tjänster.**
    
4. Avmarkera alternativet att ge användare åtkomst till Office store.

    Det hindrar alla användare från att hämta följande tillägg från Store.
      
    - Tillägg för Word, Excel och PowerPoint 2016 från:
        
      - Windows
      - Mac
      - Office
        
        
    - Datainsamling som startar i **AppSource**
        
    - Tillägg inom Microsoft 365
        
    En användare som försöker komma åt Store får ett meddelande om att Microsoft 365 har konfigurerats för att förhindra enskilda datainsamlingar av **Office Store-tillägg.**
  
Stöd för att stänga Office Store är tillgängligt i följande versioner:
  
- Windows: 16.0.9001 – tillgänglig.
    
- Mac: 16.10.18011401 – tillgänglig.
    
- iOS: 2.9.18010804 – tillgänglig.
    
- Webben – tillgänglig.
    
Det hindrar inte en administratör från att använda centraliserad distribution till att tilldela ett tillägg från Office Store.

> [!NOTE] 
> Tillägg som Visio Data visualizer, Bing-kartor och People Graph visas fortfarande i menyfliksområdet, även om en administratör har inaktiverat Store. Om du vill ta bort de här länkarna måste administratörer inaktivera Store via Group Policy Object (GPO).
  
Du kan förhindra att en användare loggar in med ett Microsoft-konto genom att begränsa inloggning till organisationskontot. Mer information finns i [Identitet, autentisering och auktorisering i Office 2016.](/DeployOffice/security/identity-authentication-and-authorization-in-office)  

> [!NOTE] 
> Om du hindrar användare från att komma åt Office Store hindras de också från att Office separat inläsning av tillägg för [testning från en nätverksresurs.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Mer om slutanvändarupplevelsen med tillägg

När du har distribuerat ett tillägg kan slutanvändarna börja använda det i sina Office-program (se Börja använda [Office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Tillägget visas på alla plattformar som har stöd för det.
  
Om tillägget har stöd för tilläggskommandon visas de i det Office menyfliksområdet. I följande exempel visas kommandot **Sök källhänvisning** för tillägget **Källhänvisningar.** 

![Office menyfliksområde med källhänvisningar](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Om det distribuerade tillägget inte har stöd för tilläggskommandon eller om du vill visa alla distribuerade tillägg kan du visa dem via **Mina tillägg.** 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>I Word 2016, Excel 2016 eller PowerPoint 2016

1. Välj **\> Infoga mina tillägg.** 
    
2. Välj **fliken Administratör** hanterad Office i fönstret Tillägg. 
    
3. Dubbelklicka på tillägget som du distribuerade tidigare (i det här exemplet **Källhänvisningar).**

    ![Fliken Administratör hanterad Office tilläggssidan](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>I Outlook

1. I **menyfliksområdet** Start **väljer du Hämta tillägg.**

    ![Knappen Lagra i Outlook](../../media/getaddinsicon.png)
  
2. Välj **Administratör hanterad i** det vänstra navigeringsfältet. 

## <a name="related-content"></a>Relaterat innehåll

[Distribuera tillägg i administrationscentret](./manage-deployment-of-add-ins.md) (artikel)\
Läs mer om att [Office tillägg](/office/dev/add-ins/overview/office-add-ins) (artikel)\
[Använd PowerShell-cmdlets för](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) centraliserad distribution för att hantera tillägg (artikel)\
[Felsökning: Användaren ser inte tillägg](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artikel)\
[Minderåriga och köp av tillägg från Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (artikel)
