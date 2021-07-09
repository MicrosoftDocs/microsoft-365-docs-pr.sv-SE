---
title: Aktivera eller inaktivera granskningar
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
description: Så här aktiverar eller inaktiverar du funktionen Granskningsloggsökning i Microsoft 365 Efterlevnadscenter för att aktivera eller inaktivera administratörs möjlighet att söka i granskningsloggen.
ms.openlocfilehash: dd39b883036ce6060aef71c6a927c03f391d827f
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341502"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="f6d72-103">Aktivera eller inaktivera granskningar</span><span class="sxs-lookup"><span data-stu-id="f6d72-103">Turn auditing on or off</span></span>

<span data-ttu-id="f6d72-104">Granskningsloggning är som standard aktiverat för Microsoft 365 och Office 365 Enterprise-organisationer.</span><span class="sxs-lookup"><span data-stu-id="f6d72-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="f6d72-105">När granskning i Microsoft 365 Efterlevnadscenter är aktiverad registreras användar- och administratörsaktiviteten från organisationen i granskningsloggen och behålls i 90 dagar och upp till ett år beroende på vilken licens som tilldelats användarna.</span><span class="sxs-lookup"><span data-stu-id="f6d72-105">When auditing in the Microsoft 365 compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="f6d72-106">Det kan dock finnas skäl för organisationen att inte registrera och behålla granskningsloggdata.</span><span class="sxs-lookup"><span data-stu-id="f6d72-106">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="f6d72-107">I sådana fall kan en global administratör välja att inaktivera granskning i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6d72-107">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

<span data-ttu-id="f6d72-108">När du inställningar för Microsoft 365 eller Office 365 organisation kan du kontrollera organisationens granskningsstatus.</span><span class="sxs-lookup"><span data-stu-id="f6d72-108">When setting up a new Microsoft 365 or Office 365 organization, you can verify the auditing status for your organization.</span></span> <span data-ttu-id="f6d72-109">Anvisningar finns i avsnittet [Kontrollera organisationens granskningsstatus i](#verify-the-auditing-status-for-your-organization) den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f6d72-109">For instructions, see the [Verify the auditing status for your organization](#verify-the-auditing-status-for-your-organization) section in this article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6d72-110">Om du inaktiverar granskning i Microsoft 365 kan du inte använda API:t för Office 365 hanteringsaktivitet eller Azure Sentinel för att komma åt granskningsdata för organisationen.</span><span class="sxs-lookup"><span data-stu-id="f6d72-110">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="f6d72-111">Om du inaktiverar granskning genom att följa stegen i den här artikeln innebär det att inga resultat returneras när du söker i granskningsloggen med hjälp av Microsoft 365 Efterlevnadscenter eller när du kör cmdleten **Search-UnifiedAuditLog** i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6d72-111">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Microsoft 365 compliance center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="f6d72-112">Det innebär också att granskningsloggar inte är tillgängliga via API:t för Office 365 managementaktivitet eller Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="f6d72-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="f6d72-113">Innan du aktiverar eller inaktiverar granskning</span><span class="sxs-lookup"><span data-stu-id="f6d72-113">Before you turn auditing on or off</span></span>

- <span data-ttu-id="f6d72-114">Du måste ha tilldelats rollen Granskningsloggar i Exchange Online att aktivera eller inaktivera granskning i Microsoft 365 organisation.</span><span class="sxs-lookup"><span data-stu-id="f6d72-114">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="f6d72-115">Som standard är den här rollen tilldelad rollgrupperna  Efterlevnadshantering och Organisationshantering på sidan Behörigheter Exchange administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="f6d72-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="f6d72-116">Globala administratörer i Microsoft 365 är medlemmar i rollgruppen Organisationshantering i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f6d72-116">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6d72-117">Användare måste ha tilldelats behörigheter i Exchange Online att aktivera eller inaktivera granskning.</span><span class="sxs-lookup"><span data-stu-id="f6d72-117">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="f6d72-118">Om du tilldelar användarna rollen  Granskningsloggar på sidan Behörigheter i Microsoft 365 Efterlevnadscenter kan de inte aktivera eller inaktivera granskning.</span><span class="sxs-lookup"><span data-stu-id="f6d72-118">If you assign users the Audit Logs role on the **Permissions** page in the Microsoft 365 compliance center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="f6d72-119">Det beror på att den underliggande cmdleten är en Exchange Online PowerShell-cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f6d72-119">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span>

- <span data-ttu-id="f6d72-120">Stegvisa instruktioner för hur du söker i granskningsloggen finns [i Söka i granskningsloggen.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="f6d72-120">For step-by-step instructions on searching the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="f6d72-121">Mer information om API för hanteringsaktivitet Microsoft 365 finns i Komma [igång Microsoft 365 Management API:er.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="f6d72-121">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="verify-the-auditing-status-for-your-organization"></a><span data-ttu-id="f6d72-122">Kontrollera organisationens granskningsstatus</span><span class="sxs-lookup"><span data-stu-id="f6d72-122">Verify the auditing status for your organization</span></span>

<span data-ttu-id="f6d72-123">Du kan kontrollera att granskning är aktiverad för organisationen genom att köra följande kommando i [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="f6d72-123">To verify that auditing is turned on for your organization, you can run the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

<span data-ttu-id="f6d72-124">Värdet för `True` egenskapen  _UnifiedAuditLogIngestionEnabled_ anger att granskning är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="f6d72-124">A value of `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> <span data-ttu-id="f6d72-125">Värdet för `False` anger att granskning inte är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="f6d72-125">A value of `False` indicates that auditing is not turned on.</span></span>

## <a name="turn-on-auditing"></a><span data-ttu-id="f6d72-126">Aktivera granskning</span><span class="sxs-lookup"><span data-stu-id="f6d72-126">Turn on auditing</span></span>

<span data-ttu-id="f6d72-127">Om granskning inte är aktiverat för organisationen kan du aktivera den i Microsoft 365 Efterlevnadscenter eller med hjälp Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6d72-127">If auditing is not turned on for your organization, you can turn it on in the Microsoft 365 compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="f6d72-128">Det kan ta flera timmar efter att du har aktiverar granskning innan du kan returnera resultat när du söker i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="f6d72-128">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="f6d72-129">Aktivera granskning med hjälp av efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="f6d72-129">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="f6d72-130">Gå till <https://compliance.microsoft.com> och logga in.</span><span class="sxs-lookup"><span data-stu-id="f6d72-130">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="f6d72-131">Klicka på Granska i det vänstra Microsoft 365 Efterlevnadscenter på **fliken Granska.**</span><span class="sxs-lookup"><span data-stu-id="f6d72-131">In the left navigation pane of the Microsoft 365 compliance center, click **Audit**.</span></span>

   <span data-ttu-id="f6d72-132">Om granskning inte är aktiverat för organisationen visas en banderoll där du uppmanas att börja spela in användar- och administratörsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="f6d72-132">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![Banderoll på granskningssida](../media/AuditingBanner.png)

3. <span data-ttu-id="f6d72-134">Klicka på **banderollen Starta inspelning av användar- och administratörsaktivitet.**</span><span class="sxs-lookup"><span data-stu-id="f6d72-134">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="f6d72-135">Det kan ta upp till 60 minuter innan ändringen verkställs.</span><span class="sxs-lookup"><span data-stu-id="f6d72-135">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="f6d72-136">Aktivera granskning med PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6d72-136">Use PowerShell to turn on auditing</span></span>

1. <span data-ttu-id="f6d72-137">[Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6d72-137">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f6d72-138">Kör följande PowerShell-kommando för att aktivera granskning.</span><span class="sxs-lookup"><span data-stu-id="f6d72-138">Run the following PowerShell command to turn on auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="f6d72-139">Ett meddelande visas om att det kan ta upp till 60 minuter innan ändringen verkställs.</span><span class="sxs-lookup"><span data-stu-id="f6d72-139">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="f6d72-140">Inaktivera granskning</span><span class="sxs-lookup"><span data-stu-id="f6d72-140">Turn off auditing</span></span>

<span data-ttu-id="f6d72-141">Du måste använda Exchange Online PowerShell för att inaktivera granskning.</span><span class="sxs-lookup"><span data-stu-id="f6d72-141">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. <span data-ttu-id="f6d72-142">[Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6d72-142">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f6d72-143">Kör följande PowerShell-kommando för att inaktivera granskning.</span><span class="sxs-lookup"><span data-stu-id="f6d72-143">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="f6d72-144">Kontrollera att granskning är inaktiverat (inaktiverat) efter ett tag.</span><span class="sxs-lookup"><span data-stu-id="f6d72-144">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="f6d72-145">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="f6d72-145">There are two ways to do this:</span></span>

    - <span data-ttu-id="f6d72-146">I Exchange Online PowerShell kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f6d72-146">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="f6d72-147">Värdet för  `False` egenskapen  _UnifiedAuditLogIngestionEnabled_ anger att granskning är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="f6d72-147">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="f6d72-148">Gå till **sidan** Granskning i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="f6d72-148">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="f6d72-149">Om granskning inte är aktiverat för organisationen visas en banderoll där du uppmanas att börja spela in användar- och administratörsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="f6d72-149">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
