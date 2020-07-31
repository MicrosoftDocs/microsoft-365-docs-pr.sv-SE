---
title: Isolerat team för ett topphemligt projekt av Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Sammanfattning: Hur Contoso använde ett team med säkerhetsisolering för ett topphemligt projekt för att utveckla en ny uppsättning produkter och tjänster.'
ms.openlocfilehash: f7b38a7ef43cdb50b46f3e37f855f490dc32cfdf
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521631"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="988d5-103">Isolerat team för ett topphemligt projekt av Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="988d5-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="988d5-104">Efter en verkställande offsite, Contoso VD beställde utvecklingen av en ny svit av produkter och tjänster som kan fördubbla Contoso vinst under de kommande fem åren.</span><span class="sxs-lookup"><span data-stu-id="988d5-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="988d5-105">Det topphemliga projektet för att utveckla affärs-, ingenjörs- och marknadsplanen fick namnet **Project 2X** och nyckelpersonal i hela företaget rekryterades.</span><span class="sxs-lookup"><span data-stu-id="988d5-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="988d5-106">Tidslinjerna för forskning och utveckling var snäva, vilket innebar att samarbetet måste vara effektivt och ge säkra möten, pågående samtal och fillagring.</span><span class="sxs-lookup"><span data-stu-id="988d5-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="988d5-107">De resulterande slutprodukterna för Project 2X var affärsplaner, produkt- och teknikspecifikationer samt marknadsföringsmaterial och scheman i form av Word-, Excel- och PowerPoint-filer.</span><span class="sxs-lookup"><span data-stu-id="988d5-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="988d5-108">På grund av deras känsliga natur var tillgången till dessa filer:</span><span class="sxs-lookup"><span data-stu-id="988d5-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="988d5-109">Begränsad till Project 2X-gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="988d5-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="988d5-110">Krypterad och skyddad med behörighet att endast tillåta åtkomst till Project 2X-gruppmedlemmar, även om filerna distribuerades utanför sina säkra mappar.</span><span class="sxs-lookup"><span data-stu-id="988d5-110">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="988d5-111">Contoso IT-personal använde ett [team med säkerhetsisolering](secure-teams-security-isolation.md) för Project 2X och dessa steg.</span><span class="sxs-lookup"><span data-stu-id="988d5-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="988d5-112">Steg 1: Skapade ett privat team</span><span class="sxs-lookup"><span data-stu-id="988d5-112">Step 1: Created a private team</span></span>

<span data-ttu-id="988d5-113">För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för teamet konfigurerade Contoso IT-administratörer de [rekommenderade SharePoint-åtkomstprinciperna](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="988d5-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="988d5-114">Därefter skapade en Contoso IT-administratör ett nytt privat team med namnet Project 2X och lade till användarkontona för Project 2X-personal som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="988d5-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="988d5-115">Konfigurationsinformation finns i [Skapa ett privat team](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="988d5-115">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="988d5-116">Steg 2: Skapade en känslighetsetikett för Project 2X-teamet</span><span class="sxs-lookup"><span data-stu-id="988d5-116">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="988d5-117">Contoso-administratörer skapade en ny känslighetsetikett med namnet **Project 2X** som:</span><span class="sxs-lookup"><span data-stu-id="988d5-117">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="988d5-118">Kräver kryptering.</span><span class="sxs-lookup"><span data-stu-id="988d5-118">Requires encryption.</span></span>
- <span data-ttu-id="988d5-119">Tillåter samtidiga redigeringsbehörigheter för gruppen Project 2X Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="988d5-119">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="988d5-120">Filerna i avsnittet **Dokument** på den underliggande Project 2X SharePoint-webbplatsen skyddades av:</span><span class="sxs-lookup"><span data-stu-id="988d5-120">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="988d5-121">Webbplatsbehörigheterna, som endast ger åtkomst till medlemmar i gruppen Project 2X Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="988d5-121">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="988d5-122">Känslighetsetiketten För Project 2X, med kryptering och behörigheter som färdas med filen om den flyttas eller kopieras från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="988d5-122">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="988d5-123">Konfigurationsinformation finns i [Skapa en känslighetsetikett](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="988d5-123">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="988d5-124">Steg 3: Konfigurerade den underliggande SharePoint-webbplatsen</span><span class="sxs-lookup"><span data-stu-id="988d5-124">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="988d5-125">För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för teamet konfigurerade Contoso IT-administratörer de [rekommenderade SharePoint-åtkomstprinciperna](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="988d5-125">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="988d5-126">Därefter konfigurerade de ytterligare behörighetsinställningar för webbplatsen för att förhindra att Project 2X delar åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="988d5-126">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site.</span></span> <span data-ttu-id="988d5-127">Konfigurationsinformation finns i [SharePoint-inställningar för ett team med säkerhetsisolering](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="988d5-127">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>

<span data-ttu-id="988d5-128">Här är den resulterande konfigurationen av Project 2X-teamet.</span><span class="sxs-lookup"><span data-stu-id="988d5-128">Here is the resulting configuration of the Project 2X team.</span></span>

![Den resulterande konfigurationen av Project 2X-teamet](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="988d5-130">Steg 4: Utbildade Project 2X-gruppmedlemmar</span><span class="sxs-lookup"><span data-stu-id="988d5-130">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="988d5-131">Contoso säkerhetspersonal utbildade Project 2X-teammedlemmarna i en obligatorisk kurs som klev igenom dem:</span><span class="sxs-lookup"><span data-stu-id="988d5-131">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="988d5-132">Så här kommer du åt det nya Project 2X-teamet, använder möten och chattar och hur du samarbetar i gruppfiler.</span><span class="sxs-lookup"><span data-stu-id="988d5-132">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="988d5-133">Så här skapar du nya filer i teamet och laddar upp nya filer som skapats lokalt.</span><span class="sxs-lookup"><span data-stu-id="988d5-133">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="988d5-134">En demonstration av hur DLP-principen blockerar filer från att delas externt.</span><span class="sxs-lookup"><span data-stu-id="988d5-134">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="988d5-135">Så här märker du filer med känslighetsetiketten För Project 2X.</span><span class="sxs-lookup"><span data-stu-id="988d5-135">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="988d5-136">En demonstration av hur Project 2X-etiketten skyddar en fil även när den lämnar teamet.</span><span class="sxs-lookup"><span data-stu-id="988d5-136">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="988d5-137">Slutresultatet blev en säker miljö där Project 2X-gruppmedlemmar samarbetade i en säker miljö för chattar, möten och filer.</span><span class="sxs-lookup"><span data-stu-id="988d5-137">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="988d5-138">Här är ett exempel på en fil som lagras i den underliggande Project 2X-platsen med känslighetsetiketten Project 2X tilldelad.</span><span class="sxs-lookup"><span data-stu-id="988d5-138">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Ett exempel på en fil som lagras på den underliggande Project 2X-platsen](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="988d5-140">I ett par fall hämtade Project 2X-gruppmedlemmar filer som skyddas av Project 2X-etiketten till en lokal enhet för offlinearbete.</span><span class="sxs-lookup"><span data-stu-id="988d5-140">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="988d5-141">Men efter att ha uppmanats om autentiseringsuppgifter när de öppnades, insåg de sitt misstag och tog bort dem.</span><span class="sxs-lookup"><span data-stu-id="988d5-141">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="988d5-142">På grund av teamens samarbetsmiljö och säkerhetsfunktionerna i Microsoft 365 hölls detaljerna i Project 2X hemliga under hela projektet.</span><span class="sxs-lookup"><span data-stu-id="988d5-142">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="988d5-143">Contoso tillkännagav sina planer och håller på att rulla ut de nya produkterna och tjänsterna till glädje för sina kunder och investerare och förtret för sina konkurrenter.</span><span class="sxs-lookup"><span data-stu-id="988d5-143">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="988d5-144">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="988d5-144">Next step</span></span>

<span data-ttu-id="988d5-145">[Distribuera ett team med säkerhetsisolering](secure-teams-security-isolation.md) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="988d5-145">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

