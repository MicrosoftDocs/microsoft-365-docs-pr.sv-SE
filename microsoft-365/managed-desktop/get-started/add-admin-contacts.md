---
title: Lägga till och verifiera administratörskontakter i administratörsportalen
description: Berätta vem vi ska kontakta för varje fokusområde.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8a5775d90f592aa5f64dd5f379fb37278032d87
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529809"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="61840-104">Lägga till och verifiera administratörskontakter i administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="61840-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="61840-105">Det finns flera sätt att kommunicera med kunder i Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="61840-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="61840-106">För att effektivisera kommunikationen och se till att vi kontrollerar med rätt personer måste du tillhandahålla en uppsättning administratörskontakter.</span><span class="sxs-lookup"><span data-stu-id="61840-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="61840-107">Microsoft Managed Desktop IT Operations kontaktar dessa personer för att få hjälp med felsökningsproblem för din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="61840-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61840-108">Du kanske redan har lagt till dessa kontakter i administratörsportalen.</span><span class="sxs-lookup"><span data-stu-id="61840-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="61840-109">Om så är fallet, ta en stund nu att dubbelkolla att kontaktlistan är korrekt, eftersom Microsoft Managed Desktop **måste** kunna nå dem om en allvarlig incident inträffar.</span><span class="sxs-lookup"><span data-stu-id="61840-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="61840-110">Azure Active Directory-åtkomst för Microsoft Managed Desktop Admin portal</span><span class="sxs-lookup"><span data-stu-id="61840-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="61840-111">Microsofts administratörsportal för hanterade skrivbord kräver att personer som ansluter till portalen har någon av dessa Azure Active Directory-roller (AD):</span><span class="sxs-lookup"><span data-stu-id="61840-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="61840-112">Global administratör</span><span class="sxs-lookup"><span data-stu-id="61840-112">Global Administrator</span></span>
- <span data-ttu-id="61840-113">Administratör för Intune-tjänsten</span><span class="sxs-lookup"><span data-stu-id="61840-113">Intune Service Administrator</span></span>
- <span data-ttu-id="61840-114">Global läsare</span><span class="sxs-lookup"><span data-stu-id="61840-114">Global Reader</span></span>
- <span data-ttu-id="61840-115">Administratör för servicesupport</span><span class="sxs-lookup"><span data-stu-id="61840-115">Service Support Administrator</span></span>

<span data-ttu-id="61840-116">Den globala administratören måste vara den som registrerar din organisation på Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="61840-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="61840-117">Alla fem rollerna har samma åtkomst i administratörsportalen för att initiera och visa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="61840-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="61840-118">Mer information om hur du tilldelar dessa roller i Azure AD finns [i Administratörsrollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="61840-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="61840-119">Admin kontaktområden i fokus</span><span class="sxs-lookup"><span data-stu-id="61840-119">Admin contact areas of focus</span></span>

<span data-ttu-id="61840-120">Administratörskontakter bör vara den bästa personen eller gruppen som kan svara på frågor och fatta beslut för olika fokusområden.</span><span class="sxs-lookup"><span data-stu-id="61840-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="61840-121">**Microsoft Managed Desktop Operations kontaktar dessa administratörskontakter för frågor som rör supportförfrågningar som lämnats in av kunden.**</span><span class="sxs-lookup"><span data-stu-id="61840-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="61840-122">Dessa administratörskontakter får meddelanden om uppdateringar av supportbegäran och nya meddelanden.</span><span class="sxs-lookup"><span data-stu-id="61840-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="61840-123">Dessa områden omfattar:</span><span class="sxs-lookup"><span data-stu-id="61840-123">These areas include:</span></span>

<span data-ttu-id="61840-124">Fokusområde</span><span class="sxs-lookup"><span data-stu-id="61840-124">Area of focus</span></span> | <span data-ttu-id="61840-125">För frågor om</span><span class="sxs-lookup"><span data-stu-id="61840-125">For questions about</span></span>
--- | ---
<span data-ttu-id="61840-126">Förpackning av appar</span><span class="sxs-lookup"><span data-stu-id="61840-126">App packaging</span></span> | <span data-ttu-id="61840-127">Felsöka appförpackningar</span><span class="sxs-lookup"><span data-stu-id="61840-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="61840-128">Enheter</span><span class="sxs-lookup"><span data-stu-id="61840-128">Devices</span></span> | <span data-ttu-id="61840-129">Enhetshälsa, felsökning med Microsoft Hanterade skrivbordsenheter</span><span class="sxs-lookup"><span data-stu-id="61840-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="61840-130">Säkerhet</span><span class="sxs-lookup"><span data-stu-id="61840-130">Security</span></span> | <span data-ttu-id="61840-131">Felsöka säkerhetsproblem med Microsoft Managed Desktop-enheter</span><span class="sxs-lookup"><span data-stu-id="61840-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="61840-132">IT-support</span><span class="sxs-lookup"><span data-stu-id="61840-132">IT help desk</span></span> | <span data-ttu-id="61840-133">i de fall där vår supportpersonal lämnar över slutanvändarbiljetter utanför Microsoft Managed Desktop-supportområden</span><span class="sxs-lookup"><span data-stu-id="61840-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="61840-134">Annat</span><span class="sxs-lookup"><span data-stu-id="61840-134">Other</span></span> | <span data-ttu-id="61840-135">För frågor som inte omfattas av andra områden</span><span class="sxs-lookup"><span data-stu-id="61840-135">For issues not covered by other areas</span></span>

<span data-ttu-id="61840-136">**Den du väljer för dessa kontakter måste ha kunskap och behörighet att fatta beslut för din Microsoft Managed Desktop-miljö.**</span><span class="sxs-lookup"><span data-stu-id="61840-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="61840-137">När du är ombord på microsoft managed desktop-miljön uppmanas du att lägga till kontakter för din lokala helpdesk och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="61840-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="61840-138">Administratörskontakter krävs när du [skickar en supportbegäran](../service-description/support.md).</span><span class="sxs-lookup"><span data-stu-id="61840-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="61840-139">Du måste ha en administratörskontakt för fokusområdet för supportbegäran.</span><span class="sxs-lookup"><span data-stu-id="61840-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="61840-140">**Så här lägger du till administratörskontakter**</span><span class="sxs-lookup"><span data-stu-id="61840-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="61840-141">Logga in på [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="61840-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="61840-142">Under **Support**väljer du **Admin-kontakter**.</span><span class="sxs-lookup"><span data-stu-id="61840-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Stödmeny, Admin-kontakter längst upp markerade](../../media/admincontacts.png)

3. <span data-ttu-id="61840-144">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="61840-144">Select **Add**.</span></span>

    ![Admin portal, Lägg till knappen, till vänster om Exportera och uppdatera](../../media/adminadd.png)

4.  <span data-ttu-id="61840-146">Välj ett **fokusområde** och ange informationen för kontakten.</span><span class="sxs-lookup"><span data-stu-id="61840-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![listan över fokusområden, till exempel Andra, Appar och Säkerhet](../../media/areaoffocus.png)

5. <span data-ttu-id="61840-148">Upprepa för varje fokusområde.</span><span class="sxs-lookup"><span data-stu-id="61840-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="61840-149">Steg för att komma igång med Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="61840-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="61840-150">Lägga till och verifiera administratörskontakter i administratörsportalen (det här avsnittet)</span><span class="sxs-lookup"><span data-stu-id="61840-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="61840-151">Justera villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="61840-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="61840-152">Koppla licenser</span><span class="sxs-lookup"><span data-stu-id="61840-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="61840-153">Installera Intune-företagsportal på enheter</span><span class="sxs-lookup"><span data-stu-id="61840-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="61840-154">Aktivera Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="61840-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="61840-155">Konfigurera Microsoft Hanterat skrivbord enheter</span><span class="sxs-lookup"><span data-stu-id="61840-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="61840-156">Få dina användare redo att använda enheter</span><span class="sxs-lookup"><span data-stu-id="61840-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="61840-157">Distribuera appar till enheter</span><span class="sxs-lookup"><span data-stu-id="61840-157">Deploy apps to devices</span></span>](deploy-apps.md)
