---
title: SharePoint-webbplats för mycket konfidentiella digitala tillgångar i Contoso Corporation
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
description: 'Sammanfattning: Hur Contoso implementerade en SharePoint-webbplats för starkt reglerade data för enklare samarbete mellan sina forskargrupper.'
ms.openlocfilehash: a1ffb336e85eb6eb850b53ed14adf947b56642cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807628"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="2997c-103">SharePoint-webbplats för mycket konfidentiella digitala tillgångar i Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="2997c-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

<span data-ttu-id="2997c-104">Contosos mest värdefulla tillgångar är dess immateriella rättigheter i form av affärshemligheter, såsom egenutvecklade tillverkningstekniker, och designspecifikationer för produkter som är under utveckling.</span><span class="sxs-lookup"><span data-stu-id="2997c-104">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="2997c-105">Dessa tillgångar var i digital form, ursprungligen lagras som filer på en SharePoint Server 2016 webbplats.</span><span class="sxs-lookup"><span data-stu-id="2997c-105">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="2997c-106">När Contoso distribuerade Microsoft 365 Enterprise ville de överlåta sina lokala digitala tillgångar till molnet för enklare åtkomst och mer öppet samarbete mellan forskargrupper i Paris, Moskva, New York, Peking och Bangalore.</span><span class="sxs-lookup"><span data-stu-id="2997c-106">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="2997c-107">På grund av sin känsliga natur måste dock tillgången till dessa filer vara:</span><span class="sxs-lookup"><span data-stu-id="2997c-107">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="2997c-108">Begränsad till uppsättningen personer som är tillåtna tillgång till dem.</span><span class="sxs-lookup"><span data-stu-id="2997c-108">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="2997c-109">Skyddad med en DLP-princip (Data Loss Prevention) för att förhindra att användare distribuerar dem utanför webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2997c-109">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="2997c-110">Krypterad och skyddad med behörigheter för att förhindra att obehöriga användare kommer åt deras innehåll, även om de distribueras utanför webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2997c-110">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="2997c-111">Säkerhets- och SharePoint-administratörer på Contosos IT-avdelning har beslutat att använda en [SharePoint-webbplats för starkt reglerade data](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="2997c-111">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="2997c-112">Contoso använde dessa steg för att skapa och säkra en SharePoint-gruppwebbplatser för sina forskargrupper.</span><span class="sxs-lookup"><span data-stu-id="2997c-112">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="2997c-113">Steg 1: Skapade en privat SharePoint-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="2997c-113">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="2997c-114">För att skydda åtkomsten till SharePoint-webbplatsen konfigurerade Contoso IT de [rekommenderade SharePoint-åtkomstprinciperna](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2997c-114">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="2997c-115">Därefter sammanställt Contoso IT-administratörer en lista över användarkonton för forskarna i deras Kontor i Paris, Moskva, New York, Peking och Bangalore.</span><span class="sxs-lookup"><span data-stu-id="2997c-115">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="2997c-116">Därefter skapade en Contoso IT-administratör en ny privat teamwebbplats med namnet **Research** och lade till alla användarkonton för sina forskare.</span><span class="sxs-lookup"><span data-stu-id="2997c-116">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="2997c-117">Sedan konfigurerade de ytterligare behörighetsinställningar för webbplatsen för att förhindra att forskare delar åtkomst till webbplatsen och för att förhindra att icke-forskare begär åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2997c-117">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="2997c-118">Steg 2: Konfigurerade platsen för en restriktiv DLP-princip</span><span class="sxs-lookup"><span data-stu-id="2997c-118">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="2997c-119">Först tillämpade Contoso-administratörer den befintliga lagringsetiketten **Highly Confidential** Office 365 på mappen Dokument på **forskningswebbplatsen.**</span><span class="sxs-lookup"><span data-stu-id="2997c-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="2997c-120">Därefter skapade de en ny DLP-princip för Office 365 med namnet **Forskning** som:</span><span class="sxs-lookup"><span data-stu-id="2997c-120">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="2997c-121">Använder lagringsetiketten **Mycket konfidentiell** Office 365.</span><span class="sxs-lookup"><span data-stu-id="2997c-121">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="2997c-122">Blockerar användare när de försöker dela en digital tillgång på **forskningswebbplatsen** utanför Contoso.</span><span class="sxs-lookup"><span data-stu-id="2997c-122">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="2997c-123">Information om konfigurationen finns i [Skydda SharePoint-filer med kvarhållningsetiketter och DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="2997c-123">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="2997c-124">Steg 3: Skapade en underetikett för Office 365-känslighet för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="2997c-124">Step 3: Created an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="2997c-125">Contoso-administratörer skapade en ny underetikett med Office 365-känslighet med namnet **Forskargrupper** för etiketten **Mycket konfidentiellt** som:</span><span class="sxs-lookup"><span data-stu-id="2997c-125">Contoso admins created a new Office 365 sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="2997c-126">Kräver kryptering.</span><span class="sxs-lookup"><span data-stu-id="2997c-126">Requires encryption.</span></span>
- <span data-ttu-id="2997c-127">Tillåter behörigheter för samtidig redigering för **gruppen Research** Office 365</span><span class="sxs-lookup"><span data-stu-id="2997c-127">Allows Co-Author permissions for the **Research** Office 365 group</span></span>
- <span data-ttu-id="2997c-128">Gäller **för gruppen Research** Office 365</span><span class="sxs-lookup"><span data-stu-id="2997c-128">Applies to the **Research** Office 365 group</span></span>

<span data-ttu-id="2997c-129">Här är den resulterande konfigurationen av **forskningsgruppens** webbplats för mycket konfidentiella tillgångar.</span><span class="sxs-lookup"><span data-stu-id="2997c-129">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![Den resulterande konfigurationen av forskningsgruppens webbplats för mycket konfidentiella tillgångar](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="2997c-131">Filer i mappar på **forskningswebbplatsen** skyddas av:</span><span class="sxs-lookup"><span data-stu-id="2997c-131">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="2997c-132">Webbplatsbehörigheterna, som endast tillåter åtkomst till medlemmar i gruppen **Research** Office 365.</span><span class="sxs-lookup"><span data-stu-id="2997c-132">The site permissions, which only allow access to members of the **Research** Office 365 group.</span></span>
- <span data-ttu-id="2997c-133">**Policyn För DLP för forskning,** som använder etiketten **Mycket konfidentiell** lagring och inställningar som förhindrar att filen delas med externa användare.</span><span class="sxs-lookup"><span data-stu-id="2997c-133">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="2997c-134">**Underetiketten För forskarkänslighet,** med kryptering och behörigheter som färdas med filen om den flyttas eller kopieras från **forskningswebbplatsen.**</span><span class="sxs-lookup"><span data-stu-id="2997c-134">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="2997c-135">Här är ett exempel på en fil som lagras på **forskningswebbplatsen** med underetiketten **Research Teams** känslighet tilldelad.</span><span class="sxs-lookup"><span data-stu-id="2997c-135">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![Den resulterande konfigurationen av forskningsgruppens webbplats för mycket konfidentiella tillgångar](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="2997c-137">Steg 4: Migrerade lokala SharePoint-forskningsdata</span><span class="sxs-lookup"><span data-stu-id="2997c-137">Step 4: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="2997c-138">Contoso-administratörer flyttade alla lokala forskningsfiler på den lokala SharePoint Server 2016-webbplatsen till mappar på den nya **Research** SharePoint-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2997c-138">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-5-trained-their-researchers"></a><span data-ttu-id="2997c-139">Steg 5: Utbildade sina forskare</span><span class="sxs-lookup"><span data-stu-id="2997c-139">Step 5: Trained their researchers</span></span>

<span data-ttu-id="2997c-140">Contosos säkerhetspersonal utbildade medlemmarna i **research** office 365-gruppen i en obligatorisk kurs som gick igenom dem:</span><span class="sxs-lookup"><span data-stu-id="2997c-140">Contoso security staff trained the members of the **Research** Office 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="2997c-141">Hur man kommer åt den nya **forskningswebbplatsen** och dess befintliga filer.</span><span class="sxs-lookup"><span data-stu-id="2997c-141">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="2997c-142">Så här skapar du nya filer på webbplatsen och laddar upp nya filer som lagras lokalt.</span><span class="sxs-lookup"><span data-stu-id="2997c-142">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="2997c-143">En demonstration av hur **Research** DLP-principen blockerar filer från att delas externt.</span><span class="sxs-lookup"><span data-stu-id="2997c-143">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="2997c-144">Så här märker du filer med **underetiketten Forskningsteams** känslighet.</span><span class="sxs-lookup"><span data-stu-id="2997c-144">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="2997c-145">En demonstration av hur **underetiketten research teams** skyddar en fil även när den läcker ut från platsen.</span><span class="sxs-lookup"><span data-stu-id="2997c-145">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="2997c-146">Slutresultatet är en säker miljö där forskarna kan samarbeta över Contoso i en säker miljö på filer som innehåller forskningsinformation.</span><span class="sxs-lookup"><span data-stu-id="2997c-146">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="2997c-147">Om ett forskningsdokument med underetiketten **Forskargrupper** lämnar **forskningswebbplatsen** krypteras och är det endast tillgängligt för medlemmar i gruppen **Research** Office 365 med giltiga användarkonton.</span><span class="sxs-lookup"><span data-stu-id="2997c-147">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Office 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="2997c-148">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2997c-148">Next step</span></span>

<span data-ttu-id="2997c-149">[Distribuera](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise i organisationen.</span><span class="sxs-lookup"><span data-stu-id="2997c-149">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="2997c-150">Se även</span><span class="sxs-lookup"><span data-stu-id="2997c-150">See also</span></span>

<span data-ttu-id="2997c-151">[Produktivitetsbibliotek i Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="2997c-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
