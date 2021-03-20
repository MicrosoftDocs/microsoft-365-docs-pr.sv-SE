---
title: Konfigurera Prioriterad inkorg för alla i organisationen
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: 'Lär dig hur du konfigurerar Prioriterad inkorg för alla eller vissa användare i organisationen. '
ms.openlocfilehash: 7059fbb886669af99c1471789cbbc623dc9719b8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914288"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Konfigurera Prioriterad inkorg för alla i organisationen

  Om du är ansvarig för att konfigurera hur e-post fungerar för ALLA i ett företag är den här artikeln för dig! Här förklaras det hur du anpassar eller inaktiverar den för ditt företag och här finns svar på [Vanliga frågor](#faq-for-focused-inbox).  <br/> Om du vill stänga av Prioriterad inkorg bara för dig själv läser du [Stänga av Prioriterad inkorg](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).  

Om du vill se till att dina användare säkert får företagsspecifika e-postmeddelanden, till exempel från personalavdelningen eller löneavdelningen, kan du konfigurera Prioriterad inkorg så att dessa meddelanden hamnar i vyn Prioriterad. Du kan även ange om användarna i organisationen ska se Prioriterad inkorg i Inkorgen eller inte.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Aktivera eller inaktivera Prioriterad inkorg för din organisation

Du kan använda PowerShell för att aktivera eller inaktivera Prioriterad inkorg för alla i organisationen. Vill du göra detta i administrationscentret för Microsoft 365? Berätta gärna det för vårt tekniska team. **[Rösta här!](https://go.microsoft.com/fwlink/?linkid=862489)**
  
 **Stänga av Prioriterad inkorg**
  
I följande PowerShell-exempel **inaktiverar** du Prioriterad inkorg i din organisation. Men funktionens tillgänglighet blockeras inte för användarna. Om de vill kan de fortfarande aktivera Prioriterad inkorg igen på sina egna klienter.  
  
1. [Ansluta till Exchange Online med fjärr-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Du kan se vilka behörigheter du behöver i avsnittet om transportregler i artikeln [Behörigheter för meddelandepolicyer och efterlevnad](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).

3. Kör cmdlet **Get-OrganizationConfig**. 

 ``` PowerShell
Get-OrganizationConfig
 ```

4. Leta efter **FocusedInboxOn** för att visa den aktuella inställningen: 

    ![Svar från PowerShell om statusen för Prioriterad inkorg.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Kör följande cmdlet om du vill inaktivera Prioriterad inkorg.

 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. Kör cmdlet **Get-OrganizationConfig** igen och så ser du att FocusedInboxOn anges till $false, vilket innebär att den har inaktiverats. 

 **Aktivera Prioriterad inkorg:**
  
- I steg 5 ovan kör du följande cmdlet om du vill aktivera Prioriterad inkorg.

 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>Vad ser användarna ser när jag aktiverar Prioriterad inkorg? 

Användarna kommer att se vyn Prioriterad efter att de stängt och startat om Outlook. När de startar om Outlook visas ett tips i Outlooks gränssnitt som hänvisar till den prioriterade inkorgen. 
  
![En bild av hur den prioriterade inkorgen ser ut när en användare först öppnar Outlook på webben.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
Om du växlar från Övrig e-post till Prioriterad inkorg kan de välja att aktivera funktionen ("Prova") eller stänga av funktionen. Om användaren har flera klienter (som stöds) kan de kan aktivera/inaktivera Prioriterad inkorg individuellt för alla klienter. Tipset ser ut så här.
  
![En bild som visar hur Prioriterad inkorg ser ut när den har distribuerats till dina användare och Outlook öppnas igen.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
Övrig e-post inaktiveras automatiskt när en användare väljer att börja använda Prioriterad inkorg. Mappen konverteras till en vanlig mapp som användaren kan byta namn på eller ta bort.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Aktivera eller inaktivera Prioriterad inkorg för specifika användare

I det här exemplet **inaktiveras** Prioriterad inkorg för Tim Matthews i organisationen Contoso. Men funktionens tillgänglighet blockeras inte för honom. Om han vill kan han fortfarande aktivera Prioriterad inkorg igen på sina egna klienter. 
  
1. [Ansluta till Exchange Online med fjärr-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Du kan se vilka behörigheter du behöver i avsnittet om transportregler i artikeln Behörigheter för meddelandepolicyer och efterlevnad (på engelska).

3. Kör cmdleten **Get-FocusedInbox**, till exempel: 

 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. Leta efter FocusedInboxOn för att visa den aktuella inställningen:

    ![Svar från PowerShell om statusen för Prioriterad inkorg.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Kör följande cmdlet om du vill inaktivera Prioriterad inkorg:

 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. ELLER, kör följande cmdlet om du vill aktivera den:

 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Använda gränssnittet till att skapa en transportregel som dirigerar e-postmeddelanden till vyn Prioriterad för alla användare

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.

2. Gå till **E-postflöde** \> **Regler**. Välj ![EAC-ikonen Lägg till](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) och välj sedan **Skapa en ny regel**. 

3. När du är färdig med den nya regeln klickar du på **Spara** så att regeln börjar gälla.

    I den följande bilden skickas alla meddelanden från ”Löneavdelningen” till den prioriterade inkorgen.

    ![prioriterad inkorg löneavdelning](../../media/focusedinbox-transport-rule.PNG)

> [!NOTE]
> Värdetexten i meddelandehuvudet i det här exemplet är **X-MS-Exchange-Organization-BypassFocusedInbox**.
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Använda PowerShell till att skapa en transportregel som dirigerar e-postmeddelanden till vyn Prioriterad för alla användare

1. [Ansluta till Exchange Online med fjärr-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Du kan se vilka behörigheter du behöver i avsnittet om transportregler i artikeln [Behörigheter för meddelandepolicyer och efterlevnad](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).

3. Kör följande kommando om du vill skicka alla meddelanden från ”Löneavdelningen” till den prioriterade inkorgen.

 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> I det här exemplet är både ”X-MS-Exchange-Organization-BypassFocusedInbox” och ”true” skiftlägeskänsliga.
> Prioriterad inkorg respekterar X-headern som åsidosätter övrig e-post, så om du använder den här inställningen i Övrig e-post används den även i Prioriterad inkorg. Detaljerad information om syntax och parametrar finns i [New-TransportRule](/powershell/module/exchange/new-transportrule).

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Du kan kontrollera meddelandehuvudena och se efter om e-post hamnar i Inkorgen på grund av att transportregeln för Prioriterad inkorg kringgås. Välj ett e-postmeddelande i en postlåda i organisationen som transportregeln för Prioriterad inkorg använts för. Om du tittar på meddelandehuvudet ska du se **X-MS-Exchange-Organization-BypassFocusedInbox: true**. Det här innebär att regeln fungerar. Läs mer om att hitta informationen i meddelandehuvudet i [Visa e-postmeddelandehuvud](https://go.microsoft.com/fwlink/p/?LinkId=822530).

## <a name="turn-onoff-clutter"></a>Aktivera/inaktivera Övrig e-post

Vi har fått rapporter att Övrig e-post plötsligt slutar fungera för en del användare. Du kan aktivera funktionen igen för specifika användare om detta inträffar. Se [Konfigurera Övrig e-post för organisationen](../email/configure-clutter.md).

## <a name="faq-for-focused-inbox"></a>Vanliga frågor och svar om Prioriterad inkorg

Här är svar på några vanliga frågor om Prioriterad inkorg.

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>Kan jag styra hur jag distribuerar Prioriterad inkorg i min organisation?

Ja. Du kan aktivera eller inaktivera Prioriterad inkorg för hela organisationen, eller så kan du aktivera eller inaktivera funktionen för vissa användare. Se ovan.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>Är funktionen Prioriterad inkorg ENDAST tillgänglig för Office 2016-klienter?

Ja, det är bara användare med Office 2016 som påverkas. Funktionen kommer inte att bakåtanpassas till Outlook 2013 eller tidigare.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>Hur lång tid tar det för ändringar i Prioriterad inkorg att verkställas i Outlook?

När du aktiverar eller inaktiverar Prioriterad inkorg börjar inställningarna gälla när användarna stänger och startar om Outlook.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>Vad händer med Övrig e-post när jag aktiverar Prioriterad inkorg?

När du har bytt får du inte längre mindre viktiga meddelanden i mappen Övrig e-post. I stället delas e-post upp mellan flikarna Prioriterad och Annan i inkorgen. Samma algoritm som flyttar objekt till mappen Övrig e-post styr nu Prioriterad inkorg, vilket betyder att all e-post som flyttades till Övrig e-post nu flyttas till Annan. Meddelanden som redan finns i mappen Övrig e-post ligger kvar där tills du bestämt om du vill ta bort dem eller flytta dem.
  
Läs det här inlägget från [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365) (på engelska).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>Kan jag låta användare behålla Övrig e-post? Vad rekommenderar Microsoft när det gäller Övrig e-post eller Prioriterad inkorg?

Ja, du kan låta användare behålla Övrig e-post och inaktivera Prioriterad inkorg, men så småningom kommer Övrig e-post att ersättas helt med Prioriterad inkorg så Microsoft rekommenderar att du byter till Prioriterad inkorg redan nu. Mer information om att använda Övrig e-post med Exchange Online finns i det här blogginlägget: [Uppdaterad information om Prioriterad inkorg och våra planer för Övrig e-post](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>Bör jag inaktivera Övrig e-post för mina slutanvändare om alla så småningom ska byta till Prioriterad inkorg?

Nej. Du kan uttryckligen inaktivera Övrig e-post för en postlåda med cmdleten Set-Clutter. Men om du gör det kommer postlådans ägare att se meddelanden som tidigare skickades till mappen Övrig e-post i Inkorgen, och de måste handskas med de här meddelandena tills klienten har uppgraderats till en version med stöd för Prioriterad inkorg. Därför bör du inte inaktivera Övrig e-post förrän de uppgraderade klienterna är tillgängliga.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>Varför finns det två cmdletar för att hantera Prioriterad inkorg?

Det finns två lägen kopplade till Prioriterad inkorg.
  
- Läget **Organisationsnivå**: Prioriterad inkorg, samt en tillhörande tidsstämpel för senaste uppdatering.

- Läget **Postlådenivå**: Prioriterad inkorg, samt en tillhörande tidsstämpel för senaste uppdatering. 

### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Hur avgör Outlook vilken version av Prioriterad inkorg som ska visas med dessa två lägen?

Outlook avgör vilken version som ska visas baserat på vilken cmdlet som har den senaste tidsstämpeln. Som standard har båda tidsstämplarna värdet ”null”, och då är funktionen aktiverad.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>Varför returnerar cmdleten Get-FocusedInbox ”true” när jag har inaktiverat Prioriterad inkorg i min organisation?

Det finns två cmdletar för att hantera Prioriterad inkorg. När du kör Get-FocusedInbox för en postlåda returneras funktionens status på postlådenivå. Versionen i Outlook väljs utifrån vilken cmdlet-status som ändrades senast.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>Kan jag se vem som har aktiverat Prioriterad inkorg genom att köra ett skript?

Nej, och det här är avsiktligt. Prioriterad inkorg aktiveras i inställningar på klientsidan, så allt du kan få veta med cmdlet är om användarens postlåda är berättigad till klientversionen. Det är möjligt att den samtidigt är aktiverad i vissa klienter och inaktiverad i andra. Till exempel kan den vara aktiverad i Outlook-appen och i Outlook Mobile men inaktiverad i Outlook på webben.