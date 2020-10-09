---
title: Isolerat team för ett hemligt projekt av Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Sammanfattning: hur contoso använde ett team med säkerhets isolering för ett Top Secret för att utveckla en ny serie produkter och tjänster.'
ms.openlocfilehash: 16d10f5d6e5b5939172c02746c9324eb20b6987e
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399495"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="c1202-103">Isolerat team för ett hemligt projekt av Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="c1202-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="c1202-104">Efter en företags ledning beställde Contosos VD utvecklingen för en ny serie produkter och tjänster som kunde dubbelt så lite som Contosos vinst under de kommande fem åren.</span><span class="sxs-lookup"><span data-stu-id="c1202-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="c1202-105">Det översta och hemliga projektet för att utveckla företags-, teknik-och marknads plan har bearbetats till **Project 2x** och viktiga anställda i företaget har rekryterats.</span><span class="sxs-lookup"><span data-stu-id="c1202-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="c1202-106">Tids linjerna för forskning och utveckling var tätt avsedda att samarbetet måste vara effektivt och möjliggöra säkra möten, pågående konversationer och fil lagring.</span><span class="sxs-lookup"><span data-stu-id="c1202-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="c1202-107">De slutliga slut produkterna för Project 2X var företags abonnemang, produkt-och teknik specifikationer och marknadsförings material och schemalägger i form av Word-, Excel-och PowerPoint-filer.</span><span class="sxs-lookup"><span data-stu-id="c1202-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="c1202-108">Till följd av känsligheten var följande:</span><span class="sxs-lookup"><span data-stu-id="c1202-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="c1202-109">Begränsat till projekt som är dubbelt så grupp medlemmar och ledarskaps chef.</span><span class="sxs-lookup"><span data-stu-id="c1202-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="c1202-110">Krypterat och skyddat med behörigheter att endast tillåta åtkomst till grupp medlemmar i Project 2X och chefs ledarskap, även om filerna distribuerades utanför deras skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="c1202-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="c1202-111">Contoso IT-personal använde ett [team med säkerhets isolering](secure-teams-security-isolation.md) för Project 2x och de här stegen.</span><span class="sxs-lookup"><span data-stu-id="c1202-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="c1202-112">Steg 1: skapa ett privat team</span><span class="sxs-lookup"><span data-stu-id="c1202-112">Step 1: Created a private team</span></span>

<span data-ttu-id="c1202-113">För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för gruppen är det bara att contoso IT-administratörer konfigurerade de [rekommenderade åtkomst principerna för SharePoint](../security/office-365-security/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c1202-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="c1202-114">Sedan skapar en Contoso-administratör en ny privat grupp med Project 2X och La till användar kontona i Project 2X-personal som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="c1202-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="c1202-115">De har även konfigurerat gruppen så att bara Project 2X team-ägarna kan skapa privata kanaler.</span><span class="sxs-lookup"><span data-stu-id="c1202-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="c1202-116">Mer information finns i [skapa ett privat team](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="c1202-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="c1202-117">Steg 2: skapa en känslighets etikett för Project 2X-teamet</span><span class="sxs-lookup"><span data-stu-id="c1202-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="c1202-118">Contoso-administratörer har skapat en ny känslighets etikett med namnet **Project 2x** som:</span><span class="sxs-lookup"><span data-stu-id="c1202-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="c1202-119">Aktive rad kryptering.</span><span class="sxs-lookup"><span data-stu-id="c1202-119">Enabled encryption.</span></span>
- <span data-ttu-id="c1202-120">Tillåtna Co-Author behörigheter för Project 2X Microsoft 365-gruppen.</span><span class="sxs-lookup"><span data-stu-id="c1202-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="c1202-121">Tillåtna visnings behörigheter för gruppen chef.</span><span class="sxs-lookup"><span data-stu-id="c1202-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="c1202-122">Blockerad åtkomst till ohanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="c1202-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="c1202-123">Filer i avsnittet **dokument** på den underliggande Project 2x SharePoint-webbplatsen skyddas av:</span><span class="sxs-lookup"><span data-stu-id="c1202-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="c1202-124">Webbplats behörigheterna, som endast tillåter fullständig behörighet till medlemmar i projektet 2X Microsoft 365-gruppen och Läs behörigheter till chefens ledarskaps grupp.</span><span class="sxs-lookup"><span data-stu-id="c1202-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="c1202-125">Etiketten Project 2X känslighet med kryptering och behörigheter som följer med filen om den flyttas eller kopieras från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c1202-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="c1202-126">Information om konfiguration finns i [skapa en känslighets etikett](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="c1202-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="c1202-127">Steg 3: Konfigurera den underliggande SharePoint-webbplatsen</span><span class="sxs-lookup"><span data-stu-id="c1202-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="c1202-128">För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för gruppen är det bara att contoso IT-administratörer konfigurerade de [rekommenderade åtkomst principerna för SharePoint](../security/office-365-security/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c1202-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="c1202-129">Sedan har de konfigurerat ytterligare behörighets inställningar för webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="c1202-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="c1202-130">Om du inte vill att grupp medlemmar i Project 2X ska kunna dela åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c1202-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="c1202-131">Information om konfiguration finns i [SharePoint-inställningar för en grupp med säkerhets isolering](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="c1202-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="c1202-132">För Läs behörighet för gruppen chef.</span><span class="sxs-lookup"><span data-stu-id="c1202-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="c1202-133">Sedan har de konfigurerat ytterligare behörighets inställningar för webbplatsen för att förhindra att medlemmar i Project 2X kan dela åtkomsten till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c1202-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="c1202-134">Eftersom privata kanaler för Project 2X skapades inaktiverades gäst delningen av grupp ägaren och ange den som standard delnings länk till det **specifika** värdet.</span><span class="sxs-lookup"><span data-stu-id="c1202-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="c1202-135">Här är den resulterande konfigurationen för Project 2X-teamet med säkerhets isolering.</span><span class="sxs-lookup"><span data-stu-id="c1202-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![Den resulterande konfigurationen för Project 2X-teamet](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="c1202-137">Steg 4: utbildad Project 2X-grupp medlemmar</span><span class="sxs-lookup"><span data-stu-id="c1202-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="c1202-138">Contoso säkerhet bemannade projektets grupp medlemmar i en obligatorisk kurs som har passerat dem genom:</span><span class="sxs-lookup"><span data-stu-id="c1202-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="c1202-139">Hur du får till gång till det nya projektet 2X, använda möten och chattar och hur du samarbetar med gruppfiler.</span><span class="sxs-lookup"><span data-stu-id="c1202-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="c1202-140">Så här skapar du nya filer i teamet och laddar upp nya filer som skapats lokalt.</span><span class="sxs-lookup"><span data-stu-id="c1202-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="c1202-141">Så här etiketterar du filer med etiketten dubbel känslighet för Project.</span><span class="sxs-lookup"><span data-stu-id="c1202-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="c1202-142">En demonstration av hur Project-dubbel etikett skyddar en fil även när den lämnar gruppen.</span><span class="sxs-lookup"><span data-stu-id="c1202-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="c1202-143">Slut resultatet var en säker miljö där grupp medlemmarna i Project 2X samarbetar i en säker miljö för chattar, möten och filer.</span><span class="sxs-lookup"><span data-stu-id="c1202-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="c1202-144">Här är ett exempel på en fil som är lagrad i den underliggande Project 2X-webbplatsen med etiketten dubbel känslighet för Project.</span><span class="sxs-lookup"><span data-stu-id="c1202-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Ett exempel på en fil som lagras i den underliggande projektets dubbel webbplats](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="c1202-146">I ett par fall har Project 2X team medlemmar laddat ned filer som skyddas av Project 2X till en lokal enhet för offlinearbete.</span><span class="sxs-lookup"><span data-stu-id="c1202-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="c1202-147">Men efter att ha uppmanats att ange autentiseringsuppgifter när du öppnade dem konstaterade de misstaget och tagit bort dem.</span><span class="sxs-lookup"><span data-stu-id="c1202-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="c1202-148">På grund av samarbets miljön i Teams och säkerhetsfunktionerna i Microsoft 365 var informationen i Project 2X den hemliga under projektets giltighets tid.</span><span class="sxs-lookup"><span data-stu-id="c1202-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="c1202-149">Contoso meddelade sina abonnemang och är i färd med att lansera nya produkter och tjänster till passar av sina kunder och investerare och Chagrin.</span><span class="sxs-lookup"><span data-stu-id="c1202-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="c1202-150">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c1202-150">Next step</span></span>

<span data-ttu-id="c1202-151">[Distribuera en grupp med säkerhets isolering](secure-teams-security-isolation.md) i din organisation.</span><span class="sxs-lookup"><span data-stu-id="c1202-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

