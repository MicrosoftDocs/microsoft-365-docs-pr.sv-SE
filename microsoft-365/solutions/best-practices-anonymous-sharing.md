---
title: Metodtips för oautentiserad delning
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: I den här artikeln får du lära dig mer om metodtips för att dela filer och mappar med oautentiserade användare.
ms.openlocfilehash: cea60152f06e8fbd242c9641b962bc9a96fdd019
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560481"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a><span data-ttu-id="f0d59-103">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="f0d59-103">Best practices for sharing files and folders with unauthenticated users</span></span>

<span data-ttu-id="f0d59-104">Oautentiserad delning (*Alla*-länkar) kan vara smidigt och användbart i olika scenarier.</span><span class="sxs-lookup"><span data-stu-id="f0d59-104">Unauthenticated sharing (*Anyone* links) can be convenient and is useful in various scenarios.</span></span> <span data-ttu-id="f0d59-105">*Alla*-länkar är det enklaste sättet att dela: personer kan öppna länken utan autentisering och kan skicka den vidare till andra.</span><span class="sxs-lookup"><span data-stu-id="f0d59-105">*Anyone* links are the easiest way to share: people can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="f0d59-106">Vanligtvis är inte allt innehåll i en organisation lämpligt för oautentiserad delning.</span><span class="sxs-lookup"><span data-stu-id="f0d59-106">Usually, not all content in an organization is appropriate for unauthenticated sharing.</span></span> <span data-ttu-id="f0d59-107">I den här artikeln beskrivs de alternativ som är tillgängliga för att hjälpa dig att skapa en miljö där dina användare kan använda oautentiserad delning av filer och mappar, men där det finns säkerhetsåtgärder för att skydda organisationens innehåll.</span><span class="sxs-lookup"><span data-stu-id="f0d59-107">This article covers the options available to help you create an environment where your users can use unauthenticated sharing of files and folders, but where there are safeguards in place to help protect your organization's content.</span></span>

> [!NOTE]
> <span data-ttu-id="f0d59-108">För att oautentiserad delning ska fungera måste du aktivera den för din organisation och för den enskilda webbplatsen eller det team som du ska använda.</span><span class="sxs-lookup"><span data-stu-id="f0d59-108">For unauthenticated sharing to work, you must enable it for your organization and for the individual site or team that you'll be using.</span></span> <span data-ttu-id="f0d59-109">Se [Samarbeta med personer utanför organisationen](collaborate-with-people-outside-your-organization.md) för det scenario du vill aktivera.</span><span class="sxs-lookup"><span data-stu-id="f0d59-109">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for the scenario that you want to enable.</span></span>

## <a name="set-an-expiration-date-for-anyone-links"></a><span data-ttu-id="f0d59-110">Ange ett utgångsdatum för Alla-länkar</span><span class="sxs-lookup"><span data-stu-id="f0d59-110">Set an expiration date for Anyone links</span></span>

<span data-ttu-id="f0d59-111">Filer lagras ofta på webbplatser, i grupper och team under långa tidsperioder.</span><span class="sxs-lookup"><span data-stu-id="f0d59-111">Files are often stored in sites, groups, and teams for long periods of time.</span></span> <span data-ttu-id="f0d59-112">Ibland finns det datakvarhållningsprinciper som kräver att filer bevaras i flera år.</span><span class="sxs-lookup"><span data-stu-id="f0d59-112">Occasionally there are data retention policies that require files to be retained for years.</span></span> <span data-ttu-id="f0d59-113">Om de här filerna delas med oautentiserade personer kan detta leda till oväntad åtkomst och framtida ändringar i filerna.</span><span class="sxs-lookup"><span data-stu-id="f0d59-113">If such files are shared with unauthenticated people, this could lead to unexpected access and changes to files in the future.</span></span> <span data-ttu-id="f0d59-114">Om du vill minska risken för detta kan du konfigurera en förfallotid för *Alla*-länkar.</span><span class="sxs-lookup"><span data-stu-id="f0d59-114">To mitigate this possibility, you can configure an expiration time for *Anyone* links.</span></span>

<span data-ttu-id="f0d59-115">När en *Alla*-länk går ut kan den inte längre användas för att få åtkomst till innehåll.</span><span class="sxs-lookup"><span data-stu-id="f0d59-115">Once an *Anyone* link expires, it can no longer be used to access content.</span></span>

<span data-ttu-id="f0d59-116">Ange ett utgångsdatum för Alla-länkar</span><span class="sxs-lookup"><span data-stu-id="f0d59-116">To set an expiration date for Anyone links</span></span>
1. <span data-ttu-id="f0d59-117">Öppna administrationscentret för SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f0d59-117">Open the SharePoint Online admin center.</span></span>
2. <span data-ttu-id="f0d59-118">Klicka på **Delning** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f0d59-118">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="f0d59-119">Markera kryssrutan **Länkarna måste upphöra att gälla inom så här många dagar** under **Välj behörigheter och giltighetsalternativ för Alla-länkar**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-119">Under **Choose expiration and permissions options for Anyone links**, select the **These links must expire within this many days** check box.</span></span></br>
   <span data-ttu-id="f0d59-120">![Skärmbild av inställningar för utgången av Alla-länkar för SharePoint på organisationsnivå](../media/sharepoint-organization-anyone-link-expiration.png)</span><span class="sxs-lookup"><span data-stu-id="f0d59-120">![Screenshot of SharePoint organization-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration.png)</span></span>
4. <span data-ttu-id="f0d59-121">Skriv ett antal dagar i rutan och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-121">Type a number of days in the box, and then click **Save**.</span></span>

<span data-ttu-id="f0d59-122">Tänk på att när en *Alla*-länk går ut kan filen eller mappen delas igen med en ny *Alla*-länk.</span><span class="sxs-lookup"><span data-stu-id="f0d59-122">Note that once an *Anyone* link expires, the file or folder can be re-shared with a new *Anyone* link.</span></span>

<span data-ttu-id="f0d59-123">Du kan ange *vem som helst* för länkens utgång för en specifik webbplats eller OneDrive med hjälp av [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite).</span><span class="sxs-lookup"><span data-stu-id="f0d59-123">You can set *Anyone* link expiration for a specific site or OneDrive by using [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite).</span></span>

## <a name="set-link-permissions"></a><span data-ttu-id="f0d59-124">Ange behörigheter för länk</span><span class="sxs-lookup"><span data-stu-id="f0d59-124">Set link permissions</span></span>

<span data-ttu-id="f0d59-125">*Alla*-länkar för en fil tillåter som standard personer att redigera filen, och *Alla*-länkar för en mapp tillåter personer att redigera och visa filer samt att ladda upp nya filer till mappen.</span><span class="sxs-lookup"><span data-stu-id="f0d59-125">By default, *Anyone* links for a file allow people to edit the file, and *Anyone* links for a folder allow people to edit and view files, and upload new files to the folder.</span></span> <span data-ttu-id="f0d59-126">Du kan ändra de här behörigheterna till endast visning för filer och mappar oberoende av varandra.</span><span class="sxs-lookup"><span data-stu-id="f0d59-126">You can change these permissions for files and for folders independently to view-only.</span></span>

<span data-ttu-id="f0d59-127">Om du vill tillåta oautentiserad delning, men är orolig för att oautentiserade personer ska ändra organisationens innehåll, bör du överväga att ställa in behörigheterna för filer och mappar till **Visa**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-127">If you want to allow unauthenticated sharing, but are concerned about unauthenticated people modifying your organization's content, consider setting the file and folder permissions to **View**.</span></span>

<span data-ttu-id="f0d59-128">Ange behörigheter för Alla-länkar</span><span class="sxs-lookup"><span data-stu-id="f0d59-128">To set permissions for Anyone links</span></span>
1. <span data-ttu-id="f0d59-129">Öppna administrationscentret för SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f0d59-129">Open the SharePoint Online admin center.</span></span>
2. <span data-ttu-id="f0d59-130">Klicka på **Delning** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f0d59-130">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="f0d59-131">Under **Avancerade inställningar för "Alla"-länkar** väljer du de fil- och mappbehörigheter som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="f0d59-131">Under **Advanced settings for "Anyone" links**, select the file and folder permissions that you want to use.</span></span></br>
   <span data-ttu-id="f0d59-132">![Skärmbild av behörighetsinställningar för Alla-länkar för SharePoint på organisationsnivå](../media/sharepoint-organization-anyone-link-permissions.png)</span><span class="sxs-lookup"><span data-stu-id="f0d59-132">![Screenshot of SharePoint organization-level Anyone link permissions settings](../media/sharepoint-organization-anyone-link-permissions.png)</span></span>

<span data-ttu-id="f0d59-133">Med *Alla*-länkar inställda på **Visa** kan användare fortfarande dela filer och mappar med gäster och ge dem redigeringsbehörighet genom att använda *Specifika personer*-länkar.</span><span class="sxs-lookup"><span data-stu-id="f0d59-133">With *Anyone* links set to **View**, users can still share files and folders with guests and give them edit permissions by using *Specific people* links.</span></span> <span data-ttu-id="f0d59-134">Med dessa länkar måste personer utanför organisationen autentiseras som gäster, och du kan spåra och granska gästaktiviteten i filer och mappar som delas med dessa länkar.</span><span class="sxs-lookup"><span data-stu-id="f0d59-134">These links require people outside your organization to authenticate as guests, and you can track and audit guest activity on files and folders shared with these links.</span></span>

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a><span data-ttu-id="f0d59-135">Ställa in standardlänktypen till att endast fungera för personer i organisationen</span><span class="sxs-lookup"><span data-stu-id="f0d59-135">Set default link type to only work for people in your organization</span></span>

<span data-ttu-id="f0d59-136">När *Alla*-delning aktiveras för organisationen anges normalt delningslänken till **Alla**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-136">When *Anyone* sharing is enabled for your organization, the default sharing link is normally set to **Anyone**.</span></span> <span data-ttu-id="f0d59-137">Det kan vara praktiskt för användarna, men kan öka risken för oavsiktlig oautentiserad delning.</span><span class="sxs-lookup"><span data-stu-id="f0d59-137">While this can be convenient for users, it can increase the risk of unintentional unauthenticated sharing.</span></span> <span data-ttu-id="f0d59-138">Om en användare glömmer att ändra länktypen vid delning av ett känsligt dokument, kan det hända att de oavsiktligt skapar en delningslänk som inte kräver autentisering.</span><span class="sxs-lookup"><span data-stu-id="f0d59-138">If a user forgets to change the link type while sharing a sensitive document, they might accidentally create a sharing link that doesn't require authentication.</span></span>

<span data-ttu-id="f0d59-139">Du kan minska den här risken genom att ändra standardlänkinställningen till en länk som bara fungerar för personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f0d59-139">You can mitigate this risk by changing the default link setting to a link that only works for people inside your organization.</span></span> <span data-ttu-id="f0d59-140">Användare som vill dela med oautentiserade personer måste då specifikt välja det alternativet.</span><span class="sxs-lookup"><span data-stu-id="f0d59-140">Users who want to share with unauthenticated people would then have to specifically select that option.</span></span>

<span data-ttu-id="f0d59-141">Ange standarddelningslänken för filer och mappar</span><span class="sxs-lookup"><span data-stu-id="f0d59-141">To set the default file and folder sharing link</span></span>
1. <span data-ttu-id="f0d59-142">I navigeringsfönstret till vänster i administrationscentret för SharePoint klickar du på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-142">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="f0d59-143">Under **Fil- och mapplänkar** väljer du **Endast personer i organisationen**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-143">Under **File and folder links**, select **Only people in your organization**.</span></span></br>
   <span data-ttu-id="f0d59-144">![Skärmbild av inställning för standardlänktyp för SharePoint](../media/sharepoint-default-sharing-link-company-link.png)</span><span class="sxs-lookup"><span data-stu-id="f0d59-144">![Screenshot of SharePoint default link type setting](../media/sharepoint-default-sharing-link-company-link.png)</span></span>
3. <span data-ttu-id="f0d59-145">Klicka på **Spara**</span><span class="sxs-lookup"><span data-stu-id="f0d59-145">Click **Save**</span></span>

## <a name="protect-against-malicious-files"></a><span data-ttu-id="f0d59-146">Skydda mot skadliga filer</span><span class="sxs-lookup"><span data-stu-id="f0d59-146">Protect against malicious files</span></span>

<span data-ttu-id="f0d59-147">Om du tillåter anonyma användare att ladda upp filer ökar risken för att någon laddar upp en skadlig fil.</span><span class="sxs-lookup"><span data-stu-id="f0d59-147">When you allow anonymous users to upload files, you're at an increased risk of someone uploading a malicious file.</span></span> <span data-ttu-id="f0d59-148">I Microsoft 365 kan du använda funktionen för *säkra bifogade filer* i avancerat skydd för att automatiskt söka igenom uppladdade filer och sätta filer som kan vara osäkra i karantän.</span><span class="sxs-lookup"><span data-stu-id="f0d59-148">In Microsoft 365, you can use the *safe attachments* feature in Advanced Threat Protection to automatically scan uploaded files and quarantine files that are found to be unsafe.</span></span>

<span data-ttu-id="f0d59-149">Aktivera säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="f0d59-149">To turn on safe attachments</span></span>
1. <span data-ttu-id="f0d59-150">Öppna administrationscentret för [Microsoft 365 Säkerhet](https://security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f0d59-150">Open the [Microsoft 365 security](https://security.microsoft.com) admin center.</span></span>
2. <span data-ttu-id="f0d59-151">Klicka på **Principer** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f0d59-151">In the left navigation, click **Policies**.</span></span>
3. <span data-ttu-id="f0d59-152">Under **Skydd mot hot** klickar du på **ATP – säkra bifogade filer (Office 365)**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-152">Under **Threat protection**, click **ATP safe attachments (Office 365)**.</span></span>
4. <span data-ttu-id="f0d59-153">Markera kryssrutan **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-153">Select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box, and then click **Save**.</span></span></br>
   <span data-ttu-id="f0d59-154">![Skärmbild av inställningen för säkra bifogade filer i Säkerhets- och efterlevnadscenter](../media/safe-attachments-setting.png)</span><span class="sxs-lookup"><span data-stu-id="f0d59-154">![Screenshot of the safe attachments setting in the Security and Compliance center](../media/safe-attachments-setting.png)</span></span>

## <a name="add-copyright-information-to-your-files"></a><span data-ttu-id="f0d59-155">Lägga till copyrightinformation i dina filer</span><span class="sxs-lookup"><span data-stu-id="f0d59-155">Add copyright information to your files</span></span>

<span data-ttu-id="f0d59-156">Om du använder känslighetsetiketter i administrationscentret för Microsoft 365 Efterlevnad kan du konfigurera etiketterna för att automatiskt lägga till en vattenstämpel eller ett sidhuvud eller en sidfot i organisationens Office-dokument.</span><span class="sxs-lookup"><span data-stu-id="f0d59-156">If you use sensitivity labels in the Microsoft 365 Compliance admin center, you can configure your labels to add a watermark or a header or footer automatically to your organization's Office documents.</span></span> <span data-ttu-id="f0d59-157">På så sätt kan du se till att delade filer innehåller copyright- eller annan ägarskapsinformation.</span><span class="sxs-lookup"><span data-stu-id="f0d59-157">In this way, you can make sure that shared files contain copyright or other ownership information.</span></span>

<span data-ttu-id="f0d59-158">Lägga till en sidfot i en fil med en etikett</span><span class="sxs-lookup"><span data-stu-id="f0d59-158">To add a footer to a labeled file</span></span>
1. <span data-ttu-id="f0d59-159">Öppna [administrationscentret för Microsoft 365 Efterlevnad](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f0d59-159">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="f0d59-160">I det vänstra navigeringsfönstret, under **Klassificering**, klickar du på **Känslighetsetiketter**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-160">In the left navigation, under **Classification**, click **Sensitivity labels**.</span></span>
3. <span data-ttu-id="f0d59-161">Klicka på den etikett som du vill använda för att lägga till en sidfot och klicka sedan på **Redigera etikett**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-161">Click the label that you want to have add a footer, and then click **Edit label**.</span></span>
4. <span data-ttu-id="f0d59-162">Klicka på fliken **Märkning av innehåll** och sätt sedan **på** innehållsmärkning.</span><span class="sxs-lookup"><span data-stu-id="f0d59-162">Click the **Content marking** tab, and then turn **On** content marking.</span></span>
5. <span data-ttu-id="f0d59-163">Markera kryssrutan för den typ av text som du vill lägga till och klicka sedan på **Anpassa text**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-163">Select the check box for the type of text you want to add, and then click **Customize text**.</span></span>
6. <span data-ttu-id="f0d59-164">Skriv den text du vill lägga till i dina dokument, markera de textalternativ som du vill använda och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-164">Type the text that you want added to your documents, select the text options that you want, and then click **Save**.</span></span></br>
   <span data-ttu-id="f0d59-165">![Skärmbild av inställningar för innehållsmärkning för en känslighetsetikett](../media/content-marking-for-anonymous-sharing.png)</span><span class="sxs-lookup"><span data-stu-id="f0d59-165">![Screenshot of the content marking settings for a sensitivity label](../media/content-marking-for-anonymous-sharing.png)</span></span>
7. <span data-ttu-id="f0d59-166">Klicka på **Spara** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="f0d59-166">Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="f0d59-167">När du har aktiverat innehållsmärkning för etiketten läggs den text som du angett till i Office-dokument när en användare använder etiketten.</span><span class="sxs-lookup"><span data-stu-id="f0d59-167">With content marking enabled for the label, the text you specified will be added to Office documents when a user applies that label.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0d59-168">Se även</span><span class="sxs-lookup"><span data-stu-id="f0d59-168">See Also</span></span>


[<span data-ttu-id="f0d59-169">Översikt över känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="f0d59-169">Overview of sensitivity labels</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)

[<span data-ttu-id="f0d59-170">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="f0d59-170">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="f0d59-171">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="f0d59-171">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
