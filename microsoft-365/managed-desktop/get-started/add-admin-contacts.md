---
title: Lägga till och verifiera administratörskontakter i administratörsportalen
description: Berätta för oss vem du ska kontakta för varje fokus område.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8b287200b1c94ff350f7ba00cf0c4e6bc1b4a71f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289267"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="386e1-104">Lägga till och verifiera administratörskontakter i administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="386e1-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="386e1-105">Det finns flera sätt som Microsoft Managed Desktop Service kommunicerar med kunder.</span><span class="sxs-lookup"><span data-stu-id="386e1-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="386e1-106">För att effektivisera kommunikationen och kontrol lera att vi håller på att kontrol lera med rätt personer måste du ange en uppsättning administratörs kontakter.</span><span class="sxs-lookup"><span data-stu-id="386e1-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="386e1-107">Microsoft Managed Desktop den här personen kontaktar de här personerna för att få hjälp med fel söknings problem för din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="386e1-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="386e1-108">Du kanske redan har lagt till dessa kontakter i administrations portalen.</span><span class="sxs-lookup"><span data-stu-id="386e1-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="386e1-109">Om så är fallet, ta ett tag nu för att kontrol lera att kontakt listan stämmer, eftersom Microsoft Managed Desktop **måste** kunna nå dem om en allvarlig olycka inträffar.</span><span class="sxs-lookup"><span data-stu-id="386e1-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="386e1-110">Åtkomst för Azure Active Directory-portalen för Microsoft Managed Desktop-administratörer</span><span class="sxs-lookup"><span data-stu-id="386e1-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="386e1-111">Administrations portalen för Microsoft Managed Desktop kräver att personer som använder portalen har en av dessa Azure Active Directory (AD)-roller:</span><span class="sxs-lookup"><span data-stu-id="386e1-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="386e1-112">Global administratör</span><span class="sxs-lookup"><span data-stu-id="386e1-112">Global Administrator</span></span>
- <span data-ttu-id="386e1-113">Intune tjänst administratör</span><span class="sxs-lookup"><span data-stu-id="386e1-113">Intune Service Administrator</span></span>
- <span data-ttu-id="386e1-114">Global läsare</span><span class="sxs-lookup"><span data-stu-id="386e1-114">Global Reader</span></span>
- <span data-ttu-id="386e1-115">Support administratör för tjänsten</span><span class="sxs-lookup"><span data-stu-id="386e1-115">Service Support Administrator</span></span>

<span data-ttu-id="386e1-116">Den globala administratören måste vara den som ska registrera din organisation på Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="386e1-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="386e1-117">Alla fem roller har samma åtkomst i administrations portalen för att initiera och Visa aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="386e1-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="386e1-118">Mer information om hur du tilldelar dessa roller i Azure AD finns i [behörigheter för administratörs roller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="386e1-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="386e1-119">Administrations kontakt områden i fokus</span><span class="sxs-lookup"><span data-stu-id="386e1-119">Admin contact areas of focus</span></span>

<span data-ttu-id="386e1-120">Administratörs kontakterna bör vara den bästa personen eller gruppen som kan besvara frågor och fatta beslut för olika fokus områden.</span><span class="sxs-lookup"><span data-stu-id="386e1-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="386e1-121">**Microsoft Managed Station ära datorer kontaktar dessa administratörs kontakter för frågor som berör support ärenden som skickas av kunden.**</span><span class="sxs-lookup"><span data-stu-id="386e1-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="386e1-122">Dessa administratörs kontakter får aviseringar om uppdateringar och nya meddelanden om supportinformation.</span><span class="sxs-lookup"><span data-stu-id="386e1-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="386e1-123">Dessa områden inkluderar:</span><span class="sxs-lookup"><span data-stu-id="386e1-123">These areas include:</span></span>

<span data-ttu-id="386e1-124">Fokus område</span><span class="sxs-lookup"><span data-stu-id="386e1-124">Area of focus</span></span> | <span data-ttu-id="386e1-125">Om du har frågor om</span><span class="sxs-lookup"><span data-stu-id="386e1-125">For questions about</span></span>
--- | ---
<span data-ttu-id="386e1-126">Program packning</span><span class="sxs-lookup"><span data-stu-id="386e1-126">App packaging</span></span> | <span data-ttu-id="386e1-127">Felsöka programpaket</span><span class="sxs-lookup"><span data-stu-id="386e1-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="386e1-128">Anordningar</span><span class="sxs-lookup"><span data-stu-id="386e1-128">Devices</span></span> | <span data-ttu-id="386e1-129">Enhets hälsa, fel sökning med Microsoft hanterade Station ära enheter</span><span class="sxs-lookup"><span data-stu-id="386e1-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="386e1-130">Säkerhet</span><span class="sxs-lookup"><span data-stu-id="386e1-130">Security</span></span> | <span data-ttu-id="386e1-131">Felsöka säkerhets problem med Microsoft hanterade Station ära enheter</span><span class="sxs-lookup"><span data-stu-id="386e1-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="386e1-132">IT-support</span><span class="sxs-lookup"><span data-stu-id="386e1-132">IT help desk</span></span> | <span data-ttu-id="386e1-133">i de fall vår support personal händer över användar biljetter utanför Microsoft Managed Desktop support-områden</span><span class="sxs-lookup"><span data-stu-id="386e1-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="386e1-134">Annat</span><span class="sxs-lookup"><span data-stu-id="386e1-134">Other</span></span> | <span data-ttu-id="386e1-135">För problem som inte täcks av andra områden</span><span class="sxs-lookup"><span data-stu-id="386e1-135">For issues not covered by other areas</span></span>

<span data-ttu-id="386e1-136">**Den du väljer för dessa kontakter måste ha kunskap och behörighet för att fatta beslut för din Microsoft-hanterade Skriv bords miljö.**</span><span class="sxs-lookup"><span data-stu-id="386e1-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="386e1-137">När du har en Microsoft Managed Desktop-miljö uppmanas du att lägga till kontakter för ditt lokala helpdesk och din säkerhet.</span><span class="sxs-lookup"><span data-stu-id="386e1-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="386e1-138">Administratörs kontakter krävs när du [skickar in en supportbegäran](../service-description/support.md).</span><span class="sxs-lookup"><span data-stu-id="386e1-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="386e1-139">Du måste ha en administratörs kontakt för att fokusera på support förfrågan.</span><span class="sxs-lookup"><span data-stu-id="386e1-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="386e1-140">**Lägga till administratörs kontakter**</span><span class="sxs-lookup"><span data-stu-id="386e1-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="386e1-141">Logga in på [administrations portalen för Microsoft Managed Desktop](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="386e1-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="386e1-142">Välj **admin-kontakter**under **support**.</span><span class="sxs-lookup"><span data-stu-id="386e1-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Menyn support, administratörs kontakter nära det markerade överst](../../media/admincontacts.png)

3. <span data-ttu-id="386e1-144">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="386e1-144">Select **Add**.</span></span>

    ![Administrations portalen, knappen Lägg till, till vänster om exportera och uppdatera](../../media/adminadd.png)

4.  <span data-ttu-id="386e1-146">Markera ett **område med fokus** och ange informationen för kontakten.</span><span class="sxs-lookup"><span data-stu-id="386e1-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![listan med fokus områden, till exempel andra, appar och säkerhet](../../media/areaoffocus.png)

5. <span data-ttu-id="386e1-148">Upprepa för varje fokus område.</span><span class="sxs-lookup"><span data-stu-id="386e1-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="386e1-149">Steg för att komma igång med Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="386e1-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="386e1-150">Lägga till och verifiera administratörs kontakter i administrations portalen (det här avsnittet)</span><span class="sxs-lookup"><span data-stu-id="386e1-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="386e1-151">Justera villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="386e1-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="386e1-152">Koppla licenser</span><span class="sxs-lookup"><span data-stu-id="386e1-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="386e1-153">Installera Intune-företagsportal på enheter</span><span class="sxs-lookup"><span data-stu-id="386e1-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="386e1-154">Aktivera Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="386e1-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="386e1-155">Konfigurera Microsoft Hanterat skrivbord enheter</span><span class="sxs-lookup"><span data-stu-id="386e1-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="386e1-156">Få dina användare redo att använda enheter</span><span class="sxs-lookup"><span data-stu-id="386e1-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="386e1-157">Distribuera appar till enheter</span><span class="sxs-lookup"><span data-stu-id="386e1-157">Deploy apps to devices</span></span>](deploy-apps.md)
