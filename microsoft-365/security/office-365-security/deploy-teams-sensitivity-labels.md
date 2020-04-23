---
title: Skydda filer i team med känslighetsetiketter
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
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Sammanfattning: Använd känslighetsetiketter för att skydda filer i team med höga krav på konfidentialitet.'
ms.openlocfilehash: c36daef7f28ad8bd3306fd7f3f7f1558a3594e68
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637622"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a><span data-ttu-id="10e82-103">Skydda filer i team med känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="10e82-103">Protect files in teams with sensitivity labels</span></span>


<span data-ttu-id="10e82-104">Till skillnad från en känslighetsetikett för strikt reglerade data som alla kan tillämpa på valfri fil behöver ett team med höga konfidentialitetskrav en egen etikett eller underetikett så att tilldelade filer:</span><span class="sxs-lookup"><span data-stu-id="10e82-104">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a highly confidential team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="10e82-105">Krypteras individuellt.</span><span class="sxs-lookup"><span data-stu-id="10e82-105">Are individually encrypted.</span></span>
- <span data-ttu-id="10e82-106">Innehåller anpassade behörigheter så att bara medlemmar i teamet kan öppna dem.</span><span class="sxs-lookup"><span data-stu-id="10e82-106">Contain custom permissions so that only members of the team can open it.</span></span>

<span data-ttu-id="10e82-107">För att åstadkomma den här extra säkerhetsnivån för filer i den underliggande SharePoint-webbplatsen för ett team måste du konfigurera en anpassad känslighetsetikett som antingen är en egen etikett eller en underetikett för den allmänna etiketten för strikt reglerade data.</span><span class="sxs-lookup"><span data-stu-id="10e82-107">To accomplish this additional level of security for files stored in the underlying SharePoint site of a team, you must configure a customized sensitivity label that is either its own label or a sublabel of the general label for highly regulated data.</span></span> <span data-ttu-id="10e82-108">Bara teammedlemmarna kommer att se den anpassade etiketten eller underetiketten i sin lista med etiketter.</span><span class="sxs-lookup"><span data-stu-id="10e82-108">Only team members will see the customized label or sublabel in their list of labels.</span></span>

<span data-ttu-id="10e82-109">Använd en känslighetsetikett när du behöver ett litet antal etiketter får både global användning och enskilda privata team.</span><span class="sxs-lookup"><span data-stu-id="10e82-109">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> 

<span data-ttu-id="10e82-110">Använd en underetikett för känslighet när du har ett stort antal etiketter eller vill ordna etiketter för team med höga konfidentialitetskrav under strikt reglerade-etiketten.</span><span class="sxs-lookup"><span data-stu-id="10e82-110">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for highly confidential teams under the highly regulated label.</span></span>

<span data-ttu-id="10e82-111">Använd [de här instruktionerna](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) till att konfigurera en separat etikett eller en underetikett med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="10e82-111">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="10e82-112">Namnet på etiketten eller underetiketten innehåller teamets namn</span><span class="sxs-lookup"><span data-stu-id="10e82-112">The name of the label or sublabel contains the name of the team</span></span>
- <span data-ttu-id="10e82-113">Kryptering är aktiverat</span><span class="sxs-lookup"><span data-stu-id="10e82-113">Encryption is enabled</span></span>
- <span data-ttu-id="10e82-114">Microsoft 365-gruppen för teamet har medförfattarbehörighet</span><span class="sxs-lookup"><span data-stu-id="10e82-114">The Microsoft 365 group for the team has Co-Author permissions</span></span>

<span data-ttu-id="10e82-115">När den nya etiketten eller underetiketten har skapats kan du publicera den för dina användare, som sedan kan tillämpa den på filer, antingen lokalt innan de laddas upp till teamet eller senare när filen lagras i teamet.</span><span class="sxs-lookup"><span data-stu-id="10e82-115">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>

<span data-ttu-id="10e82-116">Här är konfigurationen för teamet med höga konfidentialitetskrav som använder känslighetsetiketter för filkryptering och behörigheter.</span><span class="sxs-lookup"><span data-stu-id="10e82-116">Here is the configuration of the highly confidential team that uses sensitivity labels for file encryption and permissions.</span></span>

![Skydd på baslinjenivå för ett offentligt team.](../../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a><span data-ttu-id="10e82-118">Se även</span><span class="sxs-lookup"><span data-stu-id="10e82-118">See Also</span></span>

[<span data-ttu-id="10e82-119">Skydda filer i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10e82-119">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="10e82-120">Införande av moln- och hybridlösningar</span><span class="sxs-lookup"><span data-stu-id="10e82-120">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
