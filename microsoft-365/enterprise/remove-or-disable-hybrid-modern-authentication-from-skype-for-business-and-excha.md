---
title: Ta bort eller inaktivera Hybrid från Skype för företag och Exchange
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln beskrivs hur du tar bort eller inaktiverar HYBRIDS ökning från Skype för företag och Exchange.
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547102"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="6cba9-103">Ta bort eller inaktivera Hybrid från Skype för företag och Exchange</span><span class="sxs-lookup"><span data-stu-id="6cba9-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="6cba9-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6cba9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6cba9-105">Om du har aktiverat hybrid modern (HMA) endast för att hitta den olämplig för din nuvarande miljö kan du avaktivera HMA.</span><span class="sxs-lookup"><span data-stu-id="6cba9-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="6cba9-106">I den här artikeln förklaras hur.</span><span class="sxs-lookup"><span data-stu-id="6cba9-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="6cba9-107">Vem är den här artikeln för?</span><span class="sxs-lookup"><span data-stu-id="6cba9-107">Who is this article for?</span></span>

<span data-ttu-id="6cba9-108">Om du har aktiverat modern lösenordsautentisering i Skype för företag – Online eller lokalt och/eller via Exchange Online eller lokalt och hittat dig måste du inaktivera HMA, de här stegen är till för dig.</span><span class="sxs-lookup"><span data-stu-id="6cba9-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cba9-109">Se "[Skype för företag-topologin som stöds med modern verifikation](https://technet.microsoft.com/library/mt803262.aspx)" om du är i Skype för företag – Online eller lokalt, har du en HMA och måste titta på topologier som stöds innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="6cba9-109">See the '[Skype for Business topologies supported with Modern Authentication](https://technet.microsoft.com/library/mt803262.aspx)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="6cba9-110">Så här inaktiverar du hybrid modern (Exchange)</span><span class="sxs-lookup"><span data-stu-id="6cba9-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="6cba9-111">**Lokal Exchange**: Öppna Exchange Management Shell och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="6cba9-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="6cba9-112">**Exchange Online**: [Anslut till Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) med Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cba9-112">**Exchange Online**: [Connect to Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="6cba9-113">Kör följande kommando för att aktivera flaggan  *OAuth2ClientProfileEnabled*  till "false":</span><span class="sxs-lookup"><span data-stu-id="6cba9-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="6cba9-114">Så här inaktiverar du hybrid modern (Skype för företag)</span><span class="sxs-lookup"><span data-stu-id="6cba9-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="6cba9-115">**Skype för företag – lokalt**: kör följande kommandon i Skype för företag Management Shell:</span><span class="sxs-lookup"><span data-stu-id="6cba9-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="6cba9-116">**Skype för företag – Online**: [Anslut till Skype för företag – Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) med fjärr-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cba9-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="6cba9-117">Kör följande kommando för att inaktivera modern inloggningsautentisering:</span><span class="sxs-lookup"><span data-stu-id="6cba9-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="6cba9-118">[Länka tillbaka till den moderna verifikations översikten](hybrid-modern-auth-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="6cba9-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
  

