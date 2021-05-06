---
title: Microsoft Compliance Manager och GDPR
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager är ett kostnadsfritt arbetsflödesbaserat riskutvärderingsverktyg i Microsoft Service Trust Portal. Med Efterlevnadshanteraren kan du spåra, tilldela och verifiera aktiviteter för regelefterlevnad som är relaterade till Microsofts molntjänster.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "52161494"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="96905-104">Microsoft Compliance Manager och GDPR</span><span class="sxs-lookup"><span data-stu-id="96905-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="96905-105">Den allmänna dataskyddsförordningen (GDPR) som tillämpas av EU kan påverka din efterlevnadsstrategi och specifika åtgärder för att hantera användar- och kundinformation som används i Efterlevnadshanteraren.</span><span class="sxs-lookup"><span data-stu-id="96905-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="96905-106">Inställningar för användarsekretess</span><span class="sxs-lookup"><span data-stu-id="96905-106">User Privacy settings</span></span>

<span data-ttu-id="96905-107">Vissa bestämmelser kräver att en organisation måste kunna ta bort användarhistorikdata.</span><span class="sxs-lookup"><span data-stu-id="96905-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="96905-108">Efterlevnadshanteraren **ger funktioner för Inställningar** sekretess som administratörer kan:</span><span class="sxs-lookup"><span data-stu-id="96905-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="96905-109">Söka efter en användare</span><span class="sxs-lookup"><span data-stu-id="96905-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="96905-110">Exportera en rapport över kontodatahistorik</span><span class="sxs-lookup"><span data-stu-id="96905-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="96905-111">Ta bort användardatahistorik</span><span class="sxs-lookup"><span data-stu-id="96905-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="96905-112">Söka efter en användare</span><span class="sxs-lookup"><span data-stu-id="96905-112">Search for a user</span></span>

<span data-ttu-id="96905-113">Så här söker du efter ett användarkonto:</span><span class="sxs-lookup"><span data-stu-id="96905-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="96905-114">Ange ett användar-e-postalias (informationen till vänster om @-symbolen) och välj domännamnet i listan med domänsuffix till höger.</span><span class="sxs-lookup"><span data-stu-id="96905-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="96905-115">För organisationer med flera registrerade domäner bör du kontrollera att domännamnssuffixet stämmer.</span><span class="sxs-lookup"><span data-stu-id="96905-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="96905-116">När du har angett användarnamnet korrekt väljer du **Sök**.</span><span class="sxs-lookup"><span data-stu-id="96905-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="96905-117">För användarkonton som inte returneras visas **Användaren hittades inte** på sidan.</span><span class="sxs-lookup"><span data-stu-id="96905-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="96905-118">Kontrollera användarens e-postadressinformation och gör eventuella korrigeringar.</span><span class="sxs-lookup"><span data-stu-id="96905-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="96905-119">Om du vill försöka igen väljer du **Sök**.</span><span class="sxs-lookup"><span data-stu-id="96905-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="96905-120">För användarkonton som returneras ändras texten på knappen från **Sök till** **Rensa**.</span><span class="sxs-lookup"><span data-stu-id="96905-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="96905-121">Detta anger att det returnerade användarkontot är operativsystemskontexten för de ytterligare funktionerna och att dessa funktioner gäller för det här användarkontot.</span><span class="sxs-lookup"><span data-stu-id="96905-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="96905-122">Om du vill rensa sökresultat och söka efter en annan användare väljer du **Rensa**.</span><span class="sxs-lookup"><span data-stu-id="96905-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="96905-123">Exportera en rapport över kontodatahistorik</span><span class="sxs-lookup"><span data-stu-id="96905-123">Export a report of account data history</span></span>

<span data-ttu-id="96905-124">För varje användarkonto som identifieras kan du generera en rapport över beroenden som är kopplade till kontot.</span><span class="sxs-lookup"><span data-stu-id="96905-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="96905-125">Med den här informationen kan du omtilldela öppna uppgifter eller säkerställa åtkomst till tidigare uppladdade bevis.</span><span class="sxs-lookup"><span data-stu-id="96905-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="96905-126">Så här skapar och exporterar du en rapport:</span><span class="sxs-lookup"><span data-stu-id="96905-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="96905-127">Välj **Exportera** om du vill skapa och ladda ned en rapport med Kontrollen Åtgärdshanteraren (Compliance Manager) som för närvarande tilldelats det returnerade användarkontot samt listan med dokument som laddats upp av användaren.</span><span class="sxs-lookup"><span data-stu-id="96905-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="96905-128">Om det inte finns några tilldelade åtgärder eller överladdade dokument visas felmeddelandet "Inga data för den här användaren".</span><span class="sxs-lookup"><span data-stu-id="96905-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="96905-129">Rapporten laddas ned i bakgrunden i det aktiva webbläsarfönstret – om du inte ser ett popup-fönster för nedladdning som du vill kontrollera webbläsarens nedladdningshistorik.</span><span class="sxs-lookup"><span data-stu-id="96905-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="96905-130">Öppna dokumentet för att granska rapportdata.</span><span class="sxs-lookup"><span data-stu-id="96905-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96905-131">Rapportdata är inte en historisk lista som behåller och visar tillståndsändringar i tilldelningshistorik för åtgärdsobjekt.</span><span class="sxs-lookup"><span data-stu-id="96905-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="96905-132">Den genererade rapporten är en ögonblicksbild av kontrollen Åtgärdsobjekt som tilldelats vid den tidpunkt då rapporten körs (datum- och tidsstämpeln skrivs in i rapporten).</span><span class="sxs-lookup"><span data-stu-id="96905-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="96905-133">Alla efterföljande omtilldelar av åtgärdsuppgifter leder till andra ögonblicksbilder av rapportdata om rapporten genereras igen för samma användare.</span><span class="sxs-lookup"><span data-stu-id="96905-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="96905-134">Ta bort användardatahistorik</span><span class="sxs-lookup"><span data-stu-id="96905-134">Delete user data history</span></span>

<span data-ttu-id="96905-135">Anger alla kontrollobjekt som tilldelats den returnerade användaren till "inte tilldelat".</span><span class="sxs-lookup"><span data-stu-id="96905-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="96905-136">Anger värdet **uppladdat efter** för dokument som laddats upp av den returnerade användaren till "användare borttagen".</span><span class="sxs-lookup"><span data-stu-id="96905-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="96905-137">Så här tar du bort användarkontots åtgärdsobjekt och dokumentets uppladdningshistorik:</span><span class="sxs-lookup"><span data-stu-id="96905-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="96905-138">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="96905-138">Select **Delete**.</span></span>

    <span data-ttu-id="96905-139">En bekräftelsedialogruta visas: " Detta tar bort alla uppgifter i *åtgärdsobjekt och dokumentuppladdningshistoriken för den valda användaren. Den här åtgärden är permanent. Vill du fortsätta?*"</span><span class="sxs-lookup"><span data-stu-id="96905-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="96905-140">Fortsätt genom att **välja OK**, annars välj **Avbryt.**</span><span class="sxs-lookup"><span data-stu-id="96905-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
