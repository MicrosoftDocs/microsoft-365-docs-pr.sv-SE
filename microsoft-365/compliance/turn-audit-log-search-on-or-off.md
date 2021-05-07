---
title: Aktivera och inaktivera granskningsloggsökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: Aktivera eller inaktivera funktionen granskningsloggsökning i Säkerhets- och efterlevnadscenter för & för att aktivera eller inaktivera administratörers möjlighet att söka i granskningsloggen.
ms.openlocfilehash: aecd1d47592b9a5e2f134b1d9db9ff203b815b18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162029"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="5c43c-103">Aktivera och inaktivera granskningsloggsökning</span><span class="sxs-lookup"><span data-stu-id="5c43c-103">Turn audit log search on or off</span></span>

<span data-ttu-id="5c43c-104">Granskningsloggning är aktiverat som standard för Microsoft 365 och Office 365 företag.</span><span class="sxs-lookup"><span data-stu-id="5c43c-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="5c43c-105">Detta omfattar organisationer med E3/G3 eller E5/G5-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="5c43c-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="5c43c-106">När granskningsloggsökning i efterlevnadscentret är aktiverat registreras användar- och administratörsaktivitet från organisationen i granskningsloggen och behålls i 90 dagar och upp till ett år beroende på vilken licens användarna har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="5c43c-106">When audit log search in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="5c43c-107">Det kan dock finnas skäl för organisationen att inte registrera och behålla granskningsloggdata.</span><span class="sxs-lookup"><span data-stu-id="5c43c-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="5c43c-108">I sådana fall kan en global administratör välja att inaktivera granskning i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c43c-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c43c-109">Om du inaktiverar granskningsloggsökning i Microsoft 365 kan du inte använda API:t för hanteringsaktivitet i Office 365 eller Azure Sentinel för att komma åt granskningsdata för organisationen.</span><span class="sxs-lookup"><span data-stu-id="5c43c-109">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="5c43c-110">Om du inaktiverar granskningsloggsökning genom att följa stegen i den här artikeln innebär det att inga resultat returneras när du söker i granskningsloggen med hjälp av Säkerhets- och efterlevnadscenter för & eller när du kör cmdleten **Search-UnifiedAuditLog** i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c43c-110">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="5c43c-111">Det innebär också att granskningsloggar inte är tillgängliga via API:t för Office 365 managementaktivitet eller Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="5c43c-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="5c43c-112">Innan du aktiverar eller inaktiverar granskningsloggsökning</span><span class="sxs-lookup"><span data-stu-id="5c43c-112">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="5c43c-113">Du måste ha tilldelats rollen Granskningsloggar i Exchange Online aktivera eller inaktivera granskningsloggsökning i Microsoft 365 organisation.</span><span class="sxs-lookup"><span data-stu-id="5c43c-113">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="5c43c-114">Som standard är den här rollen tilldelad rollgrupperna  Efterlevnadshantering och Organisationshantering på sidan Behörigheter Exchange administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="5c43c-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="5c43c-115">Globala administratörer i Microsoft 365 är medlemmar i rollgruppen Organisationshantering i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5c43c-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5c43c-116">Användarna måste ha tilldelats behörigheter i Exchange Online att aktivera eller inaktivera granskningsloggsökning.</span><span class="sxs-lookup"><span data-stu-id="5c43c-116">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="5c43c-117">Om du tilldelar användarna rollen  Granskningsloggar på sidan Behörigheter i Säkerhets- & efterlevnadscenter kan de inte aktivera eller inaktivera granskningsloggsökning.</span><span class="sxs-lookup"><span data-stu-id="5c43c-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="5c43c-118">Det beror på att den underliggande cmdleten är en Exchange Online PowerShell-cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5c43c-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 
    
- <span data-ttu-id="5c43c-119">Stegvisa instruktioner för hur du söker i granskningsloggen finns i Söka i [granskningsloggen i Säkerhets- & Efterlevnadscenter.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="5c43c-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="5c43c-120">Mer information om API för hanteringsaktivitet Microsoft 365 finns i Komma [igång Microsoft 365 Management API:er.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="5c43c-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="5c43c-121">Du kan kontrollera att granskningsloggsökning är aktiverat genom att köra följande kommando Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5c43c-121">To verify that audit log search is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="5c43c-122">Värdet för egenskapen  `True`  _UnifiedAuditLogIngestionEnabled_ anger att granskningsloggsökning är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="5c43c-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned on.</span></span> 
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="5c43c-123">Aktivera granskningsloggsökning</span><span class="sxs-lookup"><span data-stu-id="5c43c-123">Turn on audit log search</span></span>

<span data-ttu-id="5c43c-124">Om granskningsloggsökning inte är aktiverat för organisationen kan du aktivera den i efterlevnadscentret eller med hjälp av Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c43c-124">If audit log search is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="5c43c-125">Det kan ta flera timmar efter att du har aktiverar granskningsloggsökning innan du kan returnera resultat när du söker i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="5c43c-125">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="5c43c-126">Använda efterlevnadscenter för att aktivera granskningsloggsökning</span><span class="sxs-lookup"><span data-stu-id="5c43c-126">Use the compliance center to turn on audit log search</span></span>

1. <span data-ttu-id="5c43c-127">[Gå till efterlevnadscentret](https://protection.office.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="5c43c-127">[Go to the compliance center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="5c43c-128">Gå till Sök granskningsloggsökning **i**  >  **efterlevnadscentret.**</span><span class="sxs-lookup"><span data-stu-id="5c43c-128">In the compliance center, go to **Search** > **Audit log search**.</span></span>

   <span data-ttu-id="5c43c-129">Om granskningsloggsökning inte är aktiverat för organisationen visas en banderoll som säger att granskning måste aktiveras för att registrera användar- och administratörsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="5c43c-129">If audit log search is not turned on for your organization, a banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="5c43c-130">Klicka **på Aktivera granskning.**</span><span class="sxs-lookup"><span data-stu-id="5c43c-130">Click **Turn on auditing**.</span></span>

    ![Klicka på Aktivera granskning](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="5c43c-132">Banderollen uppdateras för att säga att granskningsloggen förbereds och att du kan söka efter användar- och administratörsaktivitet om några timmar.</span><span class="sxs-lookup"><span data-stu-id="5c43c-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="5c43c-133">Använda PowerShell för att aktivera granskningsloggsökning</span><span class="sxs-lookup"><span data-stu-id="5c43c-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="5c43c-134">Anslut till Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c43c-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="5c43c-135">Kör följande PowerShell-kommando för att aktivera granskningsloggsökning i Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c43c-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="5c43c-136">Ett meddelande visas om att det kan ta upp till 60 minuter innan ändringen verkställs.</span><span class="sxs-lookup"><span data-stu-id="5c43c-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="5c43c-137">Inaktivera granskningsloggsökning</span><span class="sxs-lookup"><span data-stu-id="5c43c-137">Turn off audit log search</span></span>

<span data-ttu-id="5c43c-138">Du måste använda Exchange Online PowerShell för att inaktivera granskningsloggsökning.</span><span class="sxs-lookup"><span data-stu-id="5c43c-138">You have to use Exchange Online PowerShell to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="5c43c-139">Anslut till Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c43c-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="5c43c-140">Kör följande PowerShell-kommando för att inaktivera granskningsloggsökning.</span><span class="sxs-lookup"><span data-stu-id="5c43c-140">Run the following PowerShell command to turn off audit log search.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="5c43c-141">Kontrollera efter ett tag att granskningsloggsökning är inaktiverat (inaktiverat).</span><span class="sxs-lookup"><span data-stu-id="5c43c-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="5c43c-142">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="5c43c-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="5c43c-143">I Exchange Online PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="5c43c-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="5c43c-144">Värdet för egenskapen  `False`  _UnifiedAuditLogIngestionEnabled_ anger att granskningsloggsökning är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="5c43c-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="5c43c-145">Gå till [Sök i granskningsloggsökning](https://protection.office.com)i  \> **efterlevnadscentret.**</span><span class="sxs-lookup"><span data-stu-id="5c43c-145">In the [compliance center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="5c43c-146">En banderoll visas om att granskning måste aktiveras för att kunna registrera användar- och administratörsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="5c43c-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>