---
title: Skicka innehållstyper till en navplats
description: Läs mer om att skicka innehållstyper till en navplats
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 89c03a70da364bd4b945debc64de02255dec15e1
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975721"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="a39d7-103">Skicka innehållstyper till en navplats</span><span class="sxs-lookup"><span data-stu-id="a39d7-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="a39d7-104">Om du vill göra viktiga innehållstyper mer kontinuerligt tillgängliga för SharePoint-bibliotek och -listor kan du skicka dem till de navplatser du väljer.</span><span class="sxs-lookup"><span data-stu-id="a39d7-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="a39d7-105">Om du trycker på innehållstyperna läggs de automatiskt till i nya listor och bibliotek som skapas på de webbplatser som är kopplade till navet och till alla nya webbplatser som läggs till navet.</span><span class="sxs-lookup"><span data-stu-id="a39d7-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="a39d7-106">För att den här funktionen ska fungera måste innehållstyperna som publiceras redan vara publicerade.</span><span class="sxs-lookup"><span data-stu-id="a39d7-106">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="a39d7-107">Att skicka innehållstyper till en hubb</span><span class="sxs-lookup"><span data-stu-id="a39d7-107">To push content types to hubs</span></span>

1. <span data-ttu-id="a39d7-108">Öppna **Innehållstjänster** i administrationscenter för SharePoint och välj sedan **Galleri med innehållstyper**.</span><span class="sxs-lookup"><span data-stu-id="a39d7-108">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="a39d7-109">Välj den innehållstyp som du vill skicka till hubben.</span><span class="sxs-lookup"><span data-stu-id="a39d7-109">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="a39d7-110">Välj **Redigera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="a39d7-110">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="a39d7-111">Välj **Välj navplatser**.</span><span class="sxs-lookup"><span data-stu-id="a39d7-111">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="a39d7-112">Välj de navplatser du vill använda och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="a39d7-112">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="a39d7-113">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a39d7-113">Choose **Save**.</span></span>

<span data-ttu-id="a39d7-114">När du skickar en innehållstyp till en befintlig hubb och dess befintliga kopplade webbplatser för första gången kan det ta upp till en timme från det att hubben eller tillhörande webbplatser besökts för inställningarna att uppdateras på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a39d7-114">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="a39d7-115">Alla nya associationer till hubben kräver inte detta utan där kommer inställningarna att återspeglas efter några minuter.</span><span class="sxs-lookup"><span data-stu-id="a39d7-115">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="a39d7-116">När inställningarna har uppdaterats blir innehållstypen med de här inställningarna tillgänglig på alla nyligen kopplade webbplatser med hubben på några minuter.</span><span class="sxs-lookup"><span data-stu-id="a39d7-116">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="a39d7-117">Sedan en ny lista eller ett nytt bibliotek skapas kommer innehållstypen automatiskt, efter att ha gjorts tillgänglig, att läggas till på ett par minuter.</span><span class="sxs-lookup"><span data-stu-id="a39d7-117">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="a39d7-118">En innehållstyp som skickas kommer bara att läggas till i ett dokumentbibliotek om den kommer direkt eller indirekt från dokumentets innehållstyp och en innehållstyp läggs endast till i en lista om den inte direkt eller indirekt kommer från dokumentets innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="a39d7-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="a39d7-119">Se även</span><span class="sxs-lookup"><span data-stu-id="a39d7-119">See also</span></span>
