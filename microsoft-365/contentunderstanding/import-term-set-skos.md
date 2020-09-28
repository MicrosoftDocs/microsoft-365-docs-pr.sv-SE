---
title: Importera en term uppsättning med ett SKOSt format
description: Lär dig hur du importerar en term uppsättning med ett SKOSt format
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296234"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="bdf92-103">Importera en term uppsättning med ett SKOSt format</span><span class="sxs-lookup"><span data-stu-id="bdf92-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="bdf92-104">Du kan importera en term uppsättning med ett SKOSt format.</span><span class="sxs-lookup"><span data-stu-id="bdf92-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="bdf92-105">Mer information om formatet finns i [SharePoint-taxonomi för SKOS format](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="bdf92-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="bdf92-106">Vi rekommenderar att du sparar dina import filer på färre än 20 000 villkor.</span><span class="sxs-lookup"><span data-stu-id="bdf92-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="bdf92-107">Större filer kan öka tiden för validering och import.</span><span class="sxs-lookup"><span data-stu-id="bdf92-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="bdf92-108">Expandera **innehålls tjänster**i administrations centret för SharePoint och klicka sedan på **term lagrings plats**.</span><span class="sxs-lookup"><span data-stu-id="bdf92-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="bdf92-109">Välj den term grupp där du vill importera term uppsättningen.</span><span class="sxs-lookup"><span data-stu-id="bdf92-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="bdf92-110">Klicka på **Importera term uppsättning**i kommando fältet.</span><span class="sxs-lookup"><span data-stu-id="bdf92-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="bdf92-111">Om du vill ladda ned en exempel fil som du vill använda som mall klickar du på **Sample-metadata. TTL** för att hämta en exempel fil som använder det SKOSbaserade formatet.</span><span class="sxs-lookup"><span data-stu-id="bdf92-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="bdf92-112">Skapa import filen som innehåller term uppsättningarna & villkor som du vill importera.</span><span class="sxs-lookup"><span data-stu-id="bdf92-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="bdf92-113">Under **fil format**väljer du **SKOS (\*. TTL)**.</span><span class="sxs-lookup"><span data-stu-id="bdf92-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="bdf92-114">Klicka på **Bläddra** och navigera till och Lägg till en import fil.</span><span class="sxs-lookup"><span data-stu-id="bdf92-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="bdf92-115">Klicka på **Importera**.</span><span class="sxs-lookup"><span data-stu-id="bdf92-115">Click **Import**.</span></span> <span data-ttu-id="bdf92-116">Stäng inte panelen förrän importen är klar.</span><span class="sxs-lookup"><span data-stu-id="bdf92-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="bdf92-117">När filen importeras visas ett meddelande om att det är klart och term lagrings platsen uppdateras och du kan navigera till de nya term uppsättningarna.</span><span class="sxs-lookup"><span data-stu-id="bdf92-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdf92-118">Se även</span><span class="sxs-lookup"><span data-stu-id="bdf92-118">See also</span></span>

[<span data-ttu-id="bdf92-119">Introduktion till hanterade metadata</span><span class="sxs-lookup"><span data-stu-id="bdf92-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="bdf92-120">Översikt över dokument förståelse</span><span class="sxs-lookup"><span data-stu-id="bdf92-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="bdf92-121">Importera term uppsättningar (webbplats nivå)</span><span class="sxs-lookup"><span data-stu-id="bdf92-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)