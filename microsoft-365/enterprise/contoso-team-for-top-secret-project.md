---
title: Team för ett topphemligt projekt på Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Sammanfattning: Hur Contoso använde ett team för starkt reglerade data för ett topphemligt projekt för att utveckla en ny uppsättning produkter och tjänster.'
ms.openlocfilehash: 310ef33d4add7d71616aee8808515ca90536d8c1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636504"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="125ed-103">Team för ett topphemligt projekt på Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="125ed-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="125ed-104">Efter en verkställande offsite, Contoso VD beställde utvecklingen av en ny svit av produkter och tjänster som kan fördubbla Contoso vinst under de kommande fem åren.</span><span class="sxs-lookup"><span data-stu-id="125ed-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="125ed-105">Det topphemliga projektet för att utveckla affärs-, ingenjörs- och marknadsplanen fick namnet **Project 2X** och nyckelpersonal i hela företaget rekryterades.</span><span class="sxs-lookup"><span data-stu-id="125ed-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="125ed-106">Tidslinjerna för forskning och utveckling var snäva, vilket innebar att samarbetet måste vara effektivt och ge säkra möten, pågående samtal och fillagring.</span><span class="sxs-lookup"><span data-stu-id="125ed-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="125ed-107">De resulterande slutprodukterna för Project 2X var affärsplaner, produkt- och teknikspecifikationer samt marknadsföringsmaterial och scheman i form av Word-, Excel- och PowerPoint-filer.</span><span class="sxs-lookup"><span data-stu-id="125ed-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="125ed-108">På grund av deras känsliga karaktär, tillgång till dessa filer var:</span><span class="sxs-lookup"><span data-stu-id="125ed-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="125ed-109">Begränsad till Project 2X-gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="125ed-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="125ed-110">Skyddad med en DLP-princip (Data Loss Prevention) för att förhindra att Project 2X-gruppmedlemmar delar dem utanför teamet.</span><span class="sxs-lookup"><span data-stu-id="125ed-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="125ed-111">Krypterad och skyddad med behörighet att endast tillåta åtkomst till Project 2X-gruppmedlemmar, även om filerna distribuerades utanför Contoso.</span><span class="sxs-lookup"><span data-stu-id="125ed-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="125ed-112">Contoso [IT-personal](secure-teams-highly-regulated-data-scenario.md) använde ett team för starkt reglerade data för Project 2X och dessa steg.</span><span class="sxs-lookup"><span data-stu-id="125ed-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="125ed-113">Steg 1: Skapade ett privat team och låste den underliggande SharePoint-webbplatsen</span><span class="sxs-lookup"><span data-stu-id="125ed-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="125ed-114">För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för teamet konfigurerade Contoso IT-administratörer de [rekommenderade SharePoint-åtkomstprinciperna](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="125ed-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="125ed-115">Därefter skapade en Contoso IT-administratör ett nytt privat team med namnet Project 2X och lade till användarkontona för Project 2X-personal som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="125ed-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="125ed-116">Därefter konfigurerade de ytterligare behörighetsinställningar för webbplatsen för att förhindra att Project 2X delar åtkomst till webbplatsen och för att förhindra att andra begär åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="125ed-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="125ed-117">Konfigurationsinformation finns i [SharePoint-inställningar för ett starkt reglerat team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span><span class="sxs-lookup"><span data-stu-id="125ed-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="125ed-118">Steg 2: Konfigurerade en DLP-princip och den underliggande platsen för en kvarhållningsetikett</span><span class="sxs-lookup"><span data-stu-id="125ed-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="125ed-119">Först tillämpade Contoso-administratörer den befintliga **mycket konfidentiella** lagringsetiketten **Documents** på dokumentavsnittet på den underliggande SharePoint-webbplatsen för Project 2X-teamet.</span><span class="sxs-lookup"><span data-stu-id="125ed-119">First, Contoso admins applied the existing **Highly Confidential** retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="125ed-120">Därefter skapade de en ny DLP-princip med namnet **Project 2X** som:</span><span class="sxs-lookup"><span data-stu-id="125ed-120">Next, they created a new DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="125ed-121">Använder etiketten Mycket konfidentiell kvarhållning.</span><span class="sxs-lookup"><span data-stu-id="125ed-121">Uses the Highly Confidential retention label.</span></span>
- <span data-ttu-id="125ed-122">Blockerar användare när de försöker dela en fil i Project 2X-teamet utanför Contoso.</span><span class="sxs-lookup"><span data-stu-id="125ed-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="125ed-123">Konfigurationsinformation finns [i Skydda filer i team med kvarhållningsetiketter och DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span><span class="sxs-lookup"><span data-stu-id="125ed-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="125ed-124">Steg 3: Skapade en känslighetsetikett för Project 2X-teamet</span><span class="sxs-lookup"><span data-stu-id="125ed-124">Step 3: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="125ed-125">Contoso-administratörer skapade en ny känslighetsetikett med namnet **Project 2X** som:</span><span class="sxs-lookup"><span data-stu-id="125ed-125">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="125ed-126">Kräver kryptering.</span><span class="sxs-lookup"><span data-stu-id="125ed-126">Requires encryption.</span></span>
- <span data-ttu-id="125ed-127">Tillåter samtidiga redigeringsbehörigheter för gruppen Project 2X Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="125ed-127">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="125ed-128">Här är den resulterande konfigurationen av Project 2X-teamet.</span><span class="sxs-lookup"><span data-stu-id="125ed-128">Here is the resulting configuration of the Project 2X team.</span></span>

![Den resulterande konfigurationen av Project 2X-teamet](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="125ed-130">Filerna i avsnittet Dokument på den underliggande Project 2X SharePoint-webbplatsen skyddades av:</span><span class="sxs-lookup"><span data-stu-id="125ed-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="125ed-131">Webbplatsbehörigheterna, som endast ger åtkomst till medlemmar i Gruppen Project 2X Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="125ed-131">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="125ed-132">Den mycket konfidentiella kvarhållningsetiketten, som automatiskt tilldelas nya filer.</span><span class="sxs-lookup"><span data-stu-id="125ed-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="125ed-133">En DLP-princip som använder etiketten Mycket konfidentiell kvarhållning och inställningar som blockerar filen från att delas med externa användare.</span><span class="sxs-lookup"><span data-stu-id="125ed-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="125ed-134">Känslighetsetiketten För Project 2X, med kryptering och behörigheter som färdas med filen om den flyttas eller kopieras från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="125ed-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="125ed-135">Här är ett exempel på en fil som lagras i den underliggande Project 2X-platsen med den starkt reglerade kvarhållningsetiketten och känslighetsetiketten Project 2X tilldelad.</span><span class="sxs-lookup"><span data-stu-id="125ed-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![Ett exempel på en fil som lagras på den underliggande Project 2X-platsen](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="125ed-137">Steg 4: Utbildade Project 2X-gruppmedlemmar</span><span class="sxs-lookup"><span data-stu-id="125ed-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="125ed-138">Contoso säkerhetspersonal utbildade Project 2X-teammedlemmarna i en obligatorisk kurs som klev igenom dem:</span><span class="sxs-lookup"><span data-stu-id="125ed-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="125ed-139">Så här kommer du åt det nya Project 2X-teamet, använder möten och chattar och hur du samarbetar i gruppfiler.</span><span class="sxs-lookup"><span data-stu-id="125ed-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="125ed-140">Så här skapar du nya filer i teamet och laddar upp nya filer som skapats lokalt.</span><span class="sxs-lookup"><span data-stu-id="125ed-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="125ed-141">En demonstration av hur DLP-principen blockerar filer från att delas externt.</span><span class="sxs-lookup"><span data-stu-id="125ed-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="125ed-142">Så här märker du filer med känslighetsetiketten För Project 2X.</span><span class="sxs-lookup"><span data-stu-id="125ed-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="125ed-143">En demonstration av hur Project 2X-etiketten skyddar en fil även när den lämnar teamet.</span><span class="sxs-lookup"><span data-stu-id="125ed-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="125ed-144">Slutresultatet blev en säker miljö där Project 2X-gruppmedlemmar samarbetade i en säker miljö för chattar, möten och filer.</span><span class="sxs-lookup"><span data-stu-id="125ed-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="125ed-145">I ett par fall hämtade Project 2X-gruppmedlemmar filer som skyddas av Project 2X-etiketten till en lokal enhet för offlinearbete.</span><span class="sxs-lookup"><span data-stu-id="125ed-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="125ed-146">Men efter att ha uppmanats om autentiseringsuppgifter när de öppnades, insåg de sitt misstag och tog bort dem.</span><span class="sxs-lookup"><span data-stu-id="125ed-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="125ed-147">På grund av teamens samarbetsmiljö och säkerhetsfunktionerna i Microsoft 365 hölls detaljerna i Project 2X hemliga under hela projektet.</span><span class="sxs-lookup"><span data-stu-id="125ed-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="125ed-148">Contoso tillkännagav sina planer och håller på att rulla ut de nya produkterna och tjänsterna till glädje för sina kunder och investerare och förtret för sina konkurrenter.</span><span class="sxs-lookup"><span data-stu-id="125ed-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="125ed-149">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="125ed-149">Next step</span></span>

<span data-ttu-id="125ed-150">[Distribuera](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise i din organisation.</span><span class="sxs-lookup"><span data-stu-id="125ed-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="125ed-151">Snabbreferens</span><span class="sxs-lookup"><span data-stu-id="125ed-151">See also</span></span>

<span data-ttu-id="125ed-152">[Produktivitetsbiblioteket för Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="125ed-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
