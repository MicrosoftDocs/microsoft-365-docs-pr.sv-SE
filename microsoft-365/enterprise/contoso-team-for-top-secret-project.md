---
title: Team för ett topphemligt projekt av Contoso Corporation
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
ms.openlocfilehash: 58d381751db3e94f35a0c1b8f7a14c191918e754
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811498"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="8eb80-103">Team för ett topphemligt projekt av Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="8eb80-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="8eb80-104">Efter en verkställande offsite, beställde Contoso VD utvecklingen av en ny svit av produkter och tjänster som kan fördubbla Contoso vinst under de kommande fem åren.</span><span class="sxs-lookup"><span data-stu-id="8eb80-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="8eb80-105">Det topphemliga projektet för att utveckla affärs-, ingenjörs- och marknadsplanen utsågs till **Project 2X** och nyckelpersonal i hela företaget rekryterades.</span><span class="sxs-lookup"><span data-stu-id="8eb80-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="8eb80-106">Tidslinjerna för forskning och utveckling var snäva, vilket innebar att samarbetet måste vara effektivt och ge säkra möten, pågående samtal och fillagring.</span><span class="sxs-lookup"><span data-stu-id="8eb80-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="8eb80-107">De resulterande slutprodukter för Project 2X var affärsplaner, produkt- och teknikspecifikationer samt marknadsföringsmaterial och scheman i form av Word-, Excel- och PowerPoint-filer.</span><span class="sxs-lookup"><span data-stu-id="8eb80-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="8eb80-108">På grund av sin känsliga natur var tillgången till dessa filer:</span><span class="sxs-lookup"><span data-stu-id="8eb80-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="8eb80-109">Begränsad till Project 2X-gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="8eb80-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="8eb80-110">Skyddas med en DLP-princip (Data Loss Prevention) för att förhindra att Project 2X-gruppmedlemmar delar dem utanför teamet.</span><span class="sxs-lookup"><span data-stu-id="8eb80-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="8eb80-111">Krypterad och skyddad med behörighet för att endast tillåta åtkomst till Project 2X-gruppmedlemmar, även om filerna distribuerades utanför Contoso.</span><span class="sxs-lookup"><span data-stu-id="8eb80-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="8eb80-112">Contoso [IT-personal](secure-teams-highly-regulated-data-scenario.md) använde ett team för starkt reglerade data för Project 2X och dessa steg.</span><span class="sxs-lookup"><span data-stu-id="8eb80-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="8eb80-113">Steg 1: Skapade ett privat team och låste den underliggande SharePoint-webbplatsen</span><span class="sxs-lookup"><span data-stu-id="8eb80-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="8eb80-114">För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för teamet har Contoso IT-administratörer konfigurerat de [rekommenderade SharePoint-åtkomstprinciperna](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8eb80-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="8eb80-115">Därefter skapade en Contoso IT-administratör ett nytt privat team som heter Project 2X och lade till användarkontona för Project 2X-personal som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="8eb80-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="8eb80-116">Därefter har de konfigurerat ytterligare behörighetsinställningar för webbplatsen för att förhindra att Project 2X delar åtkomst till webbplatsen och för att förhindra att andra begär åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8eb80-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="8eb80-117">Information om konfigurationen finns i [SharePoint-inställningar för ett starkt reglerat team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span><span class="sxs-lookup"><span data-stu-id="8eb80-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="8eb80-118">Steg 2: Konfigurerade en DLP-princip och den underliggande platsen för en bevarandeetikett</span><span class="sxs-lookup"><span data-stu-id="8eb80-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="8eb80-119">För det första tillämpade Contoso-administratörer den befintliga lagringsetiketten **highly Confidential** Office 365 på avsnittet **Dokument** på den underliggande SharePoint-webbplatsen i Project 2X-teamet.</span><span class="sxs-lookup"><span data-stu-id="8eb80-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="8eb80-120">Därefter skapade de en ny Office 365 DLP-princip med namnet **Project 2X** som:</span><span class="sxs-lookup"><span data-stu-id="8eb80-120">Next, they created a new Office 365 DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="8eb80-121">Använder lagringsetiketten Mycket konfidentiell Office 365.</span><span class="sxs-lookup"><span data-stu-id="8eb80-121">Uses the Highly Confidential Office 365 retention label.</span></span>
- <span data-ttu-id="8eb80-122">Blockerar användare när de försöker dela en fil i Project 2X-teamet utanför Contoso.</span><span class="sxs-lookup"><span data-stu-id="8eb80-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="8eb80-123">Information om konfigurationen [finns i Skydda filer i team med kvarhållningsetiketter och DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span><span class="sxs-lookup"><span data-stu-id="8eb80-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="8eb80-124">Steg 3: Skapade en känslighetsetikett för Office 365 för Project 2X-teamet</span><span class="sxs-lookup"><span data-stu-id="8eb80-124">Step 3: Created an Office 365 sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="8eb80-125">Contoso-administratörer skapade en ny Office 365-känslighetsetikett med namnet **Project 2X** som:</span><span class="sxs-lookup"><span data-stu-id="8eb80-125">Contoso admins created a new Office 365 sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="8eb80-126">Kräver kryptering.</span><span class="sxs-lookup"><span data-stu-id="8eb80-126">Requires encryption.</span></span>
- <span data-ttu-id="8eb80-127">Tillåter samredigeringsbehörigheter för gruppen Project 2X Office 365.</span><span class="sxs-lookup"><span data-stu-id="8eb80-127">Allows Co-Author permissions for the Project 2X Office 365 group.</span></span>

<span data-ttu-id="8eb80-128">Här är den resulterande konfigurationen av Project 2X-teamet.</span><span class="sxs-lookup"><span data-stu-id="8eb80-128">Here is the resulting configuration of the Project 2X team.</span></span>

![Den resulterande konfigurationen av Project 2X-teamet](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="8eb80-130">Filerna i avsnittet Dokument på den underliggande Project 2X SharePoint-webbplatsen skyddades av:</span><span class="sxs-lookup"><span data-stu-id="8eb80-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="8eb80-131">Webbplatsbehörigheterna, som endast tillåter åtkomst till medlemmar i gruppen Project 2X Office 365.</span><span class="sxs-lookup"><span data-stu-id="8eb80-131">The site permissions, which only allow access to members of the Project 2X Office 365 group.</span></span>
- <span data-ttu-id="8eb80-132">Etiketten Mycket konfidentiell lagring, som automatiskt tilldelas nya filer.</span><span class="sxs-lookup"><span data-stu-id="8eb80-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="8eb80-133">En DLP-princip som använder etiketten Mycket konfidentiell lagring och inställningar som blockerar filen från att delas med externa användare.</span><span class="sxs-lookup"><span data-stu-id="8eb80-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="8eb80-134">Etiketten för project 2x-känslighet med kryptering och behörigheter som färdas med filen om den flyttas eller kopieras från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8eb80-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="8eb80-135">Här är ett exempel på en fil som lagras på den underliggande Project 2X-platsen med den högreglerade retentionsetiketten och etiketten Project 2X-känslighet tilldelad.</span><span class="sxs-lookup"><span data-stu-id="8eb80-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![Ett exempel på en fil som lagras på den underliggande Project 2X-platsen](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="8eb80-137">Steg 4: Utbildade Project 2X-teammedlemmar</span><span class="sxs-lookup"><span data-stu-id="8eb80-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="8eb80-138">Contosos säkerhetspersonal utbildade Project 2X-teammedlemmarna i en obligatorisk kurs som klev igenom dem:</span><span class="sxs-lookup"><span data-stu-id="8eb80-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="8eb80-139">Så här öppnar du det nya Project 2X-teamet, använder möten och chattar och hur du samarbetar i gruppfiler.</span><span class="sxs-lookup"><span data-stu-id="8eb80-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="8eb80-140">Så här skapar du nya filer i teamet och laddar upp nya filer som skapats lokalt.</span><span class="sxs-lookup"><span data-stu-id="8eb80-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="8eb80-141">En demonstration av hur DLP-principen blockerar filer från att delas externt.</span><span class="sxs-lookup"><span data-stu-id="8eb80-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="8eb80-142">Så här märker du filer med känslighetsetiketten Project 2X.</span><span class="sxs-lookup"><span data-stu-id="8eb80-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="8eb80-143">En demonstration av hur Project 2X-etiketten skyddar en fil även när den lämnar teamet.</span><span class="sxs-lookup"><span data-stu-id="8eb80-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="8eb80-144">Slutresultatet blev en säker miljö där Project 2X-gruppmedlemmar samarbetade i en säker miljö för chattar, möten och filer.</span><span class="sxs-lookup"><span data-stu-id="8eb80-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="8eb80-145">I ett par instanser hämtade Project 2X-gruppmedlemmar filer som skyddas av Project 2X-etiketten till en lokal enhet för offlinearbete.</span><span class="sxs-lookup"><span data-stu-id="8eb80-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="8eb80-146">Men efter att ha uppmanats för autentiseringsuppgifter när de öppnade dem, insåg de sitt misstag och raderade dem.</span><span class="sxs-lookup"><span data-stu-id="8eb80-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="8eb80-147">På grund av samarbetsmiljön för Teams och säkerhetsfunktionerna i Microsoft 365 hölls informationen om Project 2X hemlig under projektets gång.</span><span class="sxs-lookup"><span data-stu-id="8eb80-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="8eb80-148">Contoso tillkännagav sina planer och håller på att rulla ut de nya produkterna och tjänsterna till glädje för sina kunder och investerare och förtret för sina konkurrenter.</span><span class="sxs-lookup"><span data-stu-id="8eb80-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="8eb80-149">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8eb80-149">Next step</span></span>

<span data-ttu-id="8eb80-150">[Distribuera](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8eb80-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="8eb80-151">Se även</span><span class="sxs-lookup"><span data-stu-id="8eb80-151">See also</span></span>

<span data-ttu-id="8eb80-152">[Produktivitetsbibliotek i Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="8eb80-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
