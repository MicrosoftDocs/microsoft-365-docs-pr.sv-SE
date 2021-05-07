---
title: Konfigurera Advanced eDiscovery i Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: I den här artikeln beskrivs hur du skapar Advanced eDiscovery så att du kan börja skapa och hantera ärenden. Dessutom beskrivs Microsoft-prenumerationer och -licensiering som krävs. När du har slutfört några få snabbsteg är Advanced eDiscovery klar att använda.
ms.openlocfilehash: 6c6aed482da8f203154d94313ec04519d6a330ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162055"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="bdec9-105">Konfigurera Microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bdec9-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="bdec9-106">Advanced eDiscovery i Microsoft 365 ett end-to-end-arbetsflöde för att bevara, samla in, granska, analysera och exportera data som svarar på organisationens interna och externa undersökningar.</span><span class="sxs-lookup"><span data-stu-id="bdec9-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="bdec9-107">Det krävs inget för att distribuera Advanced eDiscovery, men det finns vissa uppgifter som krävs för att en IT-administratör och eDiscovery-hanterare ska kunna slutföra innan organisationen kan börja skapa och använda Advanced eDiscovery-ärenden för att hantera undersökningarna.</span><span class="sxs-lookup"><span data-stu-id="bdec9-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="bdec9-108">I den här artikeln beskrivs följande steg för att konfigurera Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="bdec9-108">This article discusses the following steps necessary to set up Advanced eDiscovery.</span></span>

![Steg för att konfigurera Advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

<span data-ttu-id="bdec9-110">Det omfattar att säkerställa rätt licensiering som krävs för att komma åt Advanced eDiscovery och lägga till vårdnadshavare för ärenden samt att tilldela behörigheter till din juridiska grupp och undersökningsteam så att de kan komma åt och hantera ärenden.</span><span class="sxs-lookup"><span data-stu-id="bdec9-110">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="bdec9-111">Steg 1: Verifiera och tilldela rätt licenser</span><span class="sxs-lookup"><span data-stu-id="bdec9-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="bdec9-112">För licensiering Advanced eDiscovery krävs rätt organisationsprenumeration och licensiering per användare.</span><span class="sxs-lookup"><span data-stu-id="bdec9-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span> <span data-ttu-id="bdec9-113">En lista över licenskrav för Advanced eDiscovery finns i [Prenumerationer och licensiering](overview-ediscovery-20.md#subscriptions-and-licensing).</span><span class="sxs-lookup"><span data-stu-id="bdec9-113">For a list of licensing requirements for Advanced eDiscovery, see [Subscriptions and licensing](overview-ediscovery-20.md#subscriptions-and-licensing).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="bdec9-114">Steg 2: Tilldela eDiscovery-behörigheter</span><span class="sxs-lookup"><span data-stu-id="bdec9-114">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="bdec9-115">För att Advanced eDiscovery komma åt eller läggas till som medlem i Advanced eDiscovery ärende måste användaren tilldelas rätt behörigheter.</span><span class="sxs-lookup"><span data-stu-id="bdec9-115">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="bdec9-116">Specifikt måste en användare läggas till som medlem i rollgruppen för eDiscovery Manager i säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="bdec9-116">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="bdec9-117">Medlemmar i den här rollgruppen kan skapa och hantera Advanced eDiscovery ärenden.</span><span class="sxs-lookup"><span data-stu-id="bdec9-117">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="bdec9-118">De kan lägga till och ta bort medlemmar, placera dokumenterare och platser för innehåll i förvaring, hantera aviseringar om juridiska hinder, skapa och redigera sökningar associerade med ett ärende, lägga till sökresultat i en granskningsuppsättning, analysera data i en granskningsuppsättning och exportera och ladda ned från ett Advanced eDiscovery-ärende.</span><span class="sxs-lookup"><span data-stu-id="bdec9-118">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="bdec9-119">Utför följande steg för att lägga till användare i rollgruppen för eDiscovery-hanteraren:</span><span class="sxs-lookup"><span data-stu-id="bdec9-119">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="bdec9-120">Gå till <https://protection.office.com/permissions> och logga in med autentiseringsuppgifterna för ett administratörskonto i Microsoft 365 organisation.</span><span class="sxs-lookup"><span data-stu-id="bdec9-120">Go to <https://protection.office.com/permissions> and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="bdec9-121">På sidan **Behörigheter** väljer du **rollgruppen för eDiscovery-hanteraren.**</span><span class="sxs-lookup"><span data-stu-id="bdec9-121">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="bdec9-122">På den utfällande sidan för eDiscovery Manager klickar **du på** Redigera bredvid **avsnittet eDiscovery Manager.**</span><span class="sxs-lookup"><span data-stu-id="bdec9-122">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="bdec9-123">På sidan **Välj eDiscovery-hanteraren** i guiden för att redigera rollgrupp klickar du **på Välj eDiscovery-hanteraren.**</span><span class="sxs-lookup"><span data-stu-id="bdec9-123">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="bdec9-124">Klicka **på** Lägg till och markera kryssrutan för alla användare som du vill lägga till i rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="bdec9-124">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="bdec9-125">Klicka **på Lägg** till för att lägga till de valda användarna och klicka sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="bdec9-125">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="bdec9-126">Klicka **på** Spara för att lägga till användarna i rollgruppen och klicka sedan **på Stäng** för att slutföra steget.</span><span class="sxs-lookup"><span data-stu-id="bdec9-126">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="bdec9-127">Mer information om rollgruppen för eDiscovery-hanteraren</span><span class="sxs-lookup"><span data-stu-id="bdec9-127">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="bdec9-128">Det finns två undergrupper i rollgruppen för eDiscovery-hanteraren.</span><span class="sxs-lookup"><span data-stu-id="bdec9-128">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="bdec9-129">Skillnaden mellan dessa undergrupper beror på omfattningen.</span><span class="sxs-lookup"><span data-stu-id="bdec9-129">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="bdec9-130">**eDiscovery Manager:** Kan visa och hantera Advanced eDiscovery fall som de skapar eller är medlem i.</span><span class="sxs-lookup"><span data-stu-id="bdec9-130">**eDiscovery Manager**: Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="bdec9-131">Om en annan eDiscovery Manager skapar ett ärende men inte lägger till en andra eDiscovery Manager som medlem i det fallet kan inte den andra eDiscovery-hanteraren visa eller öppna ärendet på sidan Advanced eDiscovery i efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="bdec9-131">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="bdec9-132">I allmänhet kan de flesta i organisationen läggas till i undergruppen för eDiscovery Manager.</span><span class="sxs-lookup"><span data-stu-id="bdec9-132">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="bdec9-133">**eDiscovery-administratör:** Kan utföra alla uppgifter som en eDiscovery-hanterare kan utföra.</span><span class="sxs-lookup"><span data-stu-id="bdec9-133">**eDiscovery Administrator**: Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="bdec9-134">En eDiscovery-administratör kan dessutom:</span><span class="sxs-lookup"><span data-stu-id="bdec9-134">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="bdec9-135">Visa alla ärenden som listas på Advanced eDiscovery sidan.</span><span class="sxs-lookup"><span data-stu-id="bdec9-135">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="bdec9-136">Hantera alla ärende i organisationen när de har lagt till sig själva som medlem i ärendet.</span><span class="sxs-lookup"><span data-stu-id="bdec9-136">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="bdec9-137">Access och exportera ärendedata för alla fall i organisationen.</span><span class="sxs-lookup"><span data-stu-id="bdec9-137">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="bdec9-138">På grund av den breda omfattningen av åtkomst bör en organisation bara ha ett fåtal administratörer som är medlemmar i undergruppen eDiscovery-administratörer.</span><span class="sxs-lookup"><span data-stu-id="bdec9-138">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="bdec9-139">Mer information om eDiscovery-behörigheter och en beskrivning av varje roll som tilldelas till rollgruppen för eDiscovery-hanteraren finns i Tilldela [eDiscovery-behörigheter.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="bdec9-139">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="bdec9-140">Steg 3: Konfigurera globala inställningar för Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bdec9-140">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="bdec9-141">Det sista steget innan användare i organisationen börjar skapa och använda ärenden är att konfigurera globala inställningar som gäller för alla ärenden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="bdec9-141">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="bdec9-142">För närvarande är den enda globala inställningen identifiering *av klientbehörighet* för jurister (fler globala inställningar kommer att vara tillgängliga i framtiden).</span><span class="sxs-lookup"><span data-stu-id="bdec9-142">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="bdec9-143">Med den här inställningen kan juristklientens behörighetsmodell köras när du analyserar data i en uppsättning med granskning.</span><span class="sxs-lookup"><span data-stu-id="bdec9-143">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="bdec9-144">I modellen används maskininlärning för att avgöra hur sannolikt det är att ett dokument innehåller innehåll som är lagligt.</span><span class="sxs-lookup"><span data-stu-id="bdec9-144">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="bdec9-145">Dessutom jämförs deltagarna i dokument med en juristlista (som du skickar in vid inställning av modellen) för att avgöra om ett dokument har minst en deltagare som är jurist.</span><span class="sxs-lookup"><span data-stu-id="bdec9-145">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="bdec9-146">Mer information om hur du inställningar och använder modellen för identifiering av juristklienter finns i Konfigurera identifiering av behörigheter för [juristklienter i Advanced eDiscovery.](attorney-privilege-detection.md)</span><span class="sxs-lookup"><span data-stu-id="bdec9-146">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bdec9-147">Det här är ett valfritt steg som du kan utföra när som helst.</span><span class="sxs-lookup"><span data-stu-id="bdec9-147">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="bdec9-148">Att inte implementera modellen för identifiering av juristklienter hindrar dig inte från att skapa och använda Advanced eDiscovery ärenden.</span><span class="sxs-lookup"><span data-stu-id="bdec9-148">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bdec9-149">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="bdec9-149">Next steps</span></span>

<span data-ttu-id="bdec9-150">När du har Advanced eDiscovery är du redo att [skapa ett ärende](create-and-manage-advanced-ediscoveryv2-case.md).</span><span class="sxs-lookup"><span data-stu-id="bdec9-150">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>