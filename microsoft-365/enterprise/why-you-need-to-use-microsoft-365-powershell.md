---
title: Varför du behöver använda PowerShell för Microsoft 365
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
description: Sammanfattning Förstå varför du måste använda PowerShell för att hantera Microsoft 365, i vissa fall mer effektivt och i andra fall efter behov.
ms.openlocfilehash: a60220001a148b3a24a996bb6e0154f80214b019
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924594"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="f9647-103">Varför du behöver använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f9647-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="f9647-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f9647-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f9647-105">Med hjälp Microsoft 365 kan du hantera dina Microsoft 365 och licenser.</span><span class="sxs-lookup"><span data-stu-id="f9647-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="f9647-106">Du kan också hantera dina Microsoft 365 tjänster, till exempel Exchange Online, Teams och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f9647-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="f9647-107">Om du i stället använder PowerShell för att hantera de här tjänsterna kan du och dra nytta av kommandorads- och skriptspråkmiljön för hastighet, automatisering och ytterligare funktioner.</span><span class="sxs-lookup"><span data-stu-id="f9647-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="f9647-108">Den här artikeln visar hur du använder PowerShell för att Microsoft 365 till:</span><span class="sxs-lookup"><span data-stu-id="f9647-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="f9647-109">Visa ytterligare information som du inte kan se i Microsoft 365 administrationscenter</span><span class="sxs-lookup"><span data-stu-id="f9647-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="f9647-110">Konfigurera funktioner och inställningar som endast är möjliga med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9647-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="f9647-111">Massåtgärder</span><span class="sxs-lookup"><span data-stu-id="f9647-111">Do bulk operations</span></span>
    
- <span data-ttu-id="f9647-112">Filtrera data</span><span class="sxs-lookup"><span data-stu-id="f9647-112">Filter data</span></span>
    
- <span data-ttu-id="f9647-113">Skriva ut eller spara data</span><span class="sxs-lookup"><span data-stu-id="f9647-113">Print or save data</span></span>
    
- <span data-ttu-id="f9647-114">Hantera mellan tjänster</span><span class="sxs-lookup"><span data-stu-id="f9647-114">Manage across services</span></span>
    
<span data-ttu-id="f9647-115">Kom ihåg att PowerShell för Microsoft 365 är en uppsättning moduler för Windows PowerShell, som är en kommandoradsmiljö för Windows-baserade tjänster och plattformar.</span><span class="sxs-lookup"><span data-stu-id="f9647-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="f9647-116">I den här miljön skapas ett kommandogränssnittsspråk som kan utökas med ytterligare moduler.</span><span class="sxs-lookup"><span data-stu-id="f9647-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="f9647-117">Det är ett sätt att utföra enkla eller komplexa kommandon eller skript.</span><span class="sxs-lookup"><span data-stu-id="f9647-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="f9647-118">När du har installerat PowerShell för Microsoft 365-moduler och ansluter till din Microsoft 365-prenumeration kan du till exempel köra följande kommando för att visa alla användarpostlådor för Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="f9647-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="f9647-119">Du kan också visa listan över postlådor med hjälp av administrationscentret för Microsoft 365, men det är inte enkelt att räkna objekten i alla listor för alla webbplatser för alla dina webbappar.</span><span class="sxs-lookup"><span data-stu-id="f9647-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="f9647-120">PowerShell för Microsoft 365 har utformats för att hjälpa dig att hantera Microsoft 365, inte för att ersätta Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="f9647-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="f9647-121">Administratörer måste kunna använda PowerShell för Microsoft 365 eftersom det finns vissa konfigurationsprocedurer som bara kan göras via PowerShell för Microsoft 365 kommandon.</span><span class="sxs-lookup"><span data-stu-id="f9647-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="f9647-122">I dessa fall behöver du veta hur du:</span><span class="sxs-lookup"><span data-stu-id="f9647-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="f9647-123">Installera PowerShell för Microsoft 365 -moduler (görs bara en gång för varje administratörsdator).</span><span class="sxs-lookup"><span data-stu-id="f9647-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="f9647-124">Anslut prenumerationen på Microsoft 365 (en gång för varje PowerShell-session).</span><span class="sxs-lookup"><span data-stu-id="f9647-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="f9647-125">Samla in den information som behövs för att köra nödvändiga PowerShell för Microsoft 365-kommandon.</span><span class="sxs-lookup"><span data-stu-id="f9647-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="f9647-126">Kör PowerShell för Microsoft 365 kommandon.</span><span class="sxs-lookup"><span data-stu-id="f9647-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="f9647-127">När du har lärt dig dessa grundläggande kunskaper behöver du inte lista dina postlådeanvändare med hjälp av **kommandot Hämta** postlåda.</span><span class="sxs-lookup"><span data-stu-id="f9647-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="f9647-128">Du behöver inte heller förstå hur du skapar ett nytt kommando, som det citerade kommandot tidigare, för att räkna alla objekt i alla listor för alla webbplatser för alla dina webbappar.</span><span class="sxs-lookup"><span data-stu-id="f9647-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="f9647-129">Microsoft och administratörsgemenskapen kan hjälpa dig med sådana uppgifter vid behov.</span><span class="sxs-lookup"><span data-stu-id="f9647-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="f9647-130">PowerShell för Microsoft 365 kan visa information som du inte kan se Microsoft 365 administrationscentret för e-Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9647-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="f9647-131">I Microsoft 365 administrationscenter visas många användbara uppgifter.</span><span class="sxs-lookup"><span data-stu-id="f9647-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="f9647-132">Men den visar inte all information som kan Microsoft 365 användare, licenser, postlådor och webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f9647-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="f9647-133">Här är ett exempel för *användare och grupper* i Microsoft 365 administrationscentret:</span><span class="sxs-lookup"><span data-stu-id="f9647-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Exempel på visning av användare och grupper i Microsoft 365 administrationscenter.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="f9647-135">Den här vyn innehåller information som du behöver i många fall.</span><span class="sxs-lookup"><span data-stu-id="f9647-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="f9647-136">Men det finns tillfällen när du behöver mer.</span><span class="sxs-lookup"><span data-stu-id="f9647-136">However, there are times when you need more.</span></span> <span data-ttu-id="f9647-137">Till exempel Microsoft 365 licensiering (och de Microsoft 365 som är tillgängliga för en användare) beror delvis på användarens geografiska position.</span><span class="sxs-lookup"><span data-stu-id="f9647-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="f9647-138">Principerna och funktionerna som du kan utöka till en användare som bor i USA kanske inte är desamma som de som du kan utöka till en användare i Indien eller Belgien.</span><span class="sxs-lookup"><span data-stu-id="f9647-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="f9647-139">Följ anvisningarna i Microsoft 365 administrationscenter för att avgöra en användares geografiska position:</span><span class="sxs-lookup"><span data-stu-id="f9647-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="f9647-140">Dubbelklicka på användarens **visningsnamn**.</span><span class="sxs-lookup"><span data-stu-id="f9647-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="f9647-141">Välj information i visningsfönstret för **användaregenskaper.**</span><span class="sxs-lookup"><span data-stu-id="f9647-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="f9647-142">Välj ytterligare information i **informationsvisningen.**</span><span class="sxs-lookup"><span data-stu-id="f9647-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="f9647-143">Bläddra tills du hittar rubriken **Land eller region:**</span><span class="sxs-lookup"><span data-stu-id="f9647-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Exempel på regioninformation för en användare i Microsoft 365 administrationscenter.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="f9647-145">Skriv användarens visningsnamn och plats på ett papper eller kopiera och klistra in det i Anteckningar.</span><span class="sxs-lookup"><span data-stu-id="f9647-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="f9647-146">Du måste upprepa proceduren för varje användare.</span><span class="sxs-lookup"><span data-stu-id="f9647-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="f9647-147">Om du har många användare kan det vara omtiga i den här processen.</span><span class="sxs-lookup"><span data-stu-id="f9647-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="f9647-148">Med PowerShell för Microsoft 365 kan du visa den här informationen för alla dina användare genom att använda följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f9647-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="f9647-149">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell och cmdlets som har *Msol* i sitt namn.</span><span class="sxs-lookup"><span data-stu-id="f9647-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="f9647-150">Du måste köra dessa cmdlets från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9647-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="f9647-151">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="f9647-151">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="f9647-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user **(Select DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="f9647-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="f9647-153">Eftersom PowerShell för Microsoft 365 har stöd för ett kommandogränssnittsspråk kan du ändra informationen som fås med **kommandot Get-AzureADUser** ytterligare.</span><span class="sxs-lookup"><span data-stu-id="f9647-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="f9647-154">Du kanske till exempel vill sortera de här användarna efter deras plats, gruppera alla brasilianska användare tillsammans, alla USA-användare tillsammans och så vidare.</span><span class="sxs-lookup"><span data-stu-id="f9647-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="f9647-155">Här är kommandot:</span><span class="sxs-lookup"><span data-stu-id="f9647-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="f9647-156">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="f9647-156">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="f9647-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span><span class="sxs-lookup"><span data-stu-id="f9647-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="f9647-158">Du kan också använda ytterligare filtrering.</span><span class="sxs-lookup"><span data-stu-id="f9647-158">You can also use additional filtering.</span></span> <span data-ttu-id="f9647-159">Om du till exempel bara vill se information om användare i Brasilien använder du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="f9647-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="f9647-160">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="f9647-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="f9647-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$ \_ . Användningsplats -eq "BR"}**) och visa sedan namn och plats för varje användare.</span><span class="sxs-lookup"><span data-stu-id="f9647-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="f9647-162">**En anmärkning om stora domäner**</span><span class="sxs-lookup"><span data-stu-id="f9647-162">**A note about large domains**</span></span>
  
<span data-ttu-id="f9647-163">Om du har en stor domän med tusentals användare kan det leda till begränsning genom att prova några av exemplen som visas i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f9647-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="f9647-164">Baserat på faktorer som att beräkna ström och tillgänglig nätverksbandbredd kanske du försöker göra för mycket på en gång.</span><span class="sxs-lookup"><span data-stu-id="f9647-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="f9647-165">Stora organisationer kanske vill dela upp några av dessa PowerShell-åtgärder i två kommandon.</span><span class="sxs-lookup"><span data-stu-id="f9647-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="f9647-166">Följande kommando returnerar till exempel alla användarkonton och visar namn och plats för varje konto:</span><span class="sxs-lookup"><span data-stu-id="f9647-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="f9647-167">Det fungerar bra för mindre domäner.</span><span class="sxs-lookup"><span data-stu-id="f9647-167">That works great for smaller domains.</span></span> <span data-ttu-id="f9647-168">Men i en stor organisation kanske du vill dela upp åtgärden i två kommandon: ett kommando för att lagra användarkontoinformationen i en variabel och en annan för att visa den information som behövs.</span><span class="sxs-lookup"><span data-stu-id="f9647-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="f9647-169">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f9647-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="f9647-170">Så här tolkar du den här uppsättningen PowerShell-kommandon:</span><span class="sxs-lookup"><span data-stu-id="f9647-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="f9647-171">Hämta alla användare i den aktuella Microsoft 365-prenumerationen och lagra informationen i en variabel med namnet $x (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="f9647-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="f9647-172">Visa innehållet i variabeln *$x*, men bara inkludera namn och plats för varje användare (**$x | Välj Visningsnamn, Användningsbeläggning**).</span><span class="sxs-lookup"><span data-stu-id="f9647-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="f9647-173">Microsoft 365 funktioner som du bara kan konfigurera med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f9647-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="f9647-174">Administrationscentret Microsoft 365 för att ge åtkomst till vanliga, användbara administrativa uppgifter som gäller för de flesta miljöer.</span><span class="sxs-lookup"><span data-stu-id="f9647-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="f9647-175">Med andra ord har Microsoft 365 administrationscentret utformats så att den vanliga administratören kan utföra de vanligaste hanteringsuppgifterna.</span><span class="sxs-lookup"><span data-stu-id="f9647-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="f9647-176">Men det finns vissa uppgifter som inte kan utföras i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="f9647-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="f9647-177">I administrationscentret för Skype för företag online finns till exempel några alternativ för att skapa anpassade mötesinbjudningar:</span><span class="sxs-lookup"><span data-stu-id="f9647-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Exempel på visning av anpassade mötesinbjudningar i administrationscentret Skype för företag Online.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="f9647-179">Med de här inställningarna kan du anpassa mötesinbjudningar genom att anpassa dem.</span><span class="sxs-lookup"><span data-stu-id="f9647-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="f9647-180">Men det finns mer att göra inställningar för möteskonfiguration än att bara skapa anpassade mötesinbjudningar.</span><span class="sxs-lookup"><span data-stu-id="f9647-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="f9647-181">Som standard tillåter möten till exempel:</span><span class="sxs-lookup"><span data-stu-id="f9647-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="f9647-182">Anonyma användare att få automatisk ingång till varje möte.</span><span class="sxs-lookup"><span data-stu-id="f9647-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="f9647-183">Deltagare om du vill spela in mötet.</span><span class="sxs-lookup"><span data-stu-id="f9647-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="f9647-184">Alla användare i organisationen som ska utses till presentatörer när de ansluter till mötet.</span><span class="sxs-lookup"><span data-stu-id="f9647-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="f9647-185">De här inställningarna är inte tillgängliga från administrationscentret Skype för företag Online.</span><span class="sxs-lookup"><span data-stu-id="f9647-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="f9647-186">Du kan styra dem från PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9647-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="f9647-187">Här är ett kommando som inaktiverar dessa tre inställningar:</span><span class="sxs-lookup"><span data-stu-id="f9647-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="f9647-188">Om du vill köra det här kommandot måste du installera [Skype för företag Online PowerShell-modulen ](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="f9647-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="f9647-189">Tolkning av det här PowerShell-kommandot är:</span><span class="sxs-lookup"><span data-stu-id="f9647-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="f9647-190">I inställningarna för nya Skype för företag **Online-möten (Set-CsMeetingConfiguration),** inaktiverar du att anonyma användare får automatisk ingång till möten (**-AdmitAnonymousUsersByDefault $False**).</span><span class="sxs-lookup"><span data-stu-id="f9647-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="f9647-191">Inaktivera möjligheten för deltagare att spela in möten (**-AllowConferenceRecording $False**).</span><span class="sxs-lookup"><span data-stu-id="f9647-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="f9647-192">Ange inte alla användare från organisationen som presentatörer (**-DesignateAsPresenter "None"**).</span><span class="sxs-lookup"><span data-stu-id="f9647-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="f9647-193">Om du vill återställa de här standardinställningarna (aktivera alternativen) kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="f9647-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="f9647-194">Det finns även andra liknande scenarier, och därför bör administratörer veta hur man kör PowerShell för Microsoft 365 kommandon.</span><span class="sxs-lookup"><span data-stu-id="f9647-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="f9647-195">PowerShell för Microsoft 365 är perfekt för massåtgärder</span><span class="sxs-lookup"><span data-stu-id="f9647-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="f9647-196">Visuella gränssnitt som Microsoft 365 administrationscentret är mest värdefulla när du har en enda åtgärd att göra.</span><span class="sxs-lookup"><span data-stu-id="f9647-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="f9647-197">Om du till exempel behöver inaktivera ett användarkonto kan du använda administrationscentret för att snabbt hitta och avmarkera en kryssruta.</span><span class="sxs-lookup"><span data-stu-id="f9647-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="f9647-198">Det kan vara enklare än att utföra en liknande åtgärd i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9647-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="f9647-199">Men om du måste ändra många saker eller vissa valda saker i en stor uppsättning av andra saker kanske Microsoft 365 administrationscentret inte är det bästa verktyget.</span><span class="sxs-lookup"><span data-stu-id="f9647-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="f9647-200">Säg till exempel att du måste ändra prefixet på tusentals telefonnummer eller ta bort den specifika användaren *Ken Myer* från alla dina SharePoint Online-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f9647-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="f9647-201">Hur gör du det i Microsoft 365 administrationscenter?</span><span class="sxs-lookup"><span data-stu-id="f9647-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="f9647-202">I det sista exemplet säger vi att du har flera hundra SharePoint -webbplatser online och du inte vet vilka Ken Meyer är medlem i.</span><span class="sxs-lookup"><span data-stu-id="f9647-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="f9647-203">Du måste först börja på Microsoft 365 och sedan utföra den här proceduren för varje webbplats:</span><span class="sxs-lookup"><span data-stu-id="f9647-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="f9647-204">Välj **webbplatsens URL.**</span><span class="sxs-lookup"><span data-stu-id="f9647-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="f9647-205">I **egenskapsrutan för webbplatssamlingen** väljer **du länken Webbplatsadress** för att öppna webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="f9647-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="f9647-206">På webbplatsen väljer du **Dela**.</span><span class="sxs-lookup"><span data-stu-id="f9647-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="f9647-207">I **dialogrutan Dela** väljer du länken som visar alla användare som har behörighet till webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="f9647-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![Exempel på visning av medlemmar i en SharePoint Online-webbplats i SharePoint Online-administrationscentret.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="f9647-209">Välj **Avancerat i** dialogrutan Delas **med.**</span><span class="sxs-lookup"><span data-stu-id="f9647-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="f9647-210">Bläddra nedåt i listan med användare, hitta och välj Ken Myer (förutsatt att han har behörighet till webbplatsen) och välj sedan **Ta bort användarbehörigheter.**</span><span class="sxs-lookup"><span data-stu-id="f9647-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="f9647-211">Det skulle ta *lång tid* för flera hundra webbplatser.</span><span class="sxs-lookup"><span data-stu-id="f9647-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="f9647-212">Alternativet är att köra följande kommando i PowerShell för att Microsoft 365 ta bort Ken Myer från alla dina webbplatser:</span><span class="sxs-lookup"><span data-stu-id="f9647-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="f9647-213">Det här kommandot kräver att du installerar [SharePoint PowerShell-modulen](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="f9647-213">This command requires that you install the [SharePoint Online PowerShell module](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="f9647-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it **(ForEach {Remove-SPOUser -Site $ \_ . URL -LoginName "kenmyer \@ litwareinc.com"}**).</span><span class="sxs-lookup"><span data-stu-id="f9647-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="f9647-215">Vi ser Microsoft 365 ta bort Ken Meyer från alla webbplatser, inklusive sådana som han inte har tillgång till.</span><span class="sxs-lookup"><span data-stu-id="f9647-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="f9647-216">Resultatet kommer därför att visa fel för de webbplatser som han inte har tillgång till.</span><span class="sxs-lookup"><span data-stu-id="f9647-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="f9647-217">Vi kan använda ytterligare villkor för det här kommandot för att endast ta bort Ken Meyer från de webbplatser där ken finns med på deras inloggningslista.</span><span class="sxs-lookup"><span data-stu-id="f9647-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="f9647-218">Men de fel som returneras gör ingen skada för webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="f9647-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="f9647-219">Det här kommandot kan ta några minuter att köra mot hundratals webbplatser, i stället för timmar av arbete via Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="f9647-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="f9647-220">Här är ett annat exempel på massåtgärd.</span><span class="sxs-lookup"><span data-stu-id="f9647-220">Here's another bulk operation example.</span></span> <span data-ttu-id="f9647-221">Använd det här kommandot för att *lägga till Bonnie Kearney*, SharePoint administratör, på alla webbplatser i organisationen:</span><span class="sxs-lookup"><span data-stu-id="f9647-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="f9647-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $ \_ . URL -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**).</span><span class="sxs-lookup"><span data-stu-id="f9647-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="f9647-223">PowerShell för Microsoft 365 ett bra sätt att filtrera data</span><span class="sxs-lookup"><span data-stu-id="f9647-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="f9647-224">I Microsoft 365 finns flera sätt att filtrera data för att enkelt hitta en riktad delmängd information.</span><span class="sxs-lookup"><span data-stu-id="f9647-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="f9647-225">Till exempel Exchange det enkelt att filtrera på praktiskt taget alla egendom för en användarpostlåda.</span><span class="sxs-lookup"><span data-stu-id="f9647-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="f9647-226">Här är till exempel listan över postlådor för alla användare som bor i staden Bloomington:</span><span class="sxs-lookup"><span data-stu-id="f9647-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Exempel på att göra en avancerad sökning i Microsoft 365 administrationscenter för listan över postlådor för alla användare som bor i staden Bloomington.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="f9647-228&quot;>I Exchange administrationscenter kan du också kombinera filtervillkor.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9647-228&quot;>The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id=&quot;f9647-229&quot;>Du kan till exempel hitta postlådorna för alla personer som bor i Bloomington och arbeta på ekonomiavdelningen.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9647-229&quot;>For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id=&quot;f9647-230&quot;>Men det finns begränsningar för vad du kan göra Exchange administrationscentret.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9647-230&quot;>But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id=&quot;f9647-231&quot;>Det gick till exempel inte lika lätt att hitta postlådorna för personer som bor i *Bloomington* eller San Bloom, eller postlådorna för alla personer som inte bor i Bloomington.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9647-231&quot;>For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id=&quot;f9647-232&quot;>Du kan använda följande PowerShell för Microsoft 365-kommando om du vill visa en lista med postlådor för alla som bor i Bloomington eller San Helena:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f9647-232&quot;>You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq &quot;UserMailbox&quot; -and ($_.City -eq &quot;San Diego&quot; -or $_.City -eq &quot;Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="f9647-233">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="f9647-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="f9647-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Bloomington (**Where {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and ($ \_ . Ort -eq "San Turk" -eller $ \_ . Ort -eq "Bloomington")}**) och visa sedan namn och ort för varje **(Välj visningsnamn, ort**).</span><span class="sxs-lookup"><span data-stu-id="f9647-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="f9647-235">Och här är kommandot för att visa alla postlådor för personer som bor var som helst utom Bloomington:</span><span class="sxs-lookup"><span data-stu-id="f9647-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="f9647-236">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="f9647-236">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="f9647-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and $ \_ . Ort -ne "Bloomington"}**) och visa sedan namn och ort för varje.</span><span class="sxs-lookup"><span data-stu-id="f9647-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="f9647-238">Använda jokertecken</span><span class="sxs-lookup"><span data-stu-id="f9647-238">Use wildcards</span></span>

<span data-ttu-id="f9647-239">Du kan också använda jokertecken i PowerShell-filter för att matcha en del av ett namn.</span><span class="sxs-lookup"><span data-stu-id="f9647-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="f9647-240">Anta till exempel att du letar efter ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="f9647-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="f9647-241">Allt du kan komma ihåg är att användarens efternamn var *Magnus eller Kanske* Magnus eller *Omsson.* </span><span class="sxs-lookup"><span data-stu-id="f9647-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="f9647-242">Du kan spåra användaren i administrationscentret Microsoft 365 med sökverktyget och utföra tre olika sökningar:</span><span class="sxs-lookup"><span data-stu-id="f9647-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="f9647-243">One for  *En för Förend*</span><span class="sxs-lookup"><span data-stu-id="f9647-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="f9647-244">One for  *En för Förend*</span><span class="sxs-lookup"><span data-stu-id="f9647-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="f9647-245">One for  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="f9647-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="f9647-246">Eftersom alla tre namnen slutar på "son" kan du ange att PowerShell ska visa alla användare vars namn slutar med "son".</span><span class="sxs-lookup"><span data-stu-id="f9647-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="f9647-247">Här är kommandot:</span><span class="sxs-lookup"><span data-stu-id="f9647-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="f9647-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like " \* son"}'**).</span><span class="sxs-lookup"><span data-stu-id="f9647-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="f9647-249">De \* står för alla tecken , det vill vara bokstäver i användarens efternamn.</span><span class="sxs-lookup"><span data-stu-id="f9647-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="f9647-250">PowerShell för Microsoft 365 gör det enkelt att skriva ut eller spara data</span><span class="sxs-lookup"><span data-stu-id="f9647-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="f9647-251">I Microsoft 365 administrationscenter kan du visa listor med data.</span><span class="sxs-lookup"><span data-stu-id="f9647-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="f9647-252">Här är ett exempel på hur Skype för företag Online-administrationscentret visar en lista över användare som har aktiverats för Skype för företag Online:</span><span class="sxs-lookup"><span data-stu-id="f9647-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Exempel på Skype för företag onlineadministrationscentret som visar en lista över användare som har aktiverats för Skype för företag Online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="f9647-254">Om du vill spara informationen i en fil måste du klistra in den i ett dokument Microsoft Excel kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="f9647-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="f9647-255">Endera fall kan kräva ytterligare formatering.</span><span class="sxs-lookup"><span data-stu-id="f9647-255">Either case might require additional formatting.</span></span> <span data-ttu-id="f9647-256">Dessutom går det Microsoft 365 kan skriva ut den visade listan direkt i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="f9647-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="f9647-257">Som tur är kan du använda PowerShell för att inte bara visa listan utan för att spara den i en fil som enkelt kan importeras till Excel.</span><span class="sxs-lookup"><span data-stu-id="f9647-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="f9647-258">Här är ett exempelkommando för att spara Skype för företag Online-användardata i en FIL med kommaavgränsade värden (CSV), som sedan enkelt kan importeras som en tabell i ett Excel kalkylblad:</span><span class="sxs-lookup"><span data-stu-id="f9647-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="f9647-259">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="f9647-259">Here's an example of the results:</span></span>
  
![Exempel på en tabell som importerats till ett Excel kalkylblad för Skype för företag av användardata online som har sparats i en fil med kommaavgränsade värden.](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="f9647-261">The interpretation of this PowerShell command is: Get all the Skype för företag Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); endast skaffa användarnamn, UPN och plats **(Välj DisplayName, UserPrincipalName, UsageLocation**); och sparar sedan informationen i en CSV-fil med namnet C: \\ Loggar \\SfBUsers.csv (**Export-Csv -Path "C: \\ Logs \\SfBUsers.csv" -NoTypeInformation**).</span><span class="sxs-lookup"><span data-stu-id="f9647-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="f9647-262">Du kan också använda alternativ för att spara listan som en XML-fil eller en HTML-sida.</span><span class="sxs-lookup"><span data-stu-id="f9647-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="f9647-263">Med ytterligare PowerShell-kommandon kan du spara det direkt som en Excel, med valfri anpassad formatering.</span><span class="sxs-lookup"><span data-stu-id="f9647-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="f9647-264">Du kan också skicka utdata från ett PowerShell-kommando som visar en lista direkt till standardskrivaren i Windows.</span><span class="sxs-lookup"><span data-stu-id="f9647-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="f9647-265">Här är ett exempelkommando:</span><span class="sxs-lookup"><span data-stu-id="f9647-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="f9647-266">Så här kommer det utskrivna dokumentet att se ut:</span><span class="sxs-lookup"><span data-stu-id="f9647-266">Here's what your printed document will look like:</span></span>
  
![Exempel på utskrivet dokument som utdata från ett PowerShell-kommando som skickas direkt till standardskrivaren i Windows.](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="f9647-268">The interpretation of this PowerShell command is: Get all the Skype för företag Online users in the current Microsoft 365 subscription; endast få användarnamn, UPN och plats; och skicka informationen till standardskrivaren Windows (**Utskrivare).**</span><span class="sxs-lookup"><span data-stu-id="f9647-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="f9647-269">Det utskrivna dokumentet har samma enkla formatering som visningen i PowerShell-kommandofönstret.</span><span class="sxs-lookup"><span data-stu-id="f9647-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="f9647-270">Om du vill ha en papperskopia behöver du bara lägga **till | Skriv ut** till slutet av kommandot.</span><span class="sxs-lookup"><span data-stu-id="f9647-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="f9647-271">Med PowerShell för Microsoft 365 kan du hantera i olika serverprodukter</span><span class="sxs-lookup"><span data-stu-id="f9647-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="f9647-272">De komponenter som ingår i Microsoft 365 är utformade för att fungera tillsammans.</span><span class="sxs-lookup"><span data-stu-id="f9647-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="f9647-273">Anta till exempel att du lägger till en ny användare Microsoft 365 och anger sådan information som användarens avdelning och telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="f9647-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="f9647-274">Den informationen blir sedan tillgänglig om du kommer åt användarens information i någon av Microsoft 365-tjänsterna: Skype för företag Online, Exchange eller SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f9647-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="f9647-275">Men det är för vanlig information som spänner över produktsviten.</span><span class="sxs-lookup"><span data-stu-id="f9647-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="f9647-276">Produktspecifik information, till exempel information om en användares e Exchange postlåda, är vanligtvis inte tillgänglig i hela programsviten.</span><span class="sxs-lookup"><span data-stu-id="f9647-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="f9647-277">Information om till exempel om en användares postlåda är aktiverad eller inte är tillgänglig endast i Exchange administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="f9647-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="f9647-278">Anta att du vill skapa en rapport som visar följande information för alla användare:</span><span class="sxs-lookup"><span data-stu-id="f9647-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="f9647-279">Användarens visningsnamn</span><span class="sxs-lookup"><span data-stu-id="f9647-279">The user's display name</span></span>
    
- <span data-ttu-id="f9647-280">Om användaren är licensierad för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f9647-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="f9647-281">Om användarens e Exchange postlåda har aktiverats</span><span class="sxs-lookup"><span data-stu-id="f9647-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="f9647-282">Om användaren är aktiverad för Skype för företag Online</span><span class="sxs-lookup"><span data-stu-id="f9647-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="f9647-283">Det är inte enkelt att skapa en sådan rapport i Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="f9647-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f9647-284">I stället måste du skapa ett separat dokument för att lagra informationen, till exempel ett Excel kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="f9647-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="f9647-285">Hämta sedan alla användarnamn och all licensinformation från administrationscentret för Microsoft 365, hämta postlådeinformation från administrationscentret för Exchange, hämta Skype för företag Online-information från administrationscentret för Skype för företag Online och kombinera informationen.</span><span class="sxs-lookup"><span data-stu-id="f9647-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="f9647-286">Alternativet är att använda ett PowerShell-skript för att sammanställa rapporten åt dig.</span><span class="sxs-lookup"><span data-stu-id="f9647-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="f9647-287">Följande exempelskript är mer komplicerat än de kommandon som du har sett hittills i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f9647-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="f9647-288">Men det visar potentialen för att använda PowerShell för att skapa informationsvyer som är svåra att få annars.</span><span class="sxs-lookup"><span data-stu-id="f9647-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="f9647-289">Här är skriptet för att kompilera och visa den lista du behöver:</span><span class="sxs-lookup"><span data-stu-id="f9647-289">Here's the script to compile and display the list you need:</span></span>
  
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

<span data-ttu-id="f9647-290">Här är ett exempel på resultatet:</span><span class="sxs-lookup"><span data-stu-id="f9647-290">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="f9647-291">Tolkning av det här PowerShell-skriptet är:</span><span class="sxs-lookup"><span data-stu-id="f9647-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="f9647-292">Hämta alla användare i den aktuella Microsoft 365-prenumerationen och lagra informationen i en variabel som heter *$x* (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="f9647-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="f9647-293">Starta en slinga som körs över alla användare i variabeln $x (**foreach ($i i $x)**).</span><span class="sxs-lookup"><span data-stu-id="f9647-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="f9647-294">Definiera en variabel *med namnet $y* och lagra användarens postlådeinformation i den ( $y = Get-Mailbox **-Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="f9647-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="f9647-295">Lägga till en ny egenskap i användarinformationen med namnet *IsMailBoxEnabled.*</span><span class="sxs-lookup"><span data-stu-id="f9647-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="f9647-296">Ange värdet för egenskapen IsMailBoxEnabled för användarens postlåda (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="f9647-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="f9647-297">Definiera en variabel *med namnet $y* och lagra användarens Skype för företag Online-information i den ( $y = Get-CsOnlineUser **-Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="f9647-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="f9647-298">Lägg till en ny egenskap i användarinformationen som heter *EnabledForSfB.*</span><span class="sxs-lookup"><span data-stu-id="f9647-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="f9647-299">Ange värdet för egenskapen Enabled för användarens onlineinformation för Skype för företag (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span><span class="sxs-lookup"><span data-stu-id="f9647-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="f9647-300">Visa listan med användare, men ta bara med deras namn, om de är licensierade och de två nya egenskaperna som anger om deras postlåda är aktiverad och om de är aktiverade för Skype för företag Online (**$x | Välj DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span><span class="sxs-lookup"><span data-stu-id="f9647-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f9647-301">Se även</span><span class="sxs-lookup"><span data-stu-id="f9647-301">See also</span></span>

[<span data-ttu-id="f9647-302">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f9647-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f9647-303">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9647-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f9647-304">Använda Windows PowerShell för att skapa rapporter i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f9647-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)