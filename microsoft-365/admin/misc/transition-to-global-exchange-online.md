---
title: Uppdatera MX-posterna för att gå över till den globala Exchange Online tjänsten
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du går över från Microsoft Cloud Germany Exchange Online till den globala Exchange Online tjänsten
ms.openlocfilehash: 8de64e30205b07a0c20a8ae4f7cdedbf6cc6824f
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644861"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="ff353-103">Uppdatera MX-posterna för att gå över till den globala Exchange Online tjänsten</span><span class="sxs-lookup"><span data-stu-id="ff353-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="ff353-104">Logga in på [Microsoft 365 administrationsportal](https://admin.microsoft.com)och gå till **Inställningar**  >  **Domains**</span><span class="sxs-lookup"><span data-stu-id="ff353-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="ff353-105">Status visas till höger för varje domän.</span><span class="sxs-lookup"><span data-stu-id="ff353-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="ff353-106">Om organisationens domäner pekar på Microsoft Cloud Germany Exchange Online måste du uppdatera MX-posten.</span><span class="sxs-lookup"><span data-stu-id="ff353-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="ff353-107">Klicka på domänen och sedan på **DNS-fel som upptäckts, klicka här för att visa**.</span><span class="sxs-lookup"><span data-stu-id="ff353-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="ff353-108">På den här sidan finns instruktioner för hur du åtgärdar MX-posten.</span><span class="sxs-lookup"><span data-stu-id="ff353-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="ff353-109">Om din domäns registrator [använder Domain Anslut](../setup/add-domain.md#registrars-with-domain-connect)kan du klicka på "Åtgärda mina poster" högst upp.</span><span class="sxs-lookup"><span data-stu-id="ff353-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="ff353-110">Annars kan du följa länken i guiden och **följa de stegvisa instruktionerna för** din registrator.</span><span class="sxs-lookup"><span data-stu-id="ff353-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>