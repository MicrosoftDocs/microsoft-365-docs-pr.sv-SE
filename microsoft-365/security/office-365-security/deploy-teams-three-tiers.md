---
title: Distribuera team för tre skyddsnivåer för filer
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Skapa och konfigurera team med Microsoft Teams för olika nivåer av informationsskydd för filer.
ms.openlocfilehash: d8912900a02149d198222a4402e101b0dce53310
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637646"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="8c831-103">Distribuera team för tre skyddsnivåer för filer</span><span class="sxs-lookup"><span data-stu-id="8c831-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="8c831-104">Använd anvisningarna i den här artikeln för att utforma och distribuera baslinjeteam samt känsliga eller strikt konfidentiella team.</span><span class="sxs-lookup"><span data-stu-id="8c831-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential teams.</span></span> <span data-ttu-id="8c831-105">Mer information om de här tre nivåerna av skydd finns i [Skydda filer i Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8c831-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>

## <a name="baseline-teams"></a><span data-ttu-id="8c831-106">Baslinjeteam</span><span class="sxs-lookup"><span data-stu-id="8c831-106">Baseline teams</span></span>

<span data-ttu-id="8c831-107">Baslinjeskydd omfattar både offentliga och privata team.</span><span class="sxs-lookup"><span data-stu-id="8c831-107">Baseline protection includes both public and private teams.</span></span> <span data-ttu-id="8c831-108">Offentliga team kan upptäckas och användas av alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8c831-108">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="8c831-109">Privata webbplatser kan bara upptäckas och användas av medlemmar i den Microsoft 365-grupp som är kopplad till teamet.</span><span class="sxs-lookup"><span data-stu-id="8c831-109">Private sites can only be discovered and accessed by members of the Microsoft 365 group associated with the team.</span></span> <span data-ttu-id="8c831-110">Medlemmar i båda dessa typer av team kan dela webbplatsen med andra.</span><span class="sxs-lookup"><span data-stu-id="8c831-110">Both of these types of teams allow members to share the site with others.</span></span>

### <a name="public"></a><span data-ttu-id="8c831-111">Offentlig</span><span class="sxs-lookup"><span data-stu-id="8c831-111">Public</span></span>

<span data-ttu-id="8c831-112">Följ anvisningarna i [den här artikeln](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) om du vill skapa ett baslinjeteam med offentlig åtkomst och behörigheter.</span><span class="sxs-lookup"><span data-stu-id="8c831-112">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with public access and permissions.</span></span>

<span data-ttu-id="8c831-113">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="8c831-113">Here is your resulting configuration.</span></span>

![Skydd på baslinjenivå för ett offentligt team.](../../media/baseline-public-team.png)

### <a name="private"></a><span data-ttu-id="8c831-115">Privat</span><span class="sxs-lookup"><span data-stu-id="8c831-115">Private</span></span>

<span data-ttu-id="8c831-116">Följ anvisningarna i [den här artikeln](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) om du vill skapa ett baslinjeteam med privat åtkomst och behörigheter.</span><span class="sxs-lookup"><span data-stu-id="8c831-116">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with private access and permissions.</span></span>

<span data-ttu-id="8c831-117">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="8c831-117">Here is your resulting configuration.</span></span>

![Skydd på baslinjenivå för ett privat team.](../../media/baseline-private-team.png)

## <a name="sensitive-teams"></a><span data-ttu-id="8c831-119">Känsliga team</span><span class="sxs-lookup"><span data-stu-id="8c831-119">Sensitive teams</span></span>

<span data-ttu-id="8c831-120">För ett känsligt team börjar du med att [skapa ett privat team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="8c831-120">For a sensitive team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="8c831-121">Därefter konfigurerar du den underliggande SharePoint-webbplatsen så att teammedlemmar inte kan dela.</span><span class="sxs-lookup"><span data-stu-id="8c831-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1. <span data-ttu-id="8c831-122">I verktygsfältet för teamet klickar du på **Filer**.</span><span class="sxs-lookup"><span data-stu-id="8c831-122">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="8c831-123">Klicka på ellipsen och sedan på **Öppna i SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8c831-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="8c831-124">Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="8c831-124">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="8c831-125">I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="8c831-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="8c831-126">Under **Delningsbehörigheter** väljer du **Endast webbplatsens ägare kan dela filer, mappar och webbplatsen**. Klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8c831-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="8c831-127">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="8c831-127">Here is your resulting configuration.</span></span>

![Känsligt skydd för ett team.](../../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a><span data-ttu-id="8c831-129">Strikt konfidentiella team</span><span class="sxs-lookup"><span data-stu-id="8c831-129">Highly confidential teams</span></span>

<span data-ttu-id="8c831-130">För ett strikt konfidentiellt team börjar du med att [skapa ett privat team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="8c831-130">With a highly confidential team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="8c831-131">Därefter konfigurerar du den underliggande SharePoint-webbplatsen så att teammedlemmar inte kan dela och för att förhindra att personer som inte är medlemmar i teamet kan begära åtkomst.</span><span class="sxs-lookup"><span data-stu-id="8c831-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1. <span data-ttu-id="8c831-132">I verktygsfältet för teamet klickar du på **Filer**.</span><span class="sxs-lookup"><span data-stu-id="8c831-132">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="8c831-133">Klicka på ellipsen och sedan på **Öppna i SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8c831-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="8c831-134">Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="8c831-134">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="8c831-135">I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="8c831-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="8c831-136">Under **Delningsbehörigheter** väljer du **Endast webbplatsägare kan dela filer, mappar och webbplats**.</span><span class="sxs-lookup"><span data-stu-id="8c831-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

6. <span data-ttu-id="8c831-137">Inaktivera **Tillåt åtkomstbegäranden** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8c831-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="8c831-138">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="8c831-138">Here is your resulting configuration.</span></span>

![Strikt konfidentiellt skydd för ett team.](../../media/highly-confidential-team.png)

## <a name="next-step"></a><span data-ttu-id="8c831-140">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8c831-140">Next step</span></span>

[<span data-ttu-id="8c831-141">Skydda filer i team med kvarhållningsetiketter och DLP</span><span class="sxs-lookup"><span data-stu-id="8c831-141">Protect files in teams with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="8c831-142">Se även</span><span class="sxs-lookup"><span data-stu-id="8c831-142">See also</span></span>

[<span data-ttu-id="8c831-143">Skydda filer i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c831-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)

[<span data-ttu-id="8c831-144">Införande av moln- och hybridlösningar</span><span class="sxs-lookup"><span data-stu-id="8c831-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
