---
title: Isolerat team för ett hemligt projekt av Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
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
description: 'Sammanfattning: Hur Contoso använde en grupp med säkerhetsisolering för ett hemligt projekt för att utveckla en ny uppsättning produkter och tjänster.'
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029022"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="bbc0a-103">Isolerat team för ett hemligt projekt av Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="bbc0a-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="bbc0a-104">Efter en chef på plats beställde Contosos VD utvecklingen av en ny uppsättning produkter och tjänster som skulle kunna dubbla Contosos resultat under de kommande fem åren.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="bbc0a-105">Det topphemliga projektet att utveckla företagets, teknik- och marknadsplan kallades **Project 2X** och viktig personal i hela företaget har rekryteringts.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="bbc0a-106">Tidslinjerna för forskning och utveckling var knappa, vilket gjorde att samarbetet kunde vara effektivt och ge säkra möten, pågående konversationer och fillagring.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="bbc0a-107">De resulterande slutprodukterna för Project 2X var affärsplaner, produkt- och tekniska specifikationer samt marknadsföringsmaterial och scheman i form av Word, Excel och PowerPoint filer.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="bbc0a-108">På grund av sin känsliga natur var åtkomsten till dessa filer:</span><span class="sxs-lookup"><span data-stu-id="bbc0a-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="bbc0a-109">Begränsas till Project 2X-teammedlemmar och ledningsgruppen.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="bbc0a-110">Krypterad och skyddad med behörigheter att bara ge åtkomst till Project 2X-teammedlemmar och ledningsgruppen, även om filerna distribuerades utanför sina skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="bbc0a-111">Contosos IT-personal använde [ett team med säkerhetsisolering](secure-teams-security-isolation.md) för att Project 2X och de här stegen.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="bbc0a-112">Steg 1: Skapat ett privat team</span><span class="sxs-lookup"><span data-stu-id="bbc0a-112">Step 1: Created a private team</span></span>

<span data-ttu-id="bbc0a-113">För att skydda åtkomsten till teamets underliggande SharePoint-webbplats konfigurerade Contoso IT-administratörer den [rekommenderade SharePoint för åtkomstprinciper.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="bbc0a-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="bbc0a-114">En Contoso IT-administratör skapade sedan ett nytt privat team med namnet Project 2X och lade till användarkontona för Project 2X-personal som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="bbc0a-115">De har även konfigurerat teamet så att endast Project 2X-teamägare kan skapa privata kanaler.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="bbc0a-116">Konfigurationsinformationen finns i Skapa [ett privat team](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="bbc0a-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="bbc0a-117">Steg 2: Skapat en känslighetsetikett för Project 2X-teamet</span><span class="sxs-lookup"><span data-stu-id="bbc0a-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="bbc0a-118">Contoso-administratörer har skapat en ny känslighetsetikett **med namnet Project 2X som:**</span><span class="sxs-lookup"><span data-stu-id="bbc0a-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="bbc0a-119">Aktiverad kryptering.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-119">Enabled encryption.</span></span>
- <span data-ttu-id="bbc0a-120">Tillåten Co-Author behörigheter för gruppen Project 2X Microsoft 365 användare.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="bbc0a-121">Tillåtna visningsbehörigheter för ledningsgruppsgruppen.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="bbc0a-122">Blockerad åtkomst till ohanterade enheter.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="bbc0a-123">Filer i avsnittet **Dokument** på den underliggande webbplatsen Project 2X SharePoint skyddade av:</span><span class="sxs-lookup"><span data-stu-id="bbc0a-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="bbc0a-124">Webbplatsbehörigheter, som endast tillåter fullständiga behörigheter för medlemmar i gruppen Project 2X Microsoft 365, och läsa behörigheter till ledningsgruppsgruppen.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="bbc0a-125">Den Project känslighetsetikett för 2X, med kryptering och behörigheter som tillsammans med filen flyttas eller kopieras från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="bbc0a-126">Mer information om konfiguration finns i [Skapa en känslighetsetikett](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="bbc0a-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="bbc0a-127">Steg 3: Konfigurerade den underliggande SharePoint webbplatsen</span><span class="sxs-lookup"><span data-stu-id="bbc0a-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="bbc0a-128">För att skydda åtkomsten till teamets underliggande SharePoint-webbplats konfigurerade Contoso IT-administratörer den [rekommenderade SharePoint för åtkomstprinciper.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="bbc0a-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="bbc0a-129">Därefter har de konfigurerat ytterligare behörighetsinställningar för webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="bbc0a-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="bbc0a-130">För att Project 2X-gruppmedlemmar från att dela åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="bbc0a-131">Information om konfiguration finns i SharePoint [för ett team med säkerhetsisolering](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="bbc0a-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="bbc0a-132">För läsbehörigheter för ledningsgruppsgruppen.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="bbc0a-133">Därefter har de konfigurerat ytterligare behörighetsinställningar för webbplatsen för att förhindra Project 2X-gruppmedlemmar från att dela åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="bbc0a-134">När privata kanaler för Project 2X har skapats inaktiverade gruppägaren gästdelningen och ställer in standardlänken för delning till värdet **Specifika** personer.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="bbc0a-135">Här är den resulterande konfigurationen av en Project 2X-grupp med säkerhetsisolering.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![Den resulterande konfigurationen av 2X-Project 2X-gruppen](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="bbc0a-137">Steg 4: Utbildat Project 2X-teammedlemmar</span><span class="sxs-lookup"><span data-stu-id="bbc0a-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="bbc0a-138">Contoso-säkerhetspersonalen har utbildat Project 2X-teammedlemmar i en obligatorisk kurs som gått igenom dem:</span><span class="sxs-lookup"><span data-stu-id="bbc0a-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="bbc0a-139">Hur du får tillgång till det Project 2X-teamet, använder möten och chattar och hur du samarbetar i teamfiler.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="bbc0a-140">Så här skapar du nya filer i teamet och laddar upp nya filer som skapats lokalt.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="bbc0a-141">Så här etiketterar du filer Project med en känslighetsetikett som är 2X.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="bbc0a-142">En demonstration av hur en Project med 2X-etikett skyddar en fil även när den lämnar teamet.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="bbc0a-143">Resultatet var en säker miljö där 2X-Project samarbetade i en säker miljö för chattar, möten och filer.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="bbc0a-144">Här är ett exempel på en fil som lagras på den underliggande 2X Project-webbplatsen med känslighetsetiketten Project 2X tilldelat.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Ett exempel på en fil som lagras på den underliggande Project 2X-webbplatsen](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="bbc0a-146">I några fall laddade Project 2X-gruppmedlemmar ned filer skyddade av Project 2X-etiketten till en lokal enhet för offlinearbete.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="bbc0a-147">När de efter en uppmaning om att ange autentiseringsuppgifter när de öppnade dem insåg de sitt misstag och raderade dem.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="bbc0a-148">På grund av samarbetsmiljön i Teams och säkerhetsfunktionerna i Microsoft 365 har informationen i Project 2X varit hemlig under hela projektet.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="bbc0a-149">Contoso meddelade sina planer och är i processen med att lansera nya produkter och tjänster till glädjen från sina kunder och investerare och chagrin av sina konkurrenter.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="bbc0a-150">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="bbc0a-150">Next step</span></span>

<span data-ttu-id="bbc0a-151">[Distribuera ett team med säkerhetsisolering](secure-teams-security-isolation.md) i din organisation.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

