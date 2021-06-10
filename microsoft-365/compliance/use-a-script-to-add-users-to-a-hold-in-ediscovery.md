---
title: Använda ett skript för att lägga till användare i ett ärende för bas-eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Lär dig hur du kör ett skript för att lägga & OneDrive för företag postlådor på en ny plats som är kopplad till ett eDiscovery-ärende Microsoft 365 efterlevnadscenter.
ms.openlocfilehash: d6e6ff1ca053fd8c729054490e78ef42dc64e829
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161989"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="6a73c-103">Använda ett skript för att lägga till användare i ett ärende för bas-eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6a73c-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="6a73c-104">Säkerhets& Compliance Center PowerShell innehåller cmdlets som gör att du kan automatisera tidskrävande uppgifter när du skapar och hanterar eDiscovery-ärenden.</span><span class="sxs-lookup"><span data-stu-id="6a73c-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="6a73c-105">För närvarande tar det tid och förberedelse att använda grundärende för eDiscovery-ärendet i säkerhets- och efterlevnadscentret för säkerhet i & för att skapa ett stort antal platser för innehåll som är beroende av senare användning.</span><span class="sxs-lookup"><span data-stu-id="6a73c-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="6a73c-106">Innan du skapar ett område måste du till exempel samla in WEBBADRESSen för OneDrive för företag webbplats som du vill skapa ett område för.</span><span class="sxs-lookup"><span data-stu-id="6a73c-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="6a73c-107">För varje användare som du vill använda som väntande måste du sedan lägga till deras postlåda och deras OneDrive för företag-webbplats i holden.</span><span class="sxs-lookup"><span data-stu-id="6a73c-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="6a73c-108">Du kan använda skriptet i den här artikeln för att automatisera processen.</span><span class="sxs-lookup"><span data-stu-id="6a73c-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="6a73c-109">Skriptet uppmanar dig att ange namnet på organisationens domän Min webbplats (till exempel i URL-adressen, namnet på ett befintligt `contoso` eDiscovery-ärende, namnet på det nya håll som är kopplat till ärendet, en lista med e-postadresser till de användare som du vill sätta på plats och en sökfråga som ska användas om du vill skapa ett frågebaserat https://contoso-my.sharepoint.com) ärende.</span><span class="sxs-lookup"><span data-stu-id="6a73c-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="6a73c-110">Skriptet hämtar sedan URL-adressen för OneDrive för företag-webbplatsen för varje användare i listan, skapar det nya antalet och lägger sedan till postlådan och OneDrive för företag-webbplatsen för varje användare i listan i listan.</span><span class="sxs-lookup"><span data-stu-id="6a73c-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="6a73c-111">Skriptet genererar även loggfiler som innehåller information om det nya arkivet.</span><span class="sxs-lookup"><span data-stu-id="6a73c-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="6a73c-112">Här är stegen för att göra detta:</span><span class="sxs-lookup"><span data-stu-id="6a73c-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="6a73c-113">Steg 1: Installera SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="6a73c-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="6a73c-114">Steg 2: Skapa en lista över användare</span><span class="sxs-lookup"><span data-stu-id="6a73c-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="6a73c-115">Steg 3: Kör skriptet för att skapa ett väntande och lägga till användare</span><span class="sxs-lookup"><span data-stu-id="6a73c-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="6a73c-116">Innan du lägger till användare i en holden</span><span class="sxs-lookup"><span data-stu-id="6a73c-116">Before you add users to a hold</span></span>

- <span data-ttu-id="6a73c-117">Du måste vara medlem i rollgruppen för eDiscovery Manager i säkerhets- och efterlevnadscentret för & och en SharePoint Online-administratör för att kunna köra skriptet i steg 3.</span><span class="sxs-lookup"><span data-stu-id="6a73c-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="6a73c-118">Mer information finns i [Tilldela eDiscovery-behörigheter i säkerhets- Office 365 & efterlevnadscenter.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="6a73c-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="6a73c-119">Maximalt 1 000 postlådor och 100 webbplatser kan läggas till i ett hold som är kopplat till ett eDiscovery-ärende i Säkerhets- och & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="6a73c-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="6a73c-120">Anta att alla användare som du vill skapa en webbplats för OneDrive för företag har möjlighet att lägga till högst 100 användare i ett område med hjälp av skriptet i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6a73c-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="6a73c-121">Se till att spara listan med användare som du skapar i steg 2 och skriptet i steg 3 i samma mapp.</span><span class="sxs-lookup"><span data-stu-id="6a73c-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="6a73c-122">Det gör det enklare att köra skriptet.</span><span class="sxs-lookup"><span data-stu-id="6a73c-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="6a73c-123">Skriptet lägger till listan med användare i ett nytt ärende som är kopplat till ett befintligt ärende.</span><span class="sxs-lookup"><span data-stu-id="6a73c-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="6a73c-124">Se till att det ärende som du vill koppla behåll till skapas innan du kör skriptet.</span><span class="sxs-lookup"><span data-stu-id="6a73c-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="6a73c-125">Skriptet i den här artikeln stöder modern autentisering när du ansluter till Security & Compliance Center PowerShell och SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6a73c-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span> <span data-ttu-id="6a73c-126">Du kan använda skriptet som det är om du är en Microsoft 365 eller en Microsoft 365 GCC organisation.</span><span class="sxs-lookup"><span data-stu-id="6a73c-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="6a73c-127">Om du är en Office 365 Germany-organisation, Microsoft 365 GCC High-organisation eller en Microsoft 365 DoD-organisation måste du redigera skriptet för att kunna köra det.</span><span class="sxs-lookup"><span data-stu-id="6a73c-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="6a73c-128">Specifikt måste du redigera linjen och använda parametrarna ConnectionUri och `Connect-IPPSSession` *AzureADAuthorizationEndpointUri* (och lämpliga värden för din organisationstyp) för att ansluta till *Säkerhets-* och efterlevnadscenter för & PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a73c-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="6a73c-129">Mer information finns i exemplen i [Anslut Security & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)</span><span class="sxs-lookup"><span data-stu-id="6a73c-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="6a73c-130">Skriptet kopplar automatiskt bort från Security & Compliance Center PowerShell och SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6a73c-130">The script automatically disconnects from Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span>

- <span data-ttu-id="6a73c-131">Skriptet innehåller minimal felhantering.</span><span class="sxs-lookup"><span data-stu-id="6a73c-131">The script includes minimal error handling.</span></span> <span data-ttu-id="6a73c-132">Det primära syftet är att snabbt och enkelt placera postlådan och OneDrive för företag-webbplatsen för varje användare i holden.</span><span class="sxs-lookup"><span data-stu-id="6a73c-132">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="6a73c-133">Exempelskripten som tillhandahålls i det här avsnittet stöds inte under något standardsupportprogram eller någon standardsupporttjänst från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a73c-133">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="6a73c-134">Exempelskripten ges i befintligt skick utan garantier av något slag.</span><span class="sxs-lookup"><span data-stu-id="6a73c-134">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="6a73c-135">Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, utan begränsning, underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål.</span><span class="sxs-lookup"><span data-stu-id="6a73c-135">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="6a73c-136">Hela risken i samband med användningen av eller prestandan hos exempelskripten och dokumentationen vilar på dig.</span><span class="sxs-lookup"><span data-stu-id="6a73c-136">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="6a73c-137">Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skripten hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador avseende utebliven vinst, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller svårighet eller omöjlighet att använda exempelskripten eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="6a73c-137">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="6a73c-138">Steg 1: Installera SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="6a73c-138">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="6a73c-139">Det första steget är att installera SharePoint Online Management Shell om det inte redan är installerat på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="6a73c-139">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="6a73c-140">Du behöver inte använda gränssnittet i den här proceduren, men du måste installera det eftersom det innehåller förutsättningar som krävs av skriptet som du kör i steg 3.</span><span class="sxs-lookup"><span data-stu-id="6a73c-140">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="6a73c-141">Dessa krav gör att skriptet kan kommunicera med SharePoint Online för att få URL:er för OneDrive för företag webbplatser.</span><span class="sxs-lookup"><span data-stu-id="6a73c-141">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="6a73c-142">Gå till [Konfigurera SharePoint Online Management Shell Windows PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) och utför steg 1 och steg 2 för att installera SharePoint Online Management Shell på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="6a73c-142">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span>

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="6a73c-143">Steg 2: Skapa en lista över användare</span><span class="sxs-lookup"><span data-stu-id="6a73c-143">Step 2: Generate a list of users</span></span>

<span data-ttu-id="6a73c-144">Skriptet i steg 3 skapar ett ärende som är kopplat till ett eDiscovery-ärende och lägger till postlådorna och OneDrive för företag av en lista över användare i servern.</span><span class="sxs-lookup"><span data-stu-id="6a73c-144">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="6a73c-145">Du kan skriva e-postadresserna i en textfil eller köra ett kommando i Windows PowerShell för att visa en lista med e-postadresser och spara dem i en fil (som finns i samma mapp som skriptet ska sparas i steg 3).</span><span class="sxs-lookup"><span data-stu-id="6a73c-145">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="6a73c-146">Här är ett PowerShell-kommando (som du kör med fjärr-PowerShell som är anslutet till din Exchange Online-organisation) för att få en lista med e-postadresser för alla användare i organisationen och spara den i en textfil som heter HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="6a73c-146">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="6a73c-147">När du har kört kommandot öppnar du textfilen och tar bort rubriken som innehåller  `PrimarySmtpAddress` egenskapsnamnet.</span><span class="sxs-lookup"><span data-stu-id="6a73c-147">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="6a73c-148">Ta sedan bort alla e-postadresser utom de för de användare som du vill lägga till i undantagssteget som du skapar i steg 3.</span><span class="sxs-lookup"><span data-stu-id="6a73c-148">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="6a73c-149">Kontrollera att det inte finns tomma rader före eller efter listan med e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="6a73c-149">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="6a73c-150">Steg 3: Kör skriptet för att skapa ett väntande och lägga till användare</span><span class="sxs-lookup"><span data-stu-id="6a73c-150">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="6a73c-151">När du kör skriptet i det här steget uppmanas du att ange följande information.</span><span class="sxs-lookup"><span data-stu-id="6a73c-151">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="6a73c-152">Se till att ha den här informationen redo innan du kör skriptet.</span><span class="sxs-lookup"><span data-stu-id="6a73c-152">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="6a73c-153">**Dina användarautentiseringsuppgifter:** Skriptet använder dina autentiseringsuppgifter för att ansluta till Säkerhets- & med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a73c-153">**Your user credentials:** The script will use your credentials to connect to Security & Compliance Center with PowerShell.</span></span> <span data-ttu-id="6a73c-154">De här autentiseringsuppgifterna används också för att komma SharePoint Online för att hämta e OneDrive för företag adresser för listan med användare.</span><span class="sxs-lookup"><span data-stu-id="6a73c-154">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="6a73c-155">**Namnet på din SharePoint domän:** Skriptet uppmanar dig att ange det här namnet så att det kan ansluta SharePoint administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="6a73c-155">**Name of your SharePoint domain:** The script prompts you to enter this name so it can connect to the SharePoint admin center.</span></span> <span data-ttu-id="6a73c-156">Den använder också domännamnet för OneDrive i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6a73c-156">It also uses the domain name for the OneDrive URLs in your organization.</span></span> <span data-ttu-id="6a73c-157">Om URL:en för administrationscentret till exempel är och URL:en för OneDrive är anger du när skriptet uppmanar dig att `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` ange `contoso` domännamnet.</span><span class="sxs-lookup"><span data-stu-id="6a73c-157">For example, if the URL for your admin center is `https://contoso-admin.sharepoint.com` and the URL for OneDrive is `https://contoso-my.sharepoint.com`, then you would enter `contoso` when the script prompts you for your domain name.</span></span>

- <span data-ttu-id="6a73c-158">**Namnet på ärendet:** Namnet på ett befintligt ärende.</span><span class="sxs-lookup"><span data-stu-id="6a73c-158">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="6a73c-159">Skriptet skapar ett nytt ärende som är associerat med det här fallet.</span><span class="sxs-lookup"><span data-stu-id="6a73c-159">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="6a73c-160">**Namn på det hållna:** Namnet på det hållna skriptet skapar och associerar med det angivna ärendet.</span><span class="sxs-lookup"><span data-stu-id="6a73c-160">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="6a73c-161">**Sökfråga för ett frågebaserat rymmer:** Du kan skapa ett frågebaserat hold-baserat så att endast det innehåll som uppfyller de angivna sökvillkoren får plats.</span><span class="sxs-lookup"><span data-stu-id="6a73c-161">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="6a73c-162">Om du vill placera allt innehåll i meddelandefältet **trycker** du på Retur när du uppmanas att ange en sökfråga.</span><span class="sxs-lookup"><span data-stu-id="6a73c-162">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="6a73c-163">**Aktivera eller inte aktivera det:** Du kan aktivera skriptets aktivering när det har skapats, eller så kan du låta skriptet skapa ett väntande skript utan att aktivera det.</span><span class="sxs-lookup"><span data-stu-id="6a73c-163">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="6a73c-164">Om du inte har skriptet som aktiverar körningen kan du aktivera det senare i Security & Compliance Center eller genom att köra följande PowerShell-kommandon:</span><span class="sxs-lookup"><span data-stu-id="6a73c-164">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="6a73c-165">**Namnet på textfilen med** listan över användare – namnet på textfilen från steg 2 som innehåller listan över användare som ska läggas till i fältet.</span><span class="sxs-lookup"><span data-stu-id="6a73c-165">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="6a73c-166">Om filen finns i samma mapp som skriptet skriver du namnet på filen (till exempel skriv HoldUsers.txt).</span><span class="sxs-lookup"><span data-stu-id="6a73c-166">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="6a73c-167">Om textfilen finns i en annan mapp skriver du den fullständiga sökvägen till filen.</span><span class="sxs-lookup"><span data-stu-id="6a73c-167">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="6a73c-168">När du har samlat in den information som skriptet kommer att be dig om är det sista steget att köra skriptet för att skapa det nya tillägget och lägga till användare i det.</span><span class="sxs-lookup"><span data-stu-id="6a73c-168">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="6a73c-169">Spara följande text i Windows PowerShell skriptfil med ett filnamnssuffix på `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="6a73c-169">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="6a73c-170">Till exempel `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="6a73c-170">For example, `AddUsersToHold.ps1`.</span></span>

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

# Load the SharePoint assemblies from the SharePoint Online Management Shell
# To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
{
    $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
    $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
    $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
    if (!$SharePointClient)
    {
        Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
        return;
    }
}

# Get other required information
do{
$casename = Read-Host "Enter the name of the case"
$caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
if($caseexists -ne 'True')
{""
write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
""}
}While($caseexists -ne 'True')
""
do{
$holdName = Read-Host "Enter the name of the new hold"
$holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
if($holdexists -eq 'True')
{""
write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
""}
}While($holdexists -eq 'True')
""
$holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
""
$holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
do{
""
$inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
""
$fileexists = test-path -path $inputfile
if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
}while($fileexists -ne 'True')
#Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
    #in the list are unique.
  [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
  [int]$dupl = $emailAddresses.count
  [array]$emailAddresses = $emailAddresses | select-object -unique
  $dupl -= $emailAddresses.count
#Validate email addresses so the hold creation does not run in to an error.
if($emailaddresses.count -gt 0){
write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
""
Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
""
$finallist =@()
foreach($emailAddress in $emailAddresses)
{
if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
{$finallist += $emailaddress}
else {"Unable to find the user $emailaddress"
[array]$excludedlist += $emailaddress}
}
""
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
}
""
}
else {"No valid locations were identified. Therefore, the hold wasn't created."}
#write log files (if needed)
$newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
$newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
{
Write-Host "Generating output files..." -foregroundColor Yellow
if($ODAdded.count -gt 0){
"OneDrive Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
if($ODExluded.count -gt 0){ 
"Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
"================================" | add-content .\LocationsNotOnHold.txt
$ODExluded | add-content .\LocationsNotOnHold.txt}
if($finallist.count -gt 0){
" " | add-content .\LocationsOnHold.txt
"Exchange Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
if($excludedlist.count -gt 0){
" "| add-content .\LocationsNotOnHold.txt
"Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
"===============================" | add-content .\LocationsNotOnHold.txt
$excludedlist | add-content .\LocationsNotOnHold.txt}
$FormatEnumerationLimit=-1
if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
}
}
else {"The hold wasn't created because no valid entries were found in the text file."}
""
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. <span data-ttu-id="6a73c-171">Öppna den lokala datorn Windows PowerShell gå till mappen där du sparade skriptet.</span><span class="sxs-lookup"><span data-stu-id="6a73c-171">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="6a73c-172">Kör skriptet. till exempel:</span><span class="sxs-lookup"><span data-stu-id="6a73c-172">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="6a73c-173">Ange den information som skriptet uppmanar dig att ange.</span><span class="sxs-lookup"><span data-stu-id="6a73c-173">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="6a73c-174">Skriptet ansluter till Säkerhets- & Efterlevnadscenter PowerShell, och skapar sedan det nya antalet i eDiscovery-ärendet och lägger till postlådorna och OneDrive för företag för användarna i listan.</span><span class="sxs-lookup"><span data-stu-id="6a73c-174">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="6a73c-175">Du kan gå till ärendet på sidan **eDiscovery** i säkerhets- & kompatibilitetscentret för att visa det nya antalet.</span><span class="sxs-lookup"><span data-stu-id="6a73c-175">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="6a73c-176">När skriptet har körts klart skapas följande loggfiler och sparas i den mapp där skriptet finns.</span><span class="sxs-lookup"><span data-stu-id="6a73c-176">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="6a73c-177">**LocationsOnHold.txt:** Innehåller en lista över postlådor och OneDrive för företag webbplatser som skriptet har satts i servern.</span><span class="sxs-lookup"><span data-stu-id="6a73c-177">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="6a73c-178">**LocationsNotOnHold.txt:** Innehåller en lista över postlådor OneDrive för företag webbplatser som skriptet inte har plats för.</span><span class="sxs-lookup"><span data-stu-id="6a73c-178">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="6a73c-179">Om en användare har en postlåda, men inte en OneDrive för företag-webbplats, skulle användaren ingå i listan med OneDrive för företag-webbplatser som inte har satts på en plats.</span><span class="sxs-lookup"><span data-stu-id="6a73c-179">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="6a73c-180">**GetCaseHoldPolicy.txt:** Innehåller resultatet från cmdleten **Get-CaseHoldPolicy** för det nya holden som skriptet körde när det nya fältet hade skapats.</span><span class="sxs-lookup"><span data-stu-id="6a73c-180">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="6a73c-181">Informationen som returneras av den här cmdleten innehåller en lista över användare vars postlådor och OneDrive för företag platser har aktiverats och om det är aktiverat eller inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="6a73c-181">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="6a73c-182">**GetCaseHoldRule.txt:** Innehåller resultatet från cmdleten **Get-CaseHoldRule** för det nya holden, som skriptet kördes efter att det nya fältet hade skapats.</span><span class="sxs-lookup"><span data-stu-id="6a73c-182">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="6a73c-183">Den information som returneras av den här cmdleten innehåller sökfrågan om du använde skriptet för att skapa ett frågebaserat håll.</span><span class="sxs-lookup"><span data-stu-id="6a73c-183">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>