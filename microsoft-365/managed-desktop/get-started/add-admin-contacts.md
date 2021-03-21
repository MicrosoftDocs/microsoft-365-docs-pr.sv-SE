---
title: Lägga till och verifiera administratörskontakter i administratörsportalen
description: Berätta vem vi ska kontakta för varje fokusområde.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925898"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="ee474-104">Lägga till och verifiera administratörskontakter i administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="ee474-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="ee474-105">Tjänsten Microsoft Managed Desktop kommunicerar med kunder på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="ee474-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="ee474-106">För att effektivisera kommunikationen och se till att vi kontrollerar med rätt personer, måste du tillhandahålla en uppsättning administratörskontakter.</span><span class="sxs-lookup"><span data-stu-id="ee474-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="ee474-107">Microsoft Managed Desktop IT Operations kontaktar dessa personer för att få hjälp med att felsöka problem för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="ee474-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee474-108">Du kanske redan har lagt till de här kontakterna i administrationsportalen.</span><span class="sxs-lookup"><span data-stu-id="ee474-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="ee474-109">I så fall bör du kontrollera att kontaktlistan är korrekt, eftersom Microsoft Managed **Desktop** måste kunna nå dem om ett allvarligt problem inträffar.</span><span class="sxs-lookup"><span data-stu-id="ee474-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="ee474-110">Azure Active Directory-åtkomst för Microsoft Managed Desktop Admin-portalen</span><span class="sxs-lookup"><span data-stu-id="ee474-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="ee474-111">Microsoft Managed Desktop Admin-portalen kräver att personer som har åtkomst till portalen har någon av dessa Azure Active Directory-roller (AD):</span><span class="sxs-lookup"><span data-stu-id="ee474-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="ee474-112">Global administratör</span><span class="sxs-lookup"><span data-stu-id="ee474-112">Global Administrator</span></span>
- <span data-ttu-id="ee474-113">Intune-tjänstadministratör</span><span class="sxs-lookup"><span data-stu-id="ee474-113">Intune Service Administrator</span></span>
- <span data-ttu-id="ee474-114">Global läsare</span><span class="sxs-lookup"><span data-stu-id="ee474-114">Global Reader</span></span>
- <span data-ttu-id="ee474-115">Tjänstsupportadministratör</span><span class="sxs-lookup"><span data-stu-id="ee474-115">Service Support Administrator</span></span>

<span data-ttu-id="ee474-116">Den globala administratören måste vara den som registrerar din organisation i Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ee474-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="ee474-117">Alla fem rollerna har samma åtkomst i administrationsportalen för att initiera och visa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="ee474-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="ee474-118">Mer information om hur du tilldelar de här rollerna i Azure AD finns i [Behörigheter för administratörsroll i Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="ee474-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="ee474-119">Administratörskontaktområden i fokus</span><span class="sxs-lookup"><span data-stu-id="ee474-119">Admin contact areas of focus</span></span>

<span data-ttu-id="ee474-120">Administratörskontakter bör vara den bästa personen eller gruppen som kan besvara frågor och fatta beslut inom olika fokusområden.</span><span class="sxs-lookup"><span data-stu-id="ee474-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="ee474-121">**Microsoft Managed Desktop Operations kommer att kontakta dessa administratörskontakter för frågor som rör supportbegäranden som lämnats in av kunden.**</span><span class="sxs-lookup"><span data-stu-id="ee474-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="ee474-122">De här administratörskontakterna får aviseringar om uppdateringar av supportbegäran och nya meddelanden.</span><span class="sxs-lookup"><span data-stu-id="ee474-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="ee474-123">Dessa områden omfattar:</span><span class="sxs-lookup"><span data-stu-id="ee474-123">These areas include:</span></span>

<span data-ttu-id="ee474-124">Fokusområde</span><span class="sxs-lookup"><span data-stu-id="ee474-124">Area of focus</span></span> | <span data-ttu-id="ee474-125">För frågor om</span><span class="sxs-lookup"><span data-stu-id="ee474-125">For questions about</span></span>
--- | ---
<span data-ttu-id="ee474-126">Appförpackning</span><span class="sxs-lookup"><span data-stu-id="ee474-126">App packaging</span></span> | <span data-ttu-id="ee474-127">Felsökning av appförpackningar</span><span class="sxs-lookup"><span data-stu-id="ee474-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="ee474-128">Enheter</span><span class="sxs-lookup"><span data-stu-id="ee474-128">Devices</span></span> | <span data-ttu-id="ee474-129">Enhetens hälsa, felsökning med Microsoft Managed Desktop-enheter</span><span class="sxs-lookup"><span data-stu-id="ee474-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="ee474-130">Säkerhet</span><span class="sxs-lookup"><span data-stu-id="ee474-130">Security</span></span> | <span data-ttu-id="ee474-131">Felsöka säkerhetsproblem med Microsoft Managed Desktop-enheter</span><span class="sxs-lookup"><span data-stu-id="ee474-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="ee474-132">It-supportavdelningen</span><span class="sxs-lookup"><span data-stu-id="ee474-132">IT help desk</span></span> | <span data-ttu-id="ee474-133">i fall där vår supportpersonal ger över användarärenden utanför supportområdena för Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ee474-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="ee474-134">Annat</span><span class="sxs-lookup"><span data-stu-id="ee474-134">Other</span></span> | <span data-ttu-id="ee474-135">För problem som inte omfattas av andra områden</span><span class="sxs-lookup"><span data-stu-id="ee474-135">For issues not covered by other areas</span></span>

<span data-ttu-id="ee474-136">**De som du väljer för dessa kontakter måste ha kunskaper och behörighet att fatta beslut om Microsoft Managed Desktop-miljön.**</span><span class="sxs-lookup"><span data-stu-id="ee474-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="ee474-137">När du onboard your Microsoft Managed Desktop environment, you're prompted to add contacts for your local Helpdesk and Security.</span><span class="sxs-lookup"><span data-stu-id="ee474-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="ee474-138">Administratörskontakter krävs när du [skickar en supportbegäran.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="ee474-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="ee474-139">Du måste ha en administratörskontakt för fokusområdet i supportbegäran.</span><span class="sxs-lookup"><span data-stu-id="ee474-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="ee474-140">**Lägga till administratörskontakter**</span><span class="sxs-lookup"><span data-stu-id="ee474-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="ee474-141">Logga in på [administrationsportalen för Microsoft Managed Desktop.](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="ee474-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="ee474-142">Under **Support** väljer du **Administratörskontakter**.</span><span class="sxs-lookup"><span data-stu-id="ee474-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Supportmenyn, administratörskontakter nästan högst upp markerat](../../media/admincontacts.png)

3. <span data-ttu-id="ee474-144">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ee474-144">Select **Add**.</span></span>

    ![Administrationsportal, knappen Lägg till, till vänster om Exportera och uppdatera](../../media/adminadd.png)

4.  <span data-ttu-id="ee474-146">Välj **ett område med fokus** och ange information om kontakten.</span><span class="sxs-lookup"><span data-stu-id="ee474-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![listan över fokusområden, till exempel Andra, Appar och Säkerhet](../../media/areaoffocus.png)

5. <span data-ttu-id="ee474-148">Upprepa detta för varje fokusområde.</span><span class="sxs-lookup"><span data-stu-id="ee474-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="ee474-149">Steg för att komma igång med Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ee474-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="ee474-150">Lägga till och verifiera administratörskontakter i administrationsportalen (det här avsnittet)</span><span class="sxs-lookup"><span data-stu-id="ee474-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="ee474-151">Justera villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="ee474-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="ee474-152">Koppla licenser</span><span class="sxs-lookup"><span data-stu-id="ee474-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="ee474-153">Installera Intune-företagsportal på enheter</span><span class="sxs-lookup"><span data-stu-id="ee474-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="ee474-154">Aktivera Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="ee474-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="ee474-155">Konfigurera Microsoft Hanterat skrivbord enheter</span><span class="sxs-lookup"><span data-stu-id="ee474-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="ee474-156">Få dina användare redo att använda enheter</span><span class="sxs-lookup"><span data-stu-id="ee474-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="ee474-157">Distribuera appar till enheter</span><span class="sxs-lookup"><span data-stu-id="ee474-157">Deploy apps to devices</span></span>](deploy-apps.md)