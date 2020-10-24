---
title: Därför måste du använda PowerShell för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 'Sammanfattning: förstå varför du måste använda PowerShell för att hantera Microsoft 365, i vissa fall mer effektivt och i andra fall efter nödvändighet.'
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754112"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="6824e-103">Därför måste du använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6824e-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="6824e-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6824e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6824e-105">Med Microsoft 365 Admin Center kan du hantera användar konton och licenser för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6824e-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="6824e-106">Du kan också hantera dina Microsoft 365-tjänster, till exempel Exchange Online, teams och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6824e-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="6824e-107">Om du istället använder PowerShell för att hantera de här tjänsterna kan du dra nytta av kommando rads-och skript språk miljö för hastighet, automatisering och andra funktioner.</span><span class="sxs-lookup"><span data-stu-id="6824e-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="6824e-108">I den här artikeln visar vi hur du använder PowerShell för att hantera Microsoft 365 för att:</span><span class="sxs-lookup"><span data-stu-id="6824e-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="6824e-109">Visa ytterligare information som inte visas i administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6824e-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="6824e-110">Konfigurera funktioner och inställningar endast möjligt med PowerShell</span><span class="sxs-lookup"><span data-stu-id="6824e-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="6824e-111">Utför Mass åtgärder</span><span class="sxs-lookup"><span data-stu-id="6824e-111">Do bulk operations</span></span>
    
- <span data-ttu-id="6824e-112">Filtrera data</span><span class="sxs-lookup"><span data-stu-id="6824e-112">Filter data</span></span>
    
- <span data-ttu-id="6824e-113">Skriva ut eller spara data</span><span class="sxs-lookup"><span data-stu-id="6824e-113">Print or save data</span></span>
    
- <span data-ttu-id="6824e-114">Hantera mellan tjänster</span><span class="sxs-lookup"><span data-stu-id="6824e-114">Manage across services</span></span>
    
<span data-ttu-id="6824e-115">Kom ihåg att PowerShell för Microsoft 365 är en uppsättning moduler för Windows PowerShell, som är en kommando rads miljö för Windows-baserade tjänster och plattformar.</span><span class="sxs-lookup"><span data-stu-id="6824e-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="6824e-116">Den här miljön skapar ett kommando gränssnitts språk som kan utökas med ytterligare moduler.</span><span class="sxs-lookup"><span data-stu-id="6824e-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="6824e-117">Det är ett sätt att utföra enkla eller komplicerade kommandon eller skript.</span><span class="sxs-lookup"><span data-stu-id="6824e-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="6824e-118">När du till exempel har installerat PowerShell för Microsoft 365-moduler och ansluter till din Microsoft 365-prenumeration kan du köra följande kommando för att visa alla användar post lådor för Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="6824e-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="6824e-119">Du kan också hämta listan med post lådor genom att använda administrations centret för Microsoft 365 men inventering av objekten i alla listor för alla dina webb program är inte lätt.</span><span class="sxs-lookup"><span data-stu-id="6824e-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="6824e-120">PowerShell för Microsoft 365 är utformat för att hjälpa dig att hantera Microsoft 365, inte för att ersätta Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="6824e-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="6824e-121">Administratörer måste kunna använda PowerShell för Microsoft 365 eftersom det finns vissa konfigurations procedurer som endast kan utföras via PowerShell för Microsoft 365-kommandon.</span><span class="sxs-lookup"><span data-stu-id="6824e-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="6824e-122">I de här fallen måste du veta hur du kan:</span><span class="sxs-lookup"><span data-stu-id="6824e-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="6824e-123">Installera PowerShell för Microsoft 365-moduler (endast en gång för varje administratörs dator).</span><span class="sxs-lookup"><span data-stu-id="6824e-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="6824e-124">Anslut till ditt Microsoft 365-abonnemang (en gång för varje PowerShell-session).</span><span class="sxs-lookup"><span data-stu-id="6824e-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="6824e-125">Samla in den information som behövs för att köra de PowerShell för Microsoft 365-kommandon som krävs.</span><span class="sxs-lookup"><span data-stu-id="6824e-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="6824e-126">Kör PowerShell för Microsoft 365-kommandon.</span><span class="sxs-lookup"><span data-stu-id="6824e-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="6824e-127">När du har lärt dig de grundläggande färdigheterna behöver du inte Visa dina post lådor med hjälp av kommandot **Hämta-post låda** .</span><span class="sxs-lookup"><span data-stu-id="6824e-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="6824e-128">Du behöver inte heller förstå hur du skapar ett nytt kommando, till exempel det omciterade kommandot för att räkna alla objekt i alla listor för alla webbapparna.</span><span class="sxs-lookup"><span data-stu-id="6824e-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="6824e-129">Microsoft och communityn för administratörer kan hjälpa dig med sådana uppgifter som behövs.</span><span class="sxs-lookup"><span data-stu-id="6824e-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="6824e-130">PowerShell för Microsoft 365 kan visa information som du inte kan se med administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6824e-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="6824e-131">Administrations centret för Microsoft 365 visar många användbara uppgifter.</span><span class="sxs-lookup"><span data-stu-id="6824e-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="6824e-132">Men det visar inte all information som kan användas i Microsoft 365 för användare, licenser, post lådor och webbplatser.</span><span class="sxs-lookup"><span data-stu-id="6824e-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="6824e-133">Här är ett exempel för *användare och grupper* i administrations centret för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="6824e-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Exempel på hur användare och grupper visas i administrations centret för Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="6824e-135">Den här vyn innehåller den information du behöver i många fall.</span><span class="sxs-lookup"><span data-stu-id="6824e-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="6824e-136">Men det finns tillfällen då du behöver mer.</span><span class="sxs-lookup"><span data-stu-id="6824e-136">However, there are times when you need more.</span></span> <span data-ttu-id="6824e-137">Microsoft 365-licensiering (och de Microsoft 365-funktioner som är tillgängliga för en användare) beror till exempel på användarens geografiska plats.</span><span class="sxs-lookup"><span data-stu-id="6824e-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="6824e-138">De principer och funktioner som du kan utöka till en användare som bor i USA kanske inte är samma som de som du kan använda för att utöka till en användare i Indien eller Belgien.</span><span class="sxs-lookup"><span data-stu-id="6824e-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="6824e-139">Följ de här anvisningarna i administrations centret för Microsoft 365 för att fastställa en användares geografiska plats:</span><span class="sxs-lookup"><span data-stu-id="6824e-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="6824e-140">Dubbelklicka på användarens **visnings namn**.</span><span class="sxs-lookup"><span data-stu-id="6824e-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="6824e-141">I fönstret användar egenskaper väljer du **information**.</span><span class="sxs-lookup"><span data-stu-id="6824e-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="6824e-142">I informations fönstret väljer du **Ytterligare information**.</span><span class="sxs-lookup"><span data-stu-id="6824e-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="6824e-143">Bläddra tills du hittar rubriken **land eller region**:</span><span class="sxs-lookup"><span data-stu-id="6824e-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Exempel på region informationen för en användare i administrations centret för Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="6824e-145">Skriv användarens visnings namn och plats på papperet, eller kopiera och klistra in i anteckningar.</span><span class="sxs-lookup"><span data-stu-id="6824e-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="6824e-146">Du måste upprepa proceduren för varje användare.</span><span class="sxs-lookup"><span data-stu-id="6824e-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="6824e-147">Om du har många användare kan den här processen bli omständlig.</span><span class="sxs-lookup"><span data-stu-id="6824e-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="6824e-148">Med PowerShell för Microsoft 365 kan du Visa den här informationen för alla användare genom att använda följande kommando:</span><span class="sxs-lookup"><span data-stu-id="6824e-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="6824e-149">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets som har *MSOL* i sitt namn.</span><span class="sxs-lookup"><span data-stu-id="6824e-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="6824e-150">Du måste köra de här cmdletarna från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6824e-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="6824e-151">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="6824e-151">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

<span data-ttu-id="6824e-152">Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen (**Get-AzureADUser**), men Visa bara namn och plats för varje användare (**Välj DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="6824e-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="6824e-153">Eftersom PowerShell för Microsoft 365 har stöd för ett kommando gränssnitts språk kan du ytterligare ändra informationen som erhålls med kommandot **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="6824e-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="6824e-154">Om du till exempel vill sortera dessa användare efter deras placering, kan du gruppera alla brasilianska användare tillsammans, alla användare tillsammans och så vidare.</span><span class="sxs-lookup"><span data-stu-id="6824e-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="6824e-155">Här är kommandot:</span><span class="sxs-lookup"><span data-stu-id="6824e-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="6824e-156">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="6824e-156">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

<span data-ttu-id="6824e-157">Tolkningen av det här PowerShell-kommandot är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen, men Visa bara namn och plats för varje användare och sortera dem först efter deras placering och sedan deras namn (**Sortera UsageLocation, DisplayName**).</span><span class="sxs-lookup"><span data-stu-id="6824e-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="6824e-158">Du kan också använda ytterligare filtrering.</span><span class="sxs-lookup"><span data-stu-id="6824e-158">You can also use additional filtering.</span></span> <span data-ttu-id="6824e-159">Om du till exempel vill visa information om användare som är baserade i Brasilien använder du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="6824e-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="6824e-160">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="6824e-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="6824e-161">Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen vars plats är Brasilien (**där {$ \_ . UsageLocation-EQ "BR"}**) och visar sedan namn och plats för varje användare.</span><span class="sxs-lookup"><span data-stu-id="6824e-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="6824e-162">**En kommentar om stora domäner**</span><span class="sxs-lookup"><span data-stu-id="6824e-162">**A note about large domains**</span></span>
  
<span data-ttu-id="6824e-163">Om du har en stor domän med tusentals användare kan du prova några av de exempel vi visar i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6824e-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="6824e-164">Beroende på faktorer som dator kraft och tillgänglig nätverks bandbredd kanske du försöker göra för mycket på en gång.</span><span class="sxs-lookup"><span data-stu-id="6824e-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="6824e-165">Stora organisationer kan dela vissa av dessa PowerShell-operationer i två kommandon.</span><span class="sxs-lookup"><span data-stu-id="6824e-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="6824e-166">Följande kommando returnerar till exempel alla användar konton och visar namn och plats för var och en av dem:</span><span class="sxs-lookup"><span data-stu-id="6824e-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="6824e-167">Det passar utmärkt för mindre domäner.</span><span class="sxs-lookup"><span data-stu-id="6824e-167">That works great for smaller domains.</span></span> <span data-ttu-id="6824e-168">I en stor organisation kanske du vill dela den operationen i två kommandon: ett kommando för att lagra information om användar kontot i en variabel och ett annat för att visa nödvändig information.</span><span class="sxs-lookup"><span data-stu-id="6824e-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="6824e-169">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="6824e-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="6824e-170">Tolkningen av denna uppsättning PowerShell-kommandon är:</span><span class="sxs-lookup"><span data-stu-id="6824e-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="6824e-171">Hämta alla användare i den aktuella Microsoft 365-prenumerationen och lagra informationen i en variabel som heter $x (**$x = get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="6824e-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="6824e-172">Visa innehållet i variabeln *$x*, men inkludera bara namn och plats för varje användare (**$x | Välj DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="6824e-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="6824e-173">Microsoft 365 har funktioner som du bara kan konfigurera med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6824e-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="6824e-174">Administrations centret för Microsoft 365 är avsett att ge till gång till vanliga och användbara administrativa uppgifter som gäller för de flesta miljöer.</span><span class="sxs-lookup"><span data-stu-id="6824e-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="6824e-175">Med andra ord har Microsoft 365 Admin Center konstruerats så att den typiska administratören kan utföra de vanligaste hanterings uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="6824e-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="6824e-176">Men det finns några uppgifter som inte kan göras i administrations centret.</span><span class="sxs-lookup"><span data-stu-id="6824e-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="6824e-177">Administrations centret för Skype för företag – Online innehåller till exempel några få alternativ för att skapa anpassade Mötes inbjudningar:</span><span class="sxs-lookup"><span data-stu-id="6824e-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Exempel på hur anpassade mötesinbjudan visas i administrations centret för Skype för företag – online.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="6824e-179">Med de här inställningarna kan du lägga till och anpassa Mötes inbjudningar.</span><span class="sxs-lookup"><span data-stu-id="6824e-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="6824e-180">Men det finns mer information om inställningar för Mötes konfiguration än att skapa anpassade Mötes inbjudningar.</span><span class="sxs-lookup"><span data-stu-id="6824e-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="6824e-181">Som standard tillåter möten till exempel:</span><span class="sxs-lookup"><span data-stu-id="6824e-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="6824e-182">Anonyma användare får automatisk ingång till varje möte.</span><span class="sxs-lookup"><span data-stu-id="6824e-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="6824e-183">Deltagare att spela in i mötet.</span><span class="sxs-lookup"><span data-stu-id="6824e-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="6824e-184">Alla användare i organisationen ska utses till presentatörer när de ansluter till mötet.</span><span class="sxs-lookup"><span data-stu-id="6824e-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="6824e-185">Dessa inställningar är inte tillgängliga från administrations centret för Skype för företag – online.</span><span class="sxs-lookup"><span data-stu-id="6824e-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="6824e-186">Du kan styra dem från PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6824e-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="6824e-187">Här är ett kommando som inaktiverar dessa tre inställningar:</span><span class="sxs-lookup"><span data-stu-id="6824e-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="6824e-188">För att köra det här kommandot måste du installera [PowerShell-modulen för Skype för företag – Online ](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="6824e-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="6824e-189">Tolkningen av detta PowerShell-kommando är:</span><span class="sxs-lookup"><span data-stu-id="6824e-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="6824e-190">I inställningar för nya Skype för företag – Online-möten (**set-CsMeetingConfiguration**) inaktiverar du Tillåt anonyma användare att få automatisk ingång till möten (**-AdmitAnonymousUsersByDefault $false**).</span><span class="sxs-lookup"><span data-stu-id="6824e-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="6824e-191">Inaktivera möjligheten för deltagare att spela in möten (**-AllowConferenceRecording $false**).</span><span class="sxs-lookup"><span data-stu-id="6824e-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="6824e-192">Du behöver inte ange alla användare från organisationen som presentatörer (**-DesignateAsPresenter "ingen"**).</span><span class="sxs-lookup"><span data-stu-id="6824e-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="6824e-193">Om du vill återställa standardinställningarna (aktivera alternativen) kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="6824e-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="6824e-194">Det finns andra liknande scenarier, vilket är orsaken till att administratörer bör kunna köra PowerShell för Microsoft 365-kommandon.</span><span class="sxs-lookup"><span data-stu-id="6824e-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="6824e-195">PowerShell för Microsoft 365 är perfekt för Mass åtgärder</span><span class="sxs-lookup"><span data-stu-id="6824e-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="6824e-196">Visuella gränssnitt som Microsoft 365 Admin Center är mest värdefulla när du har en enda åtgärd.</span><span class="sxs-lookup"><span data-stu-id="6824e-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="6824e-197">Om du till exempel behöver inaktivera ett användar konto kan du använda administrations centret för att snabbt hitta och avmarkera en kryss ruta.</span><span class="sxs-lookup"><span data-stu-id="6824e-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="6824e-198">Det kan vara enklare än att utföra en liknande åtgärd i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6824e-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="6824e-199">Men om du behöver ändra många saker eller vissa markerade saker i en stor uppsättning andra saker kanske administrations centret för Microsoft 365 inte är det bästa verktyget.</span><span class="sxs-lookup"><span data-stu-id="6824e-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="6824e-200">Säg till exempel att du måste ändra prefix på tusentals telefonnummer eller ta bort de specifika användarna *Katarina Myer* från alla SharePoint Online-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="6824e-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="6824e-201">Hur gör du det i administrations centret för Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="6824e-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="6824e-202">Anta att du har flera hundra SharePoint Online-webbplatser och att du inte vet vilka Katarina Meyer är medlem i.</span><span class="sxs-lookup"><span data-stu-id="6824e-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="6824e-203">Du skulle behöva börja med administrations centret för Microsoft 365 och sedan utföra den här proceduren för varje webbplats:</span><span class="sxs-lookup"><span data-stu-id="6824e-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="6824e-204">Välj **URL** för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="6824e-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="6824e-205">I rutan **Egenskaper för webbplats samling** väljer du länken webbplats **adress** för att öppna webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="6824e-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="6824e-206">Välj **dela**på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="6824e-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="6824e-207">I dialog rutan **dela** väljer du länken som visar alla användare som har behörighet till webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="6824e-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![Exempel på hur du visar medlemmarna på en SharePoint Online-webbplats i administrations centret för SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="6824e-209">I dialog rutan **delas med** väljer du **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="6824e-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="6824e-210">Bläddra nedåt i listan med användare, hitta och välj Katarina Myer (förutsatt att han har behörighet till webbplatsen) och välj sedan **ta bort användar behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="6824e-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="6824e-211">Det tar *lång* tid för flera hundra webbplatser.</span><span class="sxs-lookup"><span data-stu-id="6824e-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="6824e-212">Alternativet är att köra följande kommando i PowerShell för Microsoft 365 för att ta bort Katarina Myer från alla webbplatser:</span><span class="sxs-lookup"><span data-stu-id="6824e-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="6824e-213">Det här kommandot kräver att du installerar [SharePoint Online PowerShell-modulen](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="6824e-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="6824e-214">Tolkningen av det här PowerShell-kommandot är: Hämta alla SharePoint-webbplatser i den aktuella Microsoft 365-prenumerationen (**Get-SPOSite**) och för varje webbplats tar du bort Katarina Meyer från listan över användare som har åtkomst till den (**sol{Remove-Makers-site $ \_ . URL – LoginName "kenmyer \@ litwareinc.com"}**).</span><span class="sxs-lookup"><span data-stu-id="6824e-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="6824e-215">Vi berättar för Microsoft 365 att ta bort Katarina Meyer från alla webbplatser, inklusive de som han saknar åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="6824e-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="6824e-216">Därför visas fel för de webbplatser som han saknar åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="6824e-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="6824e-217">Vi kan använda ett ytterligare villkor i det här kommandot för att ta bort Katarina Meyer endast från webbplatser som har sin inloggnings lista.</span><span class="sxs-lookup"><span data-stu-id="6824e-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="6824e-218">Men felen som returneras gör att själva webbplatserna inte skadas.</span><span class="sxs-lookup"><span data-stu-id="6824e-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="6824e-219">Det kan ta några minuter att köra det här kommandot för hundratals webbplatser, i stället för timmar med att arbeta via Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="6824e-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="6824e-220">Här är ett annat Mass Operations exempel.</span><span class="sxs-lookup"><span data-stu-id="6824e-220">Here's another bulk operation example.</span></span> <span data-ttu-id="6824e-221">Använd det här kommandot för att lägga till *Håkans Kearney*, en ny SharePoint-administratör, på alla webbplatser i organisationen:</span><span class="sxs-lookup"><span data-stu-id="6824e-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="6824e-222">Tolkningen av det här PowerShell-kommandot är: Hämta alla SharePoint-webbplatser i den aktuella Microsoft 365-prenumerationen och för varje webbplats kan Håkans Kearney Access genom att lägga till hennes inloggnings namn i gruppen medlemmar på webbplatsen (**sol{Add-makar-site $ \_ . URL – LoginName "bkearney \@ litwareinc.com"-grupp "medlemmar"}**).</span><span class="sxs-lookup"><span data-stu-id="6824e-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="6824e-223">PowerShell för Microsoft 365 är ett bra sätt att filtrera data</span><span class="sxs-lookup"><span data-stu-id="6824e-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="6824e-224">Administrations centret för Microsoft 365 tillhandahåller flera olika sätt att filtrera data för att enkelt hitta en viss del av informationen.</span><span class="sxs-lookup"><span data-stu-id="6824e-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="6824e-225">Med Exchange blir det till exempel enkelt att filtrera på en användares post låda i praktiskt taget.</span><span class="sxs-lookup"><span data-stu-id="6824e-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="6824e-226">Här är en lista med post lådor för alla användare som bor i staden Bloomington:</span><span class="sxs-lookup"><span data-stu-id="6824e-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Exempel på en avancerad sökning i administrations centret för Microsoft 365 för listan med post lådor för alla användare som bor i staden Bloomington.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="6824e-228">I administrations centret för Exchange kan du även kombinera filter villkor.</span><span class="sxs-lookup"><span data-stu-id="6824e-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="6824e-229">Du kan till exempel hitta post lådorna för alla personer som bor i Bloomington och arbeta på ekonomi avdelningen.</span><span class="sxs-lookup"><span data-stu-id="6824e-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="6824e-230">Men det finns begränsningar för vad du kan göra i administrations centret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="6824e-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="6824e-231">Du kan till exempel enkelt hitta post lådorna för personer som bor i Bloomington *eller* San Diego, eller post lådorna för alla som inte bor i Bloomington.</span><span class="sxs-lookup"><span data-stu-id="6824e-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="6824e-232">Du kan använda följande PowerShell för Microsoft 365-kommando för att hämta en lista med post lådor för alla personer som bor i Bloomington eller San Diego:</span><span class="sxs-lookup"><span data-stu-id="6824e-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="6824e-233">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="6824e-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="6824e-234">Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen som har en post låda i staden San-Diego eller Bloomington (**där {$ \_ . En-EQ "UserMailbox"-och ($ \_ . City-EQ "San Diego"-eller $ \_ . City-EQ "Bloomington")}**) och visar sedan namnet och staden för var och en av dem (**Välj DisplayName, ort**).</span><span class="sxs-lookup"><span data-stu-id="6824e-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="6824e-235">Och här är kommandot för att visa alla post lådor för personer som bor var som helst utom Bloomington:</span><span class="sxs-lookup"><span data-stu-id="6824e-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="6824e-236">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="6824e-236">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

<span data-ttu-id="6824e-237">Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen som har en post låda som inte finns i staden Bloomington (**där {$ \_ . En-EQ "UserMailbox"-and $ \_ . City-Ne "Bloomington"}**) och visar sedan namnet och staden för varje.</span><span class="sxs-lookup"><span data-stu-id="6824e-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="6824e-238">Använda jokertecken</span><span class="sxs-lookup"><span data-stu-id="6824e-238">Use wildcards</span></span>

<span data-ttu-id="6824e-239">Du kan också använda jokertecken i dina PowerShell-filter för att matcha delar av ett namn.</span><span class="sxs-lookup"><span data-stu-id="6824e-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="6824e-240">Anta till exempel att du letar efter ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="6824e-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="6824e-241">Allt du kan komma ihåg är att användarens efter namn var *Anderson* eller kanske *Henderson* eller *Jorgenson*.</span><span class="sxs-lookup"><span data-stu-id="6824e-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="6824e-242">Du kan spåra användaren i administrations centret för Microsoft 365 genom att använda sökverktyget och utföra tre olika sökningar:</span><span class="sxs-lookup"><span data-stu-id="6824e-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="6824e-243">En för  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="6824e-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="6824e-244">En för  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="6824e-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="6824e-245">En för  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="6824e-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="6824e-246">Eftersom alla tre av namnen slutar med "son" kan du se till att PowerShell visar alla användare vars namn slutar på "son".</span><span class="sxs-lookup"><span data-stu-id="6824e-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="6824e-247">Här är kommandot:</span><span class="sxs-lookup"><span data-stu-id="6824e-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="6824e-248">Tolkningen av det här PowerShell-kommandot är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen, men Använd ett filter som bara visar de användare vars senaste namn slutar på "son" (**-filter ' {efter namn-like " \* son"} '**).</span><span class="sxs-lookup"><span data-stu-id="6824e-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="6824e-249">En \* uppsättning tecken som är bokstäver i användarens efter namn.</span><span class="sxs-lookup"><span data-stu-id="6824e-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="6824e-250">Med PowerShell för Microsoft 365 blir det enkelt att skriva ut eller spara data</span><span class="sxs-lookup"><span data-stu-id="6824e-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="6824e-251">Med administrations centret för Microsoft 365 kan du Visa listor med data.</span><span class="sxs-lookup"><span data-stu-id="6824e-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="6824e-252">Här är ett exempel på administrations centret för Skype för företag – online som visar en lista över användare som har Aktiver ATS för Skype för företag – online:</span><span class="sxs-lookup"><span data-stu-id="6824e-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Exempel på administrations centret för Skype för företag – online som visar en lista över användare som har Aktiver ATS för Skype för företag – online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="6824e-254">Om du vill spara informationen i en fil måste du klistra in den i ett dokument eller ett Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="6824e-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="6824e-255">Något av fallen kan kräva ytterligare formatering.</span><span class="sxs-lookup"><span data-stu-id="6824e-255">Either case might require additional formatting.</span></span> <span data-ttu-id="6824e-256">Administrations centret för Microsoft 365 kan dessutom inte skriva ut den lista som visas direkt.</span><span class="sxs-lookup"><span data-stu-id="6824e-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="6824e-257">Som tur är kan du använda PowerShell för att inte bara visa listan men för att spara den i en fil som enkelt kan importeras till Excel.</span><span class="sxs-lookup"><span data-stu-id="6824e-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="6824e-258">Här är ett exempel kommando för att spara användar data för Skype för företag – Online i en CSV-fil (kommaseparerade värden), som enkelt kan importeras som en tabell i ett Excel-kalkylblad:</span><span class="sxs-lookup"><span data-stu-id="6824e-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="6824e-259">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="6824e-259">Here's an example of the results:</span></span>
  
![Exempel på en tabell som importer ATS till ett Excel-kalkylblad för användare av Skype för företag – online som sparats i en fil med kommateckenavgränsade värden.](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="6824e-261">Tolkningen av detta PowerShell-kommando är: Hämta alla Skype för företag – Online-användare i den aktuella Microsoft 365-prenumerationen (**Get-CsOnlineUser**); Hämta bara användar namn, UPN och plats (**Välj DisplayName, userPrincipalName, UsageLocation**); och spara sedan informationen i en CSV-fil som heter C: \\ loggar \\SfBUsers.csv (**export-csv-Path "C: \\ loggar \\SfBUsers.csv"-NoTypeInformation**).</span><span class="sxs-lookup"><span data-stu-id="6824e-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="6824e-262">Du kan också använda alternativen för att spara denna lista som en XML-fil eller en HTML-sida.</span><span class="sxs-lookup"><span data-stu-id="6824e-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="6824e-263">Med ytterligare PowerShell-kommandon kan du faktiskt spara det direkt som en Excel-fil med eventuell anpassad formatering.</span><span class="sxs-lookup"><span data-stu-id="6824e-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="6824e-264">Du kan också skicka utdata från ett PowerShell-kommando som visar en lista direkt till standard skrivaren i Windows.</span><span class="sxs-lookup"><span data-stu-id="6824e-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="6824e-265">Här är ett exempel kommando:</span><span class="sxs-lookup"><span data-stu-id="6824e-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="6824e-266">Så här ser det utskrivna dokumentet ut:</span><span class="sxs-lookup"><span data-stu-id="6824e-266">Here's what your printed document will look like:</span></span>
  
![Exempel på ett utskrivet dokument som fick ett PowerShell-kommando skickat direkt till standard skrivaren i Windows.](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="6824e-268">Tolkningen av detta PowerShell-kommando är: Hämta alla Skype för företag – Online-användare i den aktuella Microsoft 365-prenumerationen; få bara användar namn, UPN och plats; och skicka sedan informationen till standard skrivaren i Windows (**ut-skrivaren**).</span><span class="sxs-lookup"><span data-stu-id="6824e-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="6824e-269">Det utskrivna dokumentet har samma enkla formatering som visas i PowerShell-Kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="6824e-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="6824e-270">Om du vill ha en pappers kopia lägger du bara till **| Slut på skrivare** till slutet av kommandot.</span><span class="sxs-lookup"><span data-stu-id="6824e-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="6824e-271">Med PowerShell för Microsoft 365 kan du hantera olika Server produkter</span><span class="sxs-lookup"><span data-stu-id="6824e-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="6824e-272">De komponenter som utgör Microsoft 365 är utformade för att fungera tillsammans.</span><span class="sxs-lookup"><span data-stu-id="6824e-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="6824e-273">Anta till exempel att du lägger till en ny användare i Microsoft 365 och att du anger information som användarens avdelning och telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="6824e-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="6824e-274">Denna information kommer att vara tillgänglig om du kommer åt användarens information i någon av Microsoft 365-tjänsterna: Skype för företag – Online, Exchange eller SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6824e-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="6824e-275">Men det är för gemensam information som omfattar produkterna.</span><span class="sxs-lookup"><span data-stu-id="6824e-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="6824e-276">Produktspecifika uppgifter, till exempel information om en användares Exchange-postlåda, är normalt inte tillgänglig i hela sviten.</span><span class="sxs-lookup"><span data-stu-id="6824e-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="6824e-277">Information om till exempel att en användares post låda är aktive rad eller inte är tillgänglig i administrations centret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="6824e-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="6824e-278">Anta att du vill skapa en rapport som visar följande information för alla dina användare:</span><span class="sxs-lookup"><span data-stu-id="6824e-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="6824e-279">Användarens visnings namn</span><span class="sxs-lookup"><span data-stu-id="6824e-279">The user's display name</span></span>
    
- <span data-ttu-id="6824e-280">Om användaren är licensierad för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6824e-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="6824e-281">Om användarens Exchange-postlåda har Aktiver ATS</span><span class="sxs-lookup"><span data-stu-id="6824e-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="6824e-282">Om användaren är aktive rad för Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="6824e-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="6824e-283">Du kan inte enkelt tillverka en sådan rapport i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6824e-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6824e-284">I stället måste du skapa ett separat dokument för att lagra informationen, till exempel ett Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="6824e-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="6824e-285">Hämta sedan alla användar namn och licensierings information från administrations centret för Microsoft 365, hämta information från administrations centret för Exchange, få information om Skype för företag – Online från administrations centret för Skype för företag – Online och kombinera den informationen.</span><span class="sxs-lookup"><span data-stu-id="6824e-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="6824e-286">Alternativet är att använda ett PowerShell-skript för att kompilera rapporten åt dig.</span><span class="sxs-lookup"><span data-stu-id="6824e-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="6824e-287">Följande exempel skript är mer komplicerat än de kommandon du har sett hittills i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6824e-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="6824e-288">Men det visar potentialen för att använda PowerShell för att skapa informations vyer som är svåra att se.</span><span class="sxs-lookup"><span data-stu-id="6824e-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="6824e-289">Så här kompilerar och visar du den lista du behöver:</span><span class="sxs-lookup"><span data-stu-id="6824e-289">Here's the script to compile and display the list you need:</span></span>
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

<span data-ttu-id="6824e-290">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="6824e-290">Here's an example of the results:</span></span>
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

<span data-ttu-id="6824e-291">Tolkningen av det här PowerShell-skriptet är:</span><span class="sxs-lookup"><span data-stu-id="6824e-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="6824e-292">Hämta alla användare i den aktuella Microsoft 365-prenumerationen och lagra informationen i en variabel som heter *$x* (**$x = get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="6824e-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="6824e-293">Starta en loop som körs över alla användare i variabeln $x $i (**fram$x)**.</span><span class="sxs-lookup"><span data-stu-id="6824e-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="6824e-294">Definiera en variabel som heter *$y* och lagra användarens post lådans information (**$y = Get-Mailbox-Identity $i. UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="6824e-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="6824e-295">Lägga till en ny egenskap i användar informationen som heter *IsMailBoxEnabled*.</span><span class="sxs-lookup"><span data-stu-id="6824e-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="6824e-296">Ange värdet för egenskapen IsMailBoxEnabled i användarens post låda (**$i | Add-Member-MemberType NoteProperty-Name IsMailBoxEnabled-value $y. IsMailBoxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="6824e-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="6824e-297">Definiera en variabel som heter *$y*och lagra användarens information om Skype för företag – Online (**$y = Get-CsOnlineUser-Identity $i. UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="6824e-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="6824e-298">Lägga till en ny egenskap i användar informationen som heter *EnabledForSfB*.</span><span class="sxs-lookup"><span data-stu-id="6824e-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="6824e-299">Ange värdet för egenskapen Enabled för användarens online-information för Skype för företag (**$i | Add-Member-MemberType NoteProperty EnabledForSfB-värde $y. enabled**).</span><span class="sxs-lookup"><span data-stu-id="6824e-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="6824e-300">Visa listan med användare, men bara ange deras namn, om de är licensierade och de två nya egenskaperna som visar om sin post låda är aktive rad och om den är aktive rad för Skype för företag – Online (**$x | Välj DisplayName, Ärlicensierad, IsMailboxEnabled, EnabledforSfB**).</span><span class="sxs-lookup"><span data-stu-id="6824e-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6824e-301">Se även</span><span class="sxs-lookup"><span data-stu-id="6824e-301">See also</span></span>

[<span data-ttu-id="6824e-302">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6824e-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6824e-303">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="6824e-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6824e-304">Använda Windows PowerShell för att skapa rapporter i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6824e-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
