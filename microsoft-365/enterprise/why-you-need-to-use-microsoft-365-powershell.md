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
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694340"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="41f0e-103">Därför måste du använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41f0e-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="41f0e-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="41f0e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="41f0e-105">Med administrations centret för Microsoft 365 kan du inte bara hantera dina användar konton och licenser för Microsoft 365, men du kan även hantera dina Microsoft 365-tjänster, till exempel Exchange Online, teams och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="41f0e-105">With the Microsoft 365 admin center, you can not only manage your Microsoft 365 user accounts and licenses, but you can also manage your Microsoft 365 services such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="41f0e-106">Men du kan också hantera de här elementen med PowerShell-kommandon och dra nytta av en kommando rads-och skript språk miljö för hastighet, automatisering och annan kapacitet.</span><span class="sxs-lookup"><span data-stu-id="41f0e-106">However, you can also manage these elements with PowerShell commands, taking advantage of a command-line and scripting language environment for speed, automation, and additional capability.</span></span>
  
<span data-ttu-id="41f0e-107">I den här artikeln visar vi hur du kan använda PowerShell för att hantera Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="41f0e-107">In this article, we'll show you these ways in which you can use PowerShell to manage Microsoft 365:</span></span>
  
- <span data-ttu-id="41f0e-108">Visa ytterligare information som du inte kan se med administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41f0e-108">Reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="41f0e-109">Konfigurera funktioner och inställningar endast möjligt med PowerShell</span><span class="sxs-lookup"><span data-stu-id="41f0e-109">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="41f0e-110">Utför Mass åtgärder</span><span class="sxs-lookup"><span data-stu-id="41f0e-110">Perform bulk operations</span></span>
    
- <span data-ttu-id="41f0e-111">Filtrera data</span><span class="sxs-lookup"><span data-stu-id="41f0e-111">Filtering data</span></span>
    
- <span data-ttu-id="41f0e-112">Skriva ut eller spara data</span><span class="sxs-lookup"><span data-stu-id="41f0e-112">Print or save data</span></span>
    
- <span data-ttu-id="41f0e-113">Hantera mellan tjänster</span><span class="sxs-lookup"><span data-stu-id="41f0e-113">Manage across services</span></span>
    
<span data-ttu-id="41f0e-114">Innan du börjar förstår du att PowerShell för Microsoft 365 är en uppsättning moduler för Windows PowerShell, en kommando rads miljö för Windows-baserade tjänster och plattformar.</span><span class="sxs-lookup"><span data-stu-id="41f0e-114">Before you begin, understand that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="41f0e-115">Den här miljön skapar ett gränssnitts språk som kan utökas med ytterligare moduler och ger dig en möjlighet att utföra enkla eller komplexa kommandon eller skript.</span><span class="sxs-lookup"><span data-stu-id="41f0e-115">This environment creates a command shell language that can be extended with additional modules and provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="41f0e-116">När du till exempel har installerat PowerShell för Microsoft 365-moduler och ansluter till din Microsoft 365-prenumeration kan du köra det här kommandot för att visa alla användar post lådor för Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="41f0e-116">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run this command to list all of the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="41f0e-117">Det är lätt att hämta listan med post lådor med hjälp av administrations centret för Microsoft 365, men det är lätt att räkna antalet objekt i alla listor för alla dina webb program.</span><span class="sxs-lookup"><span data-stu-id="41f0e-117">Getting the list of mailboxes can also be easily done using the Microsoft 365 admin center, but counting the number of items in all of the lists for all of the sites for all of your web apps cannot be easily done.</span></span>
  
<span data-ttu-id="41f0e-118">Observera att PowerShell för Microsoft 365 är utformat för att utöka och förbättra din förmåga att hantera Microsoft 365, inte för att ersätta Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="41f0e-118">Please note that PowerShell for Microsoft 365 is designed to augment and enhance your ability to manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="41f0e-119">Som administratör måste du vara minst van vid att använda PowerShell för Microsoft 365 eftersom det finns vissa konfigurations procedurer som bara kan utföras med PowerShell för Microsoft 365-kommandon.</span><span class="sxs-lookup"><span data-stu-id="41f0e-119">As an administrator, you must become at least comfortable with using PowerShell for Microsoft 365 because there are some configuration procedures that can only be done with PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="41f0e-120">I sådana fall måste du förstå hur du kan:</span><span class="sxs-lookup"><span data-stu-id="41f0e-120">In these cases, you will be required to understand how to:</span></span>
  
- <span data-ttu-id="41f0e-121">Installera PowerShell för Microsoft 365-moduler (utförs bara en gång för varje administratörs dator).</span><span class="sxs-lookup"><span data-stu-id="41f0e-121">Install the PowerShell for Microsoft 365 modules (done only once for each administrator computer).</span></span>
    
- <span data-ttu-id="41f0e-122">Anslut till ditt Microsoft 365-abonnemang (utförs en gång för varje PowerShell-session).</span><span class="sxs-lookup"><span data-stu-id="41f0e-122">Connect to your Microsoft 365 subscription (done once for each PowerShell session).</span></span>
    
- <span data-ttu-id="41f0e-123">Samla in den information som behövs för att köra de PowerShell för Microsoft 365-kommandon som krävs.</span><span class="sxs-lookup"><span data-stu-id="41f0e-123">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="41f0e-124">Kör PowerShell för Microsoft 365-kommandon.</span><span class="sxs-lookup"><span data-stu-id="41f0e-124">Run the PowerShell for Microsoft 365 commands successfully.</span></span>
    
<span data-ttu-id="41f0e-125">Efter att ha lärt de här grundläggande färdigheterna behöver du inte lista dina post lådor med kommandot **Hämta-post låda** , eller så behöver du inte förstå hur du skapar ett nytt kommando som föregående om du vill räkna alla objekt i alla dina webb program.</span><span class="sxs-lookup"><span data-stu-id="41f0e-125">After learning these basic skills, you are not required to list your mailbox users with **Get-Mailbox** command, nor are you required to understand how to create a new command like the previous one to count all the items in all the lists for all of the sites for all of your web apps.</span></span> <span data-ttu-id="41f0e-126">Microsoft och communityn för administratörer kan hjälpa dig med det som behövs.</span><span class="sxs-lookup"><span data-stu-id="41f0e-126">Microsoft and the community of administrators can help you with that as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="41f0e-127">PowerShell för Microsoft 365 kan visa ytterligare information som du inte kan se med administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41f0e-127">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="41f0e-128">Administrations centret för Microsoft 365 visar mycket värdefull information, men det betyder inte att det visar all den information som Microsoft 365 lagrar på användare, licenser, post lådor och webbplatser.</span><span class="sxs-lookup"><span data-stu-id="41f0e-128">The Microsoft 365 admin center displays a lot of useful information, but that doesn't mean that it displays all the possible information that Microsoft 365 stores on users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="41f0e-129">Här är ett exempel på **användare och grupper** i Microsoft 365 Admin Center:</span><span class="sxs-lookup"><span data-stu-id="41f0e-129">Here is an example for **users and groups** in the Microsoft 365 admin center:</span></span>
  
![Exempel på hur användare och grupper visas i administrations centret för Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="41f0e-131">I många avseenden visar detta den information du behöver veta.</span><span class="sxs-lookup"><span data-stu-id="41f0e-131">For many purposes, this displays the information you need to know.</span></span> <span data-ttu-id="41f0e-132">Men det finns tillfällen då du behöver mer.</span><span class="sxs-lookup"><span data-stu-id="41f0e-132">However, there are times when you need more.</span></span> <span data-ttu-id="41f0e-133">Microsoft 365-licensiering (och de Microsoft 365-funktioner som är tillgängliga för en användare) beror till exempel på användarens geografiska plats.</span><span class="sxs-lookup"><span data-stu-id="41f0e-133">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depend in part on that user's geographic location.</span></span> <span data-ttu-id="41f0e-134">De principer och funktioner som du kan förlänga till en användare som bor i USA kanske inte är samma som de principer och funktioner som du kan förlänga till en användare som bor i Indien eller i Belgien.</span><span class="sxs-lookup"><span data-stu-id="41f0e-134">The policies and features you can extend to a user who lives in the United States might not be the same as the policies and features you can extend to a user who lives in India or in Belgium.</span></span> <span data-ttu-id="41f0e-135">Du kan använda administrations centret för Microsoft 365 för att fastställa en användares geografiska plats med de här stegen:</span><span class="sxs-lookup"><span data-stu-id="41f0e-135">You can use the Microsoft 365 admin center to determine a user's geographic location with these steps:</span></span>
  
1. <span data-ttu-id="41f0e-136">Dubbelklicka på användarens **visnings namn**.</span><span class="sxs-lookup"><span data-stu-id="41f0e-136">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="41f0e-137">I fönstret användar egenskaper klickar du på **information**.</span><span class="sxs-lookup"><span data-stu-id="41f0e-137">In the user properties display pane, click **details**.</span></span>
    
3. <span data-ttu-id="41f0e-138">Klicka på **Ytterligare information**i informations fönstret.</span><span class="sxs-lookup"><span data-stu-id="41f0e-138">In the details display, click **additional details**.</span></span>
    
4. <span data-ttu-id="41f0e-139">Bläddra nedåt tills du ser rubriken **land eller region**:</span><span class="sxs-lookup"><span data-stu-id="41f0e-139">Scroll down until you see the heading **Country or region**:</span></span>
    
     ![Exempel på region informationen för en användare i administrations centret för Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="41f0e-141">Skriv användarens visnings namn och plats på papperet, eller kopiera och klistra in i anteckningar.</span><span class="sxs-lookup"><span data-stu-id="41f0e-141">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span> 
    
<span data-ttu-id="41f0e-142">Du måste upprepa proceduren för varje användare.</span><span class="sxs-lookup"><span data-stu-id="41f0e-142">You must repeat this procedure for each user.</span></span> <span data-ttu-id="41f0e-143">För många användare kan det vara en omständlig uppgift.</span><span class="sxs-lookup"><span data-stu-id="41f0e-143">For many users, this can be a tedious task.</span></span> <span data-ttu-id="41f0e-144">Med PowerShell för Microsoft 365 kan du Visa den här informationen för alla dina användare med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="41f0e-144">With PowerShell for Microsoft 365, you can display this information for all of your users with the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="41f0e-145">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="41f0e-145">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="41f0e-146">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41f0e-146">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="41f0e-147">Här är ett exempel på skärmen:</span><span class="sxs-lookup"><span data-stu-id="41f0e-147">Here is an example of the display:</span></span>
  
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

> [!TIP]
>  <span data-ttu-id="41f0e-148">Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen ( **Get-AzureADUser** ), men Visa bara namn och plats för varje användare ( **Välj DisplayName, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-148">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription ( **Get-AzureADUser** ), but only display the name and location for each user ( **Select DisplayName, UsageLocation** ).</span></span>
  
<span data-ttu-id="41f0e-149">Eftersom PowerShell för Microsoft 365 stöder ett kommando gränssnitts språk kan du ytterligare ändra informationen som hämtas från kommandot **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="41f0e-149">Because PowerShell for Microsoft 365 supports a command shell language, you can further manipulate the information obtained from the **Get-AzureADUser** command.</span></span> <span data-ttu-id="41f0e-150">Om du till exempel vill sortera dessa användare efter deras placering, kan du gruppera alla användare i Brasilien, alla användare i USA, etc. Här är kommandot:</span><span class="sxs-lookup"><span data-stu-id="41f0e-150">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, etc. Here is the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="41f0e-151">Här är ett exempel på skärmen:</span><span class="sxs-lookup"><span data-stu-id="41f0e-151">Here is an example of the display:</span></span>
  
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

> [!TIP]
>  <span data-ttu-id="41f0e-152">Tolkningen av det här PowerShell-kommandot är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen, men Visa bara namn och plats för varje användare och sortera dem först efter deras placering och sedan deras namn ( **Sortera UsageLocation, DisplayName** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location, and then their names ( **Sort UsageLocation, DisplayName** ).</span></span>
  
<span data-ttu-id="41f0e-153">Du kan också använda ytterligare filtrering.</span><span class="sxs-lookup"><span data-stu-id="41f0e-153">You can also employ additional filtering.</span></span> <span data-ttu-id="41f0e-154">Om du till exempel vill visa information om användare som är baserade i Brasilien använder du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="41f0e-154">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="41f0e-155">Här är ett exempel på skärmen:</span><span class="sxs-lookup"><span data-stu-id="41f0e-155">Here is an example of the display:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  <span data-ttu-id="41f0e-156">Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen vars plats är Brasilien ( **där {$ \_ . UsageLocation-EQ "BR"}** ) och visar sedan namn och plats för varje användare.</span><span class="sxs-lookup"><span data-stu-id="41f0e-156">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription whose location is Brazil ( **Where {$\_.UsageLocation -eq "BR"}** ), then display the name and location for each user.</span></span>
  
 <span data-ttu-id="41f0e-157">**En snabb anteckning angående större domäner**</span><span class="sxs-lookup"><span data-stu-id="41f0e-157">**A Quick Note Regarding Larger Domains**</span></span>
  
<span data-ttu-id="41f0e-158">Om du har en mycket stor domän med tusentals användare kan du prova några av exemplen som vi visar i den här artikeln leda till "begränsning".</span><span class="sxs-lookup"><span data-stu-id="41f0e-158">If you have a very large domain with tens of thousands of users, trying some of the examples we show in this article could lead to "throttling."</span></span> <span data-ttu-id="41f0e-159">Det innebär att beroende på saker som dator kraft och tillgänglig nätverks bandbredd, försöker du göra lite för mycket åt gången.</span><span class="sxs-lookup"><span data-stu-id="41f0e-159">That means that, based on things like computing power and available network bandwidth, you're trying to do a little too much at one time.</span></span> <span data-ttu-id="41f0e-160">Därför kan det vara bra att dela upp några av dessa PowerShell för Microsoft 365-kommandon i två kommandon.</span><span class="sxs-lookup"><span data-stu-id="41f0e-160">Because of that, larger organizations might want to split some of these PowerShell for Microsoft 365 commands into two commands.</span></span> <span data-ttu-id="41f0e-161">Till exempel returnerar det här kommandot alla användar konton och visar namn och plats för var och en av dem:</span><span class="sxs-lookup"><span data-stu-id="41f0e-161">For example, this one command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="41f0e-162">Det passar utmärkt för mindre domäner.</span><span class="sxs-lookup"><span data-stu-id="41f0e-162">That works great for smaller domains.</span></span> <span data-ttu-id="41f0e-163">I en stor organisation kan du behöva dela upp det i två kommandon: ett kommando för att lagra användar konto informationen i en variabel och ett annat kommando för att visa nödvändig information.</span><span class="sxs-lookup"><span data-stu-id="41f0e-163">In a large organization, however, you might need to split that into two commands: one command to store the user account information in a variable and another command to display the needed information.</span></span> <span data-ttu-id="41f0e-164">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="41f0e-164">Here is an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="41f0e-165">Tolkningen av denna uppsättning PowerShell-kommandon är:</span><span class="sxs-lookup"><span data-stu-id="41f0e-165">The interpretation of this set of PowerShell commands is:</span></span>
- <span data-ttu-id="41f0e-166">Hämta alla användare i den aktuella Microsoft 365-prenumerationen och lagra informationen i en variabel som heter $x ( **$x = get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-166">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="41f0e-167">Visa innehållet i variabeln $x, men inkludera bara namn och plats för varje användare ( **$x | Välj DisplayName, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-167">Display the contents of the variable $x, but only include the name and location for each user ( **$x | Select DisplayName, UsageLocation** ).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="41f0e-168">Microsoft 365 har funktioner som du bara kan konfigurera med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41f0e-168">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="41f0e-169">Administrations centret för Microsoft 365 är avsett att ge till gång till de vanligaste eller meningsfulla administrativa uppgifter som gäller för de flesta användare.</span><span class="sxs-lookup"><span data-stu-id="41f0e-169">The Microsoft 365 admin center is intended to provide access to the most common or meaningful administrative tasks that apply to most people.</span></span> <span data-ttu-id="41f0e-170">Med andra ord har Microsoft 365 Admin Center konstruerats så att den typiska administratören kan använda verktyget för att utföra de vanligaste hanterings uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="41f0e-170">In other words, the Microsoft 365 admin center was designed so that the typical administrator could use the tool to carry out the most common management tasks.</span></span> <span data-ttu-id="41f0e-171">Genom den här definitionen innebär det att det finns vissa uppgifter som inte kan utföras med hjälp av administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41f0e-171">By this definition, that means that there are some tasks that can't be completed by using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="41f0e-172">Administrations centret för Skype för företag – Online innehåller till exempel några få alternativ för att skapa anpassade Mötes inbjudningar:</span><span class="sxs-lookup"><span data-stu-id="41f0e-172">For example, the Skype for Business Online Admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Exempel på hur anpassade mötesinbjudan visas i administrations centret för Skype för företag – online.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="41f0e-174">Med de här inställningarna kan du lägga till och anpassa Mötes inbjudningar.</span><span class="sxs-lookup"><span data-stu-id="41f0e-174">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="41f0e-175">Men det finns mer information om konfigurations inställningar för möten än att skapa anpassade Mötes inbjudningar.</span><span class="sxs-lookup"><span data-stu-id="41f0e-175">However, there's more to meeting configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="41f0e-176">Som standard tillåter möten till exempel:</span><span class="sxs-lookup"><span data-stu-id="41f0e-176">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="41f0e-177">Anonyma användare får automatisk ingång till varje möte.</span><span class="sxs-lookup"><span data-stu-id="41f0e-177">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="41f0e-178">Deltagare att spela in i mötet.</span><span class="sxs-lookup"><span data-stu-id="41f0e-178">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="41f0e-179">Alla användare i organisationen ska utses till presentatörer när de ansluter till mötet.</span><span class="sxs-lookup"><span data-stu-id="41f0e-179">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="41f0e-180">Dessa inställningar är inte tillgängliga från administrations centret för Skype för företag – online.</span><span class="sxs-lookup"><span data-stu-id="41f0e-180">These settings are not available from the Skype for Business Online Admin center.</span></span> <span data-ttu-id="41f0e-181">Men du kan styra dem från PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41f0e-181">However, you can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="41f0e-182">Här är ett kommando som inaktiverar dessa tre inställningar:</span><span class="sxs-lookup"><span data-stu-id="41f0e-182">Here is a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="41f0e-183">Det här kommandot kräver att du installerar [PowerShell-modulen för Skype för företag – Online ](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="41f0e-183">This command requires that you install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="41f0e-184">Tolkningen av det här PowerShell-kommandot är: för inställningar för nya Skype för företag – Online-möten ( **set-CsMeetingConfiguration** ) inaktiverar du tillåta att anonyma användare får automatisk ingång till möten ( **-AdmitAnonymousUsersByDefault $false** ), inaktiverar möjligheten för deltagare att spela in möten ( **$false-** **DesignateAsPresenter "inget"** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-184">The interpretation of this PowerShell command is: For the settings for new Skype for Business Online meetings ( **Set-CsMeetingConfiguration** ), disable allowing anonymous users to gain automatic entrance to meetings ( **-AdmitAnonymousUsersByDefault $False** ), disable the ability for attendees to record meetings ( **-AllowConferenceRecording $False** ), and do not designate all users from your organization as presenters ( **-DesignateAsPresenter "None"** ).</span></span>
  
<span data-ttu-id="41f0e-185">Om du ändrar dig och vill återställa dessa standardinställningar (alla aktiverade) kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="41f0e-185">If you change your mind and want to restore these default settings (all of them enabled), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="41f0e-186">Det här är bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="41f0e-186">This is just one example.</span></span> <span data-ttu-id="41f0e-187">Det finns andra, som du måste känna till genom att köra PowerShell för Microsoft 365-kommandon.</span><span class="sxs-lookup"><span data-stu-id="41f0e-187">There are others, which is why you, as an administrator, need to be comfortable with running PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a><span data-ttu-id="41f0e-188">PowerShell för Microsoft 365 är perfekt när de utför Mass åtgärder</span><span class="sxs-lookup"><span data-stu-id="41f0e-188">PowerShell for Microsoft 365 is great at carrying out bulk operations</span></span>

<span data-ttu-id="41f0e-189">Historiskt, visuella gränssnitt som Microsoft 365 Admin Center är mest värdefulla när du har en enda åtgärd att utföra.</span><span class="sxs-lookup"><span data-stu-id="41f0e-189">Historically, visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to perform.</span></span> <span data-ttu-id="41f0e-190">Om du till exempel behöver inaktivera ett användar konto kan du använda administrations centret för Microsoft 365 för att snabbt hitta och avmarkera en kryss ruta.</span><span class="sxs-lookup"><span data-stu-id="41f0e-190">For example, if you need to disable one user account, you can use the Microsoft 365 admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="41f0e-191">Det kan vara enklare än att utföra en liknande åtgärd i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41f0e-191">This can be simpler than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="41f0e-192">Men om du behöver ändra många saker eller vissa markerade saker i en stor uppsättning andra saker kanske administrations centret för Microsoft 365 inte är det bästa med din tid.</span><span class="sxs-lookup"><span data-stu-id="41f0e-192">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best use of your time.</span></span> <span data-ttu-id="41f0e-193">Om du till exempel hade ändrat prefix på tusentals telefonnummer eller om du vill ta bort en specifik användare, Katarina Myer, från alla SharePoint Online-webbplatser, hur gör du det i administrations centret för Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="41f0e-193">For example, if you had to change the prefix on thousands of phone numbers or you needed to remove a specific user, Ken Myer, from all of your SharePoint Online sites, how would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="41f0e-194">I det senare exemplet har du flera hundra SharePoint Online-webbplatser och du vet inte ens vilka Katarina Meyer är medlem.</span><span class="sxs-lookup"><span data-stu-id="41f0e-194">For the latter example, you have several hundred SharePoint Online sites and you don't know even know which ones of which Ken Meyer is a member.</span></span> <span data-ttu-id="41f0e-195">Det innebär att du måste starta i administrations centret för Microsoft 365 och sedan utföra den här proceduren för varje webbplats:</span><span class="sxs-lookup"><span data-stu-id="41f0e-195">That means you'll have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="41f0e-196">Klicka på webbplatsens **URL-adress** .</span><span class="sxs-lookup"><span data-stu-id="41f0e-196">Click the **URL** of the site.</span></span>
    
2. <span data-ttu-id="41f0e-197">I rutan **Egenskaper för webbplats samling** klickar du på länken webbplats **adress** för att öppna webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="41f0e-197">In the **site collection properties** box, click the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="41f0e-198">Klicka på **dela**på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="41f0e-198">On the site, click **Share**.</span></span>
    
4. <span data-ttu-id="41f0e-199">I dialog rutan **dela** klickar du på länken som visar alla användare som har behörighet till webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="41f0e-199">In the **Share** dialog box click the link that shows you all the users who have permissions to the site:</span></span>
    
     ![Exempel på hur du visar medlemmarna på en SharePoint Online-webbplats i administrations centret för SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="41f0e-201">Klicka på **Avancerat**i dialog rutan **delas med** .</span><span class="sxs-lookup"><span data-stu-id="41f0e-201">In the **Shared With** dialog box, click **Advanced**.</span></span>
    
6. <span data-ttu-id="41f0e-202">Bläddra nedåt i listan med användare, hitta och välj Katarina Myer (förutsatt att han har behörighet till webbplatsen) och klicka sedan på **ta bort användar behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="41f0e-202">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then click **Remove User Permissions**.</span></span>
    
<span data-ttu-id="41f0e-203">Det kan ta lång tid för flera hundra webbplatser.</span><span class="sxs-lookup"><span data-stu-id="41f0e-203">This can take a long time for several hundred sites.</span></span>
  
<span data-ttu-id="41f0e-204">Alternativet är att använda PowerShell för Microsoft 365 och följande kommando för att ta bort Katarina Myer från alla webbplatser:</span><span class="sxs-lookup"><span data-stu-id="41f0e-204">The alternative is to use PowerShell for Microsoft 365 and the following command to remove Ken Myer from all of your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="41f0e-205">Det här kommandot kräver att du installerar [SharePoint Online PowerShell-modulen](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="41f0e-205">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="41f0e-206">Tolkningen av det här PowerShell-kommandot är: Hämta alla SharePoint-webbplatser i den aktuella Microsoft 365-prenumerationen ( **Get-SPOSite** ) och för varje webbplats tar du bort Katarina Meyer från listan över användare som har åtkomst till den ( **sol{Remove-make-in-site $ \_ . URL – LoginName "kenmyer@litwareinc.com"}** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-206">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription ( **Get-SPOSite** ) and for each site, remove Ken Meyer from the list of users who can access it ( **ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer@litwareinc.com"}** ).</span></span>
  
<span data-ttu-id="41f0e-207">Eftersom vi meddelar att Microsoft 365 tar bort Katarina Meyer från alla webbplatser, inklusive de som han inte har åtkomst till, visar kommandot fel för de webbplatser som han för tillfället inte har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="41f0e-207">Because we are telling Microsoft 365 to remove Ken Meyer from every site, including those in which he does not have access, the display of this command will show errors for those sites in which he does not currently have access.</span></span> <span data-ttu-id="41f0e-208">Vi kan använda ett ytterligare villkor i det här kommandot för att ta bort Meyer endast från webbplatser som har sin inloggnings lista, men de fel som visas i listan är inte skadliga för själva webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="41f0e-208">We can use an additional condition on this command to remove Key Meyer only from the sites that have him in their login list, but the listed errors cause no harm to the sites themselves.</span></span> <span data-ttu-id="41f0e-209">Det kan ta några minuter att köra det här kommandot för hundratals webbplatser, i stället för timmar med att arbeta via Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="41f0e-209">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="41f0e-210">Här är ett annat Mass åtgärds exempel.</span><span class="sxs-lookup"><span data-stu-id="41f0e-210">Here is another bulk operation example.</span></span> <span data-ttu-id="41f0e-211">Använd det här kommandot för att lägga till Håkans Kearney, en ny SharePoint-administratör, på alla webbplatser i organisationen:</span><span class="sxs-lookup"><span data-stu-id="41f0e-211">Use this command to add Bonnie Kearney, a new SharePoint administrator, to all of the sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  <span data-ttu-id="41f0e-212">Tolkningen av det här PowerShell-kommandot är: Hämta alla SharePoint-webbplatser i den aktuella Microsoft 365-prenumerationen och för varje webbplats kan du låta Håkans Kearney Access genom att lägga till hennes inloggnings namn i gruppen medlemmar på webbplatsen ( **sol{Add-makar-site $ \_ . URL – LoginName "bkearney@litwareinc.com" – grupp "medlemmar"}** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-212">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription and for each site, allow Bonnie Kearney access by adding her login name to the Members group of the site ( **ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}** ).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="41f0e-213">PowerShell för Microsoft 365 är ett bra sätt att filtrera data</span><span class="sxs-lookup"><span data-stu-id="41f0e-213">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="41f0e-214">Administrations centret för Microsoft 365 tillhandahåller flera olika sätt att filtrera data så att du snabbt och enkelt kan hitta en viss del av informationen.</span><span class="sxs-lookup"><span data-stu-id="41f0e-214">The Microsoft 365 admin center provides several different ways to filter your data to quickly and easily locate a targeted subset of information.</span></span> <span data-ttu-id="41f0e-215">Med Exchange blir det till exempel enkelt att filtrera på en användares post låda i praktiskt taget.</span><span class="sxs-lookup"><span data-stu-id="41f0e-215">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="41f0e-216">Här är en lista med post lådor för alla användare som bor i staden Bloomington:</span><span class="sxs-lookup"><span data-stu-id="41f0e-216">For example, here is the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Exempel på en avancerad sökning i administrations centret för Microsoft 365 för listan med post lådor för alla användare som bor i staden Bloomington.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="41f0e-218">I administrations centret för Exchange kan du även kombinera filter villkor.</span><span class="sxs-lookup"><span data-stu-id="41f0e-218">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="41f0e-219">Du kan till exempel hitta post lådorna för alla personer som bor i Bloomington och som arbetar på ekonomi avdelningen.</span><span class="sxs-lookup"><span data-stu-id="41f0e-219">For example, you can find the mailboxes for all the people who live in Bloomington and who work in the Finance department.</span></span> 
  
<span data-ttu-id="41f0e-220">Men det finns begränsningar i administrations centret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="41f0e-220">However, there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="41f0e-221">Du kanske till exempel vill hitta post lådorna för personer som bor i Bloomington eller San Diego eller post lådorna för alla personer som inte bor i Bloomington.</span><span class="sxs-lookup"><span data-stu-id="41f0e-221">For example, maybe you'd like to find the mailboxes of people who live in Bloomington or San Diego, or the mailboxes for all the people who don't live in Bloomington.</span></span> 
  
<span data-ttu-id="41f0e-222">Med PowerShell för Microsoft 365 kan du hämta en lista med post lådor för alla personer som bor i städer med Bloomington eller San Diego med det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="41f0e-222">With PowerShell for Microsoft 365, you can get a list of mailboxes for all the people who live in the cities of Bloomington or San Diego with this command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="41f0e-223">Här är ett exempel på skärmen:</span><span class="sxs-lookup"><span data-stu-id="41f0e-223">Here is an example of the display:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  <span data-ttu-id="41f0e-224">Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen som har en post låda i städer med antingen San-Diego eller Bloomington ( **där {$ \_ . En-EQ "UserMailbox"-och ($ \_ . City-EQ "San Diego"-eller $ \_ . City-EQ "Bloomington")}** ) och visar sedan namnet och staden för var och en av dem ( **Välj DisplayName, ort** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-224">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox in the cities of either San Diego or Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}** ), then display the name and city for each ( **Select DisplayName, City** ).</span></span>
  
<span data-ttu-id="41f0e-225">Så här gör du för att visa alla post lådor för personer som bor var som helst förutom Bloomington:</span><span class="sxs-lookup"><span data-stu-id="41f0e-225">To list all the mailboxes for people who live anywhere except Bloomington, here is the command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="41f0e-226">Här är ett exempel på skärmen:</span><span class="sxs-lookup"><span data-stu-id="41f0e-226">Here is an example of the display:</span></span>
  
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

> [!TIP]
>  <span data-ttu-id="41f0e-227">Tolkningen av detta PowerShell-kommando är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen som har en post låda som inte finns i staden Bloomington ( **där {$ \_ . En-EQ "UserMailbox"-and $ \_ . City-Ne "Bloomington"}** ) och visar sedan namnet och staden för varje.</span><span class="sxs-lookup"><span data-stu-id="41f0e-227">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}** ), then display the name and city for each.</span></span>
  
<span data-ttu-id="41f0e-228">Du kan också använda jokertecken i dina PowerShell-filter för att matcha delar av ett namn.</span><span class="sxs-lookup"><span data-stu-id="41f0e-228">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="41f0e-229">Anta till exempel att du letar efter ett användar konto och alla du kan komma ihåg är att deras efter namn var Anderson eller kanske Henderson eller att det var Jorgenson.</span><span class="sxs-lookup"><span data-stu-id="41f0e-229">For example, suppose you're looking for a user account, and all you can remember is that their last name was Anderson, or maybe Henderson, or maybe it was Jorgenson.</span></span>
  
<span data-ttu-id="41f0e-230">Du kan spåra användaren i administrations centret för Microsoft 365 genom att använda sökverktyget och utföra tre olika sökningar:</span><span class="sxs-lookup"><span data-stu-id="41f0e-230">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="41f0e-231">En för  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="41f0e-231">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="41f0e-232">En för  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="41f0e-232">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="41f0e-233">En för  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="41f0e-233">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="41f0e-234">Eftersom alla tre av namnen slutar med "son" kan du se till att PowerShell visar alla användare vars namn slutar på "son".</span><span class="sxs-lookup"><span data-stu-id="41f0e-234">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="41f0e-235">Här är kommandot:</span><span class="sxs-lookup"><span data-stu-id="41f0e-235">Here is the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  <span data-ttu-id="41f0e-236">Tolkningen av det här PowerShell-kommandot är: Hämta alla användare i den aktuella Microsoft 365-prenumerationen, men Använd ett filter som bara visar de användare vars senaste namn slutar med "son" ( **-filter ' {efter namn-like " \* son"} '** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-236">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" ( **-Filter '{LastName -like "\*son"}'** ).</span></span> <span data-ttu-id="41f0e-237">En \* uppsättning tecken som är bokstäver i användarens efter namn.</span><span class="sxs-lookup"><span data-stu-id="41f0e-237">The \* stands for any set of characters, which are letters in the case of the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="41f0e-238">Med PowerShell för Microsoft 365 blir det enkelt att skriva ut eller spara data</span><span class="sxs-lookup"><span data-stu-id="41f0e-238">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="41f0e-239">Med administrations centret för Microsoft 365 kan du Visa listor med data.</span><span class="sxs-lookup"><span data-stu-id="41f0e-239">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="41f0e-240">Här är ett exempel på administrations centret för Skype för företag – online som visar en lista över användare som har Aktiver ATS för Skype för företag – online:</span><span class="sxs-lookup"><span data-stu-id="41f0e-240">Here is an example of the Skype for Business Online Admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Exempel på administrations centret för Skype för företag – online som visar en lista över användare som har Aktiver ATS för Skype för företag – online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="41f0e-242">Om du vill spara informationen i en fil måste du kopiera och klistra in den i ett dokument eller Excel.</span><span class="sxs-lookup"><span data-stu-id="41f0e-242">To save that information to a file, you must copy and paste it into a document or Excel.</span></span> <span data-ttu-id="41f0e-243">I båda fallen kan kopieringen behöva ytterligare formatering.</span><span class="sxs-lookup"><span data-stu-id="41f0e-243">In either case, the copy might require additional formatting.</span></span> <span data-ttu-id="41f0e-244">Administrations centret för Microsoft 365 kan dessutom inte skriva ut den lista som visas direkt.</span><span class="sxs-lookup"><span data-stu-id="41f0e-244">Additionally, the Microsoft 365 admin center does not provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="41f0e-245">Som tur är kan du använda PowerShell för att inte bara visa listan, utan att spara den i en fil som enkelt kan importeras till Excel.</span><span class="sxs-lookup"><span data-stu-id="41f0e-245">Fortunately, you can use PowerShell to not only display the list, but save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="41f0e-246">Här är ett exempel kommando för att spara användar data för Skype för företag – Online i en CSV-fil (kommaseparerade värden), en fil som enkelt kan importeras som en tabell i ett Excel-kalkylblad:</span><span class="sxs-lookup"><span data-stu-id="41f0e-246">Here is an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, a file that can be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="41f0e-247">Här är ett exempel på skärmen:</span><span class="sxs-lookup"><span data-stu-id="41f0e-247">Here is an example of the display:</span></span>
  
![Exempel på en tabell som importer ATS till ett Excel-kalkylblad för användare av Skype för företag – online som sparats i en CSV-fil (kommaseparerade värden).](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  <span data-ttu-id="41f0e-249">Tolkningen av detta PowerShell-kommando är: Hämta alla Skype för företag – Online-användare i den aktuella Microsoft 365-prenumerationen ( **Get-CsOnlineUser** ), skaffa endast användar namn, UPN och plats ( **Välj DisplayName, userPrincipalName, UsageLocation** ) och spara sedan informationen i CSV-filen med namnet C: \\ loggar \\SfBUsers.csv ( **export-CSV-Path "C: \\ logs \\SfBUsers.csv"-NoTypeInformation** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-249">The interpretation of this PowerShell command is: Get all of the Skype for Business Online users in the current Microsoft 365 subscription ( **Get-CsOnlineUser** ), obtain only the user name, UPN, and location ( **Select DisplayName, UserPrincipalName, UsageLocation** ), and then save that information in CSV file named C:\\Logs\\SfBUsers.csv ( **Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation** ).</span></span>
  
<span data-ttu-id="41f0e-250">Du kan också använda alternativen för att spara denna lista som en XML-fil eller som en HTML-sida.</span><span class="sxs-lookup"><span data-stu-id="41f0e-250">You can also use options to save this list as an XML file or as an HTML page.</span></span> <span data-ttu-id="41f0e-251">Med ytterligare PowerShell-kommandon kan du faktiskt spara det direkt som en Excel-fil med eventuell anpassad formatering.</span><span class="sxs-lookup"><span data-stu-id="41f0e-251">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you desire.</span></span> 
  
<span data-ttu-id="41f0e-252">Du kan också skicka utdata från ett PowerShell-kommando som visar en lista direkt till standard skrivaren i Windows.</span><span class="sxs-lookup"><span data-stu-id="41f0e-252">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="41f0e-253">Här är ett exempel kommando:</span><span class="sxs-lookup"><span data-stu-id="41f0e-253">Here is an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="41f0e-254">Så här ser det utskrivna dokumentet ut:</span><span class="sxs-lookup"><span data-stu-id="41f0e-254">Here's what your printed document will look like:</span></span>
  
![Exempel på ett utskrivet dokument som visade att ett PowerShell-kommando visas direkt på standard skrivaren i Windows.](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  <span data-ttu-id="41f0e-256">Tolkningen av det här PowerShell-kommandot är: Hämta alla Skype för företag – Online-användare i den aktuella Microsoft 365-prenumerationen, Hämta endast användar namn, UPN och plats och skicka sedan informationen till standard skrivaren för Windows ( **ut-skrivaren** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-256">The interpretation of this PowerShell command is:  Get all of the Skype for Business Online users in the current Microsoft 365 subscription, obtain only the user name, UPN, and location, and then send that information to the default Windows printer ( **Out-Printer** ).</span></span>
  
<span data-ttu-id="41f0e-257">Det utskrivna dokumentet har samma enkla formatering som visas i PowerShell-Kommandotolken, men när du har skapat ett PowerShell-kommando som visar det du behöver lägger du till **| Ut-skrivaren** till slutet av kommandot för att få en pappers kopia att arbeta från.</span><span class="sxs-lookup"><span data-stu-id="41f0e-257">The printed document has the same simple formatting as the display within the PowerShell command window, but once you have created a PowerShell command to list what you need, you just add **| Out-Printer** to the end of the command to get a hard copy to work from.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="41f0e-258">Med PowerShell för Microsoft 365 kan du hantera olika Server produkter</span><span class="sxs-lookup"><span data-stu-id="41f0e-258">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="41f0e-259">De olika komponenter som utgör Microsoft 365 är utformade för att fungera tillsammans.</span><span class="sxs-lookup"><span data-stu-id="41f0e-259">The different components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="41f0e-260">Anta till exempel att du lägger till en ny användare i Microsoft 365 och anger den informationen som användarens avdelning och telefonnummer när du gör det.</span><span class="sxs-lookup"><span data-stu-id="41f0e-260">For example, suppose you add a new user to Microsoft 365 and, when you do, you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="41f0e-261">Denna information kommer att vara tillgänglig om du använder någon av Microsoft 365-tjänsterna: Skype för företag – Online, Exchange eller SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="41f0e-261">That information will then be available if you access the user's information using any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint Online.</span></span>
  
<span data-ttu-id="41f0e-262">Men det är för gemensam information som omfattar produkterna.</span><span class="sxs-lookup"><span data-stu-id="41f0e-262">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="41f0e-263">Produktspecifika information – till exempel kan information om en användares Exchange-postlåda inte vara tillgänglig i hela paketet.</span><span class="sxs-lookup"><span data-stu-id="41f0e-263">Product-specific information-for example, information about a user's Exchange mailbox-is typically not available across the suite.</span></span> <span data-ttu-id="41f0e-264">Om du till exempel vill veta om en användares post låda är aktive rad eller inte är den informationen bara tillgänglig i administrations centret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="41f0e-264">For example, if you want to know if a user's mailbox is enabled or not, that information is available only in the Exchange Admin center.</span></span> 
  
<span data-ttu-id="41f0e-265">Anta att du vill skapa en rapport som visar följande information för alla dina användare:</span><span class="sxs-lookup"><span data-stu-id="41f0e-265">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="41f0e-266">Användarens visnings namn</span><span class="sxs-lookup"><span data-stu-id="41f0e-266">The user's display name</span></span>
    
- <span data-ttu-id="41f0e-267">Om användaren är licensierad för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41f0e-267">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="41f0e-268">Om användarens Exchange-postlåda har Aktiver ATS</span><span class="sxs-lookup"><span data-stu-id="41f0e-268">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="41f0e-269">Om användaren är aktive rad för Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="41f0e-269">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="41f0e-270">Du kan för närvarande inte använda administrations centret för Microsoft 365 för att enkelt skapa en sådan rapport.</span><span class="sxs-lookup"><span data-stu-id="41f0e-270">You currently cannot use the Microsoft 365 admin center to easily produce such a report.</span></span> <span data-ttu-id="41f0e-271">I stället måste du skapa ett separat dokument för att lagra informationen, till exempel ett Excel-kalkylblad, och få alla användar namn och licensierings information från administrations centret för Microsoft 365, hämta information om post lådor från administrations centret för Exchange, få information om Skype för företag – Online från administrations centret för Skype för företag – Online och sedan sortera och kombinera den informationen.</span><span class="sxs-lookup"><span data-stu-id="41f0e-271">Instead, you'll have to create a separate document to store the information, like an Excel worksheet, and get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then collate and combine that information.</span></span>
  
<span data-ttu-id="41f0e-272">Alternativet är att använda ett PowerShell-skript för att kompilera rapporten åt dig.</span><span class="sxs-lookup"><span data-stu-id="41f0e-272">The alternative is to use a PowerShell script to compile that report for you.</span></span>
  
<span data-ttu-id="41f0e-273">Följande exempel skript är mer komplicerat än de kommandon du har sett hittills i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="41f0e-273">The following example script is more complicated than the commands you have seen so far in this article.</span></span> <span data-ttu-id="41f0e-274">Men det visar potentialen för att använda PowerShell för att skapa vyer av information som är mycket svår att göra.</span><span class="sxs-lookup"><span data-stu-id="41f0e-274">But, it shows the potential of using PowerShell to create views of information that are very difficult to do otherwise.</span></span> <span data-ttu-id="41f0e-275">Här är det skript som kan kompilera och visa en nödvändig lista:</span><span class="sxs-lookup"><span data-stu-id="41f0e-275">Here is the script that can compile and display the needed list:</span></span>
  
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

<span data-ttu-id="41f0e-276">Här är ett exempel på skärmen:</span><span class="sxs-lookup"><span data-stu-id="41f0e-276">Here is an example of the display:</span></span>
  
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

<span data-ttu-id="41f0e-277">Tolkningen av det här PowerShell-skriptet är:</span><span class="sxs-lookup"><span data-stu-id="41f0e-277">The interpretation of this PowerShell script is:</span></span>  

- <span data-ttu-id="41f0e-278">Hämta alla användare i den aktuella Microsoft 365-prenumerationen och lagra informationen i en variabel som heter $x ( **$x = get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-278">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="41f0e-279">Starta en loop som körs över alla användare i variabeln som heter $x **$i (fram$x)** .</span><span class="sxs-lookup"><span data-stu-id="41f0e-279">Start a loop that runs over all the users in the variable named $x ( **foreach ($i in $x)** ).</span></span>  
- <span data-ttu-id="41f0e-280">Definiera en variabel som heter $y och lagra användarens post lådans information ( **$y = Get-Mailbox-Identity $i. UserPrincipalName** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-280">Define a variable named $y and store the user's mailbox information in it ( **$y = Get-Mailbox -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="41f0e-281">Lägga till en ny egenskap i användar informationen som heter IsMailBoxEnabled och ange värdet för egenskapen IsMailBoxEnabled för användarens post låda ( **$i | Add-member-MemberType NoteProperty IsMailboxEnabled-Value $y. IsMailboxEnabled** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-281">Add a new property to the user information named IsMailBoxEnabled and set it to the value of the IsMailBoxEnabled property of the user's mailbox ( **$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled** ).</span></span>
- <span data-ttu-id="41f0e-282">Definiera en variabel som heter $y och lagra användarens information om Skype för företag – Online ( **$y = get-CsOnlineUser-Identity $i. UserPrincipalName** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-282">Define a variable named $y and store the user's Skype for Business Online information in it ( **$y = Get-CsOnlineUser -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="41f0e-283">Lägga till en ny egenskap i användar informationen med namnet EnabledForSfB och ange värdet för egenskapen Enabled för användarens information om Skype för företag – Online ( **$i | Add-member-MemberType NoteProperty EnabledForSfB-Value $y. enabled** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-283">Add a new property to the user information named EnabledForSfB and set it to the value of the Enabled property of the user's Skype for Business Online information ( **$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled** ).</span></span>
- <span data-ttu-id="41f0e-284">Visa listan med användare, men bara ange deras namn, om de är licensierade och de två nya egenskaperna som visar om sin post låda är aktive rad och om den är aktive rad för Skype för företag – Online ( **$x | Välj DisplayName, Ärlicensierad, IsMailboxEnabled, EnabledforSfB** ).</span><span class="sxs-lookup"><span data-stu-id="41f0e-284">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41f0e-285">Se även</span><span class="sxs-lookup"><span data-stu-id="41f0e-285">See also</span></span>

[<span data-ttu-id="41f0e-286">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41f0e-286">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="41f0e-287">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="41f0e-287">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="41f0e-288">Använda Windows PowerShell för att skapa rapporter i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41f0e-288">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)

