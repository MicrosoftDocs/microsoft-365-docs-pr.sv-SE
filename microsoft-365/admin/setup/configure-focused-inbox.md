---
title: Konfigurera Prioriterad inkorg för alla i organisationen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
ms.openlocfilehash: eaf2c7623c81b24670a7b512c6311f0af036b255
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644609"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a><span data-ttu-id="c730f-103">Konfigurera Prioriterad inkorg för alla i organisationen</span><span class="sxs-lookup"><span data-stu-id="c730f-103">Configure Focused Inbox for everyone in your organization</span></span>

  <span data-ttu-id="c730f-104">Om du är ansvarig för att konfigurera hur e-post fungerar för ALLA i ett företag är den här artikeln för dig!</span><span class="sxs-lookup"><span data-stu-id="c730f-104">If you're responsible for configuring how email works for EVERYONE in a business this article is for you!</span></span> <span data-ttu-id="c730f-105">Här förklaras det hur du anpassar eller inaktiverar den för ditt företag och här finns svar på [Vanliga frågor](#faq-for-focused-inbox).</span><span class="sxs-lookup"><span data-stu-id="c730f-105">It explains how to customize it or turn it off for your business, and answers [frequently asked questions](#faq-for-focused-inbox).</span></span>  <br/> <span data-ttu-id="c730f-106">Om du vill stänga av Prioriterad inkorg bara för dig själv läser du [Stänga av Prioriterad inkorg](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span><span class="sxs-lookup"><span data-stu-id="c730f-106">If you would like to turn off Focused Inbox for just yourself, please see [Turn off Focused Inbox](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span></span>  
   
<span data-ttu-id="c730f-p102">Om du vill se till att dina användare säkert får företagsspecifika e-postmeddelanden, till exempel från personalavdelningen eller löneavdelningen, kan du konfigurera Prioriterad inkorg så att dessa meddelanden hamnar i vyn Prioriterad. Du kan även ange om användarna i organisationen ska se Prioriterad inkorg i Inkorgen eller inte.</span><span class="sxs-lookup"><span data-stu-id="c730f-p102">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a><span data-ttu-id="c730f-109">Aktivera eller inaktivera Prioriterad inkorg för din organisation</span><span class="sxs-lookup"><span data-stu-id="c730f-109">Turn Focused Inbox On or Off in your organization</span></span>

<span data-ttu-id="c730f-110">Du kan använda PowerShell för att aktivera eller inaktivera Prioriterad inkorg för alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c730f-110">You use PowerShell to turn Focused Inbox on or off for everyone in your organization.</span></span> <span data-ttu-id="c730f-111">Vill du göra detta i administrationscentret för Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c730f-111">Do you want to do this in the Microsoft 365 admin center?</span></span> <span data-ttu-id="c730f-112">Berätta gärna det för vårt tekniska team.</span><span class="sxs-lookup"><span data-stu-id="c730f-112">Let our Engineering team know.</span></span> <span data-ttu-id="c730f-113">**[Rösta här!](https://go.microsoft.com/fwlink/?linkid=862489)**</span><span class="sxs-lookup"><span data-stu-id="c730f-113">**[Vote here!](https://go.microsoft.com/fwlink/?linkid=862489)**</span></span>
  
 <span data-ttu-id="c730f-114">**Stänga av Prioriterad inkorg**</span><span class="sxs-lookup"><span data-stu-id="c730f-114">**To turn off Focused Inbox:**</span></span>
  
<span data-ttu-id="c730f-p104">I följande PowerShell-exempel **inaktiverar** du Prioriterad inkorg i din organisation. Men funktionens tillgänglighet blockeras inte för användarna. Om de vill kan de fortfarande aktivera Prioriterad inkorg igen på sina egna klienter. </span><span class="sxs-lookup"><span data-stu-id="c730f-p104">The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients.</span></span> 
  
1. <span data-ttu-id="c730f-118">[Ansluta till Exchange Online med fjärr-PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="c730f-118">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="c730f-p105">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Du kan se vilka behörigheter du behöver i avsnittet om transportregler i artikeln [Behörigheter för meddelandepolicyer och efterlevnad](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span><span class="sxs-lookup"><span data-stu-id="c730f-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>
    
3. <span data-ttu-id="c730f-121">Kör cmdlet **Get-OrganizationConfig**.</span><span class="sxs-lookup"><span data-stu-id="c730f-121">Run the **Get-OrganizationConfig** cmdlet.</span></span> 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. <span data-ttu-id="c730f-122">Leta efter **FocusedInboxOn** för att visa den aktuella inställningen:</span><span class="sxs-lookup"><span data-stu-id="c730f-122">Look for **FocusedInboxOn** to view its current setting:</span></span> 
    
    ![Svar från PowerShell om statusen för Prioriterad inkorg.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="c730f-124">Kör följande cmdlet om du vill inaktivera Prioriterad inkorg.</span><span class="sxs-lookup"><span data-stu-id="c730f-124">Run the following cmdlet to turn Focused Inbox off.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. <span data-ttu-id="c730f-125">Kör cmdlet **Get-OrganizationConfig** igen och så ser du att FocusedInboxOn anges till $false, vilket innebär att den har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="c730f-125">Run the **Get-OrganizationConfig** cmdlet again and you'll see that FocusedInboxOn is set to $false, which means it's been turned off.</span></span> 
    
 <span data-ttu-id="c730f-126">**Aktivera Prioriterad inkorg:**</span><span class="sxs-lookup"><span data-stu-id="c730f-126">**To turn on Focused Inbox:**</span></span>
  
- <span data-ttu-id="c730f-127">I steg 5 ovan kör du följande cmdlet om du vill aktivera Prioriterad inkorg.</span><span class="sxs-lookup"><span data-stu-id="c730f-127">In Step 5 above, run the following cmdlet to turn Focused Inbox on.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a><span data-ttu-id="c730f-128">Vad ser användarna ser när jag aktiverar Prioriterad inkorg? </span><span class="sxs-lookup"><span data-stu-id="c730f-128">What do users see after I turn on Focused Inbox?</span></span>

<span data-ttu-id="c730f-p106">Användarna kommer att se vyn Prioriterad efter att de stängt och startat om Outlook. När de startar om Outlook visas ett tips i Outlooks gränssnitt som hänvisar till den prioriterade inkorgen. </span><span class="sxs-lookup"><span data-stu-id="c730f-p106">Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span></span>
  
![En bild av hur den prioriterade inkorgen ser ut när en användare först öppnar Outlook på webben.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
<span data-ttu-id="c730f-p107">Om du växlar från Övrig e-post till Prioriterad inkorg kan de välja att aktivera funktionen ("Prova") eller stänga av funktionen. Om användaren har flera klienter (som stöds) kan de kan aktivera/inaktivera Prioriterad inkorg individuellt för alla klienter. Tipset ser ut så här.</span><span class="sxs-lookup"><span data-stu-id="c730f-p107">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:</span></span>
  
![En bild som visar hur Prioriterad inkorg ser ut när den har distribuerats till dina användare och Outlook öppnas igen.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
<span data-ttu-id="c730f-p108">Övrig e-post inaktiveras automatiskt när en användare väljer att börja använda Prioriterad inkorg. Mappen konverteras till en vanlig mapp som användaren kan byta namn på eller ta bort.</span><span class="sxs-lookup"><span data-stu-id="c730f-p108">When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a><span data-ttu-id="c730f-138">Aktivera eller inaktivera Prioriterad inkorg för specifika användare</span><span class="sxs-lookup"><span data-stu-id="c730f-138">Turn Focused Inbox On or Off for specific users</span></span>

<span data-ttu-id="c730f-p109">I det här exemplet **inaktiveras** Prioriterad inkorg för Tim Matthews i organisationen Contoso. Men funktionens tillgänglighet blockeras inte för honom. Om han vill kan han fortfarande aktivera Prioriterad inkorg igen på sina egna klienter.</span><span class="sxs-lookup"><span data-stu-id="c730f-p109">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization. However, it doesn't block the availability of the feature to him. If his wants, he can still re-enable Focused Inbox again on each of his clients.</span></span> 
  
1. <span data-ttu-id="c730f-142">[Ansluta till Exchange Online med fjärr-PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="c730f-142">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="c730f-p110">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Du kan se vilka behörigheter du behöver i avsnittet om transportregler i artikeln Behörigheter för meddelandepolicyer och efterlevnad (på engelska).</span><span class="sxs-lookup"><span data-stu-id="c730f-p110">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span></span>
    
3. <span data-ttu-id="c730f-145">Kör cmdleten **Get-FocusedInbox**, till exempel:</span><span class="sxs-lookup"><span data-stu-id="c730f-145">Run the **Get-FocusedInbox** cmdlet, for example:</span></span> 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. <span data-ttu-id="c730f-146">Leta efter FocusedInboxOn för att visa den aktuella inställningen:</span><span class="sxs-lookup"><span data-stu-id="c730f-146">Look for FocusedInboxOn to view its current setting:</span></span>
    
    ![Svar från PowerShell om statusen för Prioriterad inkorg.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="c730f-148">Kör följande cmdlet om du vill inaktivera Prioriterad inkorg:</span><span class="sxs-lookup"><span data-stu-id="c730f-148">Run the following cmdlet to turn Focused Inbox off:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. <span data-ttu-id="c730f-149">ELLER, kör följande cmdlet om du vill aktivera den:</span><span class="sxs-lookup"><span data-stu-id="c730f-149">OR, run the following cmdlet to turn it on:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="c730f-150">Använda gränssnittet till att skapa en transportregel som dirigerar e-postmeddelanden till vyn Prioriterad för alla användare</span><span class="sxs-lookup"><span data-stu-id="c730f-150">Use the UI to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="c730f-151">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="c730f-151">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="c730f-152">Gå till **E-postflöde** \> **Regler**.</span><span class="sxs-lookup"><span data-stu-id="c730f-152">Navigate to **mail flow** \> **Rules**.</span></span> <span data-ttu-id="c730f-153">Välj ![EAC-ikonen Lägg till](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) och välj sedan **Skapa en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="c730f-153">Select ![EAC Add icon](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) and then select **Create a new rule...**.</span></span> 
    
3. <span data-ttu-id="c730f-154">När du är färdig med den nya regeln klickar du på **Spara** så att regeln börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="c730f-154">After you're done creating the new rule, select **Save** to start the rule.</span></span> 
    
    <span data-ttu-id="c730f-155">I den följande bilden skickas alla meddelanden från ”Löneavdelningen” till den prioriterade inkorgen.</span><span class="sxs-lookup"><span data-stu-id="c730f-155">The following image shows an example where all messages From "Payroll Department" are to be delivered to the Focused Inbox.</span></span>
    
    ![prioriterad inkorg löneavdelning](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="c730f-157">Använda PowerShell till att skapa en transportregel som dirigerar e-postmeddelanden till vyn Prioriterad för alla användare</span><span class="sxs-lookup"><span data-stu-id="c730f-157">Use PowerShell to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="c730f-158">[Ansluta till Exchange Online med fjärr-PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="c730f-158">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="c730f-p112">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Du kan se vilka behörigheter du behöver i avsnittet om transportregler i artikeln [Behörigheter för meddelandepolicyer och efterlevnad](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span><span class="sxs-lookup"><span data-stu-id="c730f-p112">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>

3. <span data-ttu-id="c730f-161">Kör följande kommando om du vill skicka alla meddelanden från ”Löneavdelningen” till den prioriterade inkorgen.</span><span class="sxs-lookup"><span data-stu-id="c730f-161">Run the following command to allow all messages from "Payroll Department," for example, to be delivered to the Focused Inbox.</span></span>
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> <span data-ttu-id="c730f-162">I det här exemplet är både ”X-MS-Exchange-Organization-BypassFocusedInbox” och ”true” skiftlägeskänsliga.</span><span class="sxs-lookup"><span data-stu-id="c730f-162">In this example, both "X-MS-Exchange-Organization-BypassFocusedInbox" and "true" are case sensitive.</span></span>
> <span data-ttu-id="c730f-163">Prioriterad inkorg respekterar X-headern som åsidosätter övrig e-post, så om du använder den här inställningen i Övrig e-post används den även i Prioriterad inkorg.</span><span class="sxs-lookup"><span data-stu-id="c730f-163">Also, Focused Inbox will honor the X-header that bypasses Clutter, so if you use this setting in Clutter, it will be used in Focused Inbox.</span></span> <span data-ttu-id="c730f-164">Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span><span class="sxs-lookup"><span data-stu-id="c730f-164">For detailed syntax and parameter information, see [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c730f-165">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="c730f-165">How do you know this worked?</span></span>

<span data-ttu-id="c730f-166">Du kan kontrollera meddelandehuvudena och se efter om e-post hamnar i Inkorgen på grund av att transportregeln för Prioriterad inkorg kringgås.</span><span class="sxs-lookup"><span data-stu-id="c730f-166">You can check email message headers to see if the email messages are landing in the Inbox due to the Focused Inbox transport rule bypass.</span></span> <span data-ttu-id="c730f-167">Välj ett e-postmeddelande i en postlåda i organisationen som transportregeln för Prioriterad inkorg använts för.</span><span class="sxs-lookup"><span data-stu-id="c730f-167">Pick an email message from a mailbox in your organization that has the Focused Inbox transport rule applied.</span></span> <span data-ttu-id="c730f-168">Om du tittar på meddelandehuvudet ska du se **X-MS-Exchange-Organization-BypassFocusedInbox: true**.</span><span class="sxs-lookup"><span data-stu-id="c730f-168">Look at the headers stamped on the message, and you should see the **X-MS-Exchange-Organization-BypassFocusedInbox: true** header.</span></span> <span data-ttu-id="c730f-169">Det här innebär att regeln fungerar.</span><span class="sxs-lookup"><span data-stu-id="c730f-169">This means the bypass is working.</span></span> <span data-ttu-id="c730f-170">Läs mer om att hitta informationen i meddelandehuvudet i [Visa e-postmeddelandehuvud](https://go.microsoft.com/fwlink/p/?LinkId=822530).</span><span class="sxs-lookup"><span data-stu-id="c730f-170">Check out the [View the Internet header information for an email message](https://go.microsoft.com/fwlink/p/?LinkId=822530) article for info on how to find the header information.</span></span> 
 
## <a name="turn-onoff-clutter"></a><span data-ttu-id="c730f-171">Aktivera/inaktivera Övrig e-post</span><span class="sxs-lookup"><span data-stu-id="c730f-171">Turn on/off Clutter</span></span>
 
<span data-ttu-id="c730f-p115">Vi har fått rapporter att Övrig e-post plötsligt slutar fungera för en del användare. Du kan aktivera funktionen igen för specifika användare om detta inträffar. Se [Konfigurera Övrig e-post för organisationen](../email/configure-clutter.md).</span><span class="sxs-lookup"><span data-stu-id="c730f-p115">We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).</span></span>
 
## <a name="faq-for-focused-inbox"></a><span data-ttu-id="c730f-175">Vanliga frågor och svar om Prioriterad inkorg</span><span class="sxs-lookup"><span data-stu-id="c730f-175">FAQ for Focused Inbox</span></span>

<span data-ttu-id="c730f-176">Här är svar på några vanliga frågor om Prioriterad inkorg.</span><span class="sxs-lookup"><span data-stu-id="c730f-176">Here are answers to Frequently Asked Questions about Focused Inbox.</span></span> 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a><span data-ttu-id="c730f-177">Kan jag styra hur jag distribuerar Prioriterad inkorg i min organisation?</span><span class="sxs-lookup"><span data-stu-id="c730f-177">Can I control how I roll out Focused Inbox in my organization?</span></span>

<span data-ttu-id="c730f-p116">Ja. Du kan aktivera eller inaktivera Prioriterad inkorg för hela organisationen, eller så kan du aktivera eller inaktivera funktionen för vissa användare. Se ovan.</span><span class="sxs-lookup"><span data-stu-id="c730f-p116">Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.</span></span>
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a><span data-ttu-id="c730f-181">Är funktionen Prioriterad inkorg ENDAST tillgänglig för Office 2016-klienter?</span><span class="sxs-lookup"><span data-stu-id="c730f-181">Is the Focused Inbox feature ONLY available for Office 2016 clients?</span></span>

<span data-ttu-id="c730f-182">Ja, det är bara användare med Office 2016 som påverkas.</span><span class="sxs-lookup"><span data-stu-id="c730f-182">Yes, only users with Office 2016 are affected.</span></span> <span data-ttu-id="c730f-183">Funktionen kommer inte att bakåtanpassas till Outlook 2013 eller tidigare.</span><span class="sxs-lookup"><span data-stu-id="c730f-183">The feature is not going to be backported to Outlook 2013 or earlier.</span></span>
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a><span data-ttu-id="c730f-184">Hur lång tid tar det för ändringar i Prioriterad inkorg att verkställas i Outlook?</span><span class="sxs-lookup"><span data-stu-id="c730f-184">How long does it take for Focused Inbox changes to take place in Outlook?</span></span>

<span data-ttu-id="c730f-185">När du aktiverar eller inaktiverar Prioriterad inkorg börjar inställningarna gälla när användarna stänger och startar om Outlook.</span><span class="sxs-lookup"><span data-stu-id="c730f-185">Once you turn on or turn off Focused Inbox, the settings will take effect once your users close and restart Outlook.</span></span>
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a><span data-ttu-id="c730f-186">Vad händer med Övrig e-post när jag aktiverar Prioriterad inkorg?</span><span class="sxs-lookup"><span data-stu-id="c730f-186">What happens to Clutter once I turn on Focused Inbox?</span></span>

<span data-ttu-id="c730f-p118">När du har bytt får du inte längre mindre viktiga meddelanden i mappen Övrig e-post. I stället delas e-post upp mellan flikarna Prioriterad och Annan i inkorgen. Samma algoritm som flyttar objekt till mappen Övrig e-post styr nu Prioriterad inkorg, vilket betyder att all e-post som flyttades till Övrig e-post nu flyttas till Annan. Meddelanden som redan finns i mappen Övrig e-post ligger kvar där tills du bestämt om du vill ta bort dem eller flytta dem.</span><span class="sxs-lookup"><span data-stu-id="c730f-p118">After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span></span>
  
<span data-ttu-id="c730f-191">Läs det här inlägget från [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365) (på engelska).</span><span class="sxs-lookup"><span data-stu-id="c730f-191">Check out this post by [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span></span>
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a><span data-ttu-id="c730f-192">Kan jag låta användare behålla Övrig e-post?</span><span class="sxs-lookup"><span data-stu-id="c730f-192">Can I keep users on Clutter?</span></span> <span data-ttu-id="c730f-193">Vad rekommenderar Microsoft när det gäller Övrig e-post eller Prioriterad inkorg?</span><span class="sxs-lookup"><span data-stu-id="c730f-193">What is Microsoft's recommendation when it comes to using Clutter vs Focused Inbox?</span></span>

<span data-ttu-id="c730f-p120">Ja, du kan låta användare behålla Övrig e-post och inaktivera Prioriterad inkorg, men så småningom kommer Övrig e-post att ersättas helt med Prioriterad inkorg så Microsoft rekommenderar att du byter till Prioriterad inkorg redan nu. Mer information om att använda Övrig e-post med Exchange Online finns i det här blogginlägget: [Uppdaterad information om Prioriterad inkorg och våra planer för Övrig e-post](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span><span class="sxs-lookup"><span data-stu-id="c730f-p120">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span></span>
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a><span data-ttu-id="c730f-196">Bör jag inaktivera Övrig e-post för mina slutanvändare om alla så småningom ska byta till Prioriterad inkorg?</span><span class="sxs-lookup"><span data-stu-id="c730f-196">Should I disable Clutter for my end users if we are going to move everyone to Focused Inbox?</span></span>

<span data-ttu-id="c730f-p121">Nej. Du kan uttryckligen inaktivera Övrig e-post för en postlåda med cmdleten Set-Clutter. Men om du gör det kommer postlådans ägare att se meddelanden som tidigare skickades till mappen Övrig e-post i Inkorgen, och de måste handskas med de här meddelandena tills klienten har uppgraderats till en version med stöd för Prioriterad inkorg. Därför bör du inte inaktivera Övrig e-post förrän de uppgraderade klienterna är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="c730f-p121">No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.</span></span>
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a><span data-ttu-id="c730f-201">Varför finns det två cmdletar för att hantera Prioriterad inkorg?</span><span class="sxs-lookup"><span data-stu-id="c730f-201">Why are there two different cmdlets for managing Focused Inbox?</span></span>

<span data-ttu-id="c730f-202">Det finns två lägen kopplade till Prioriterad inkorg.</span><span class="sxs-lookup"><span data-stu-id="c730f-202">There are two states associated with Focused Inbox.</span></span>
  
- <span data-ttu-id="c730f-203">Läget **Organisationsnivå**: Prioriterad inkorg, samt en tillhörande tidsstämpel för senaste uppdatering.</span><span class="sxs-lookup"><span data-stu-id="c730f-203">**Organization Level**: Focused Inbox state, and an associated last update time-stamp.</span></span> 
    
- <span data-ttu-id="c730f-204">Läget **Postlådenivå**: Prioriterad inkorg, samt en tillhörande tidsstämpel för senaste uppdatering.</span><span class="sxs-lookup"><span data-stu-id="c730f-204">**Mailbox Level**: Focused Inbox state, and an associated last update time-stamp</span></span> 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a><span data-ttu-id="c730f-205">Hur avgör Outlook vilken version av Prioriterad inkorg som ska visas med dessa två lägen?</span><span class="sxs-lookup"><span data-stu-id="c730f-205">How does Outlook decide to show the Focused Inbox experience with these two states?</span></span>

<span data-ttu-id="c730f-p122">Outlook avgör vilken version som ska visas baserat på vilken cmdlet som har den senaste tidsstämpeln. Som standard har båda tidsstämplarna värdet ”null”, och då är funktionen aktiverad.</span><span class="sxs-lookup"><span data-stu-id="c730f-p122">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.</span></span>
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a><span data-ttu-id="c730f-208">Varför returnerar cmdleten Get-FocusedInbox ”true” när jag har inaktiverat Prioriterad inkorg i min organisation?</span><span class="sxs-lookup"><span data-stu-id="c730f-208">Why does the Get-FocusedInbox cmdlet return "true", when I've turned Focused Inbox off in my organization?</span></span>

<span data-ttu-id="c730f-p123">Det finns två cmdletar för att hantera Prioriterad inkorg. När du kör Get-FocusedInbox för en postlåda returneras funktionens status på postlådenivå. Versionen i Outlook väljs utifrån vilken cmdlet-status som ändrades senast.</span><span class="sxs-lookup"><span data-stu-id="c730f-p123">There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.</span></span>
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a><span data-ttu-id="c730f-212">Kan jag se vem som har aktiverat Prioriterad inkorg genom att köra ett skript?</span><span class="sxs-lookup"><span data-stu-id="c730f-212">Can I run a script to see who has turned on Focused Inbox?</span></span>

<span data-ttu-id="c730f-p124">Nej, och det här är avsiktligt. Prioriterad inkorg aktiveras i inställningar på klientsidan, så allt du kan få veta med cmdlet är om användarens postlåda är berättigad till klientversionen. Det är möjligt att den samtidigt är aktiverad i vissa klienter och inaktiverad i andra. Till exempel kan den vara aktiverad i Outlook-appen och i Outlook Mobile men inaktiverad i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="c730f-p124">No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span></span>
