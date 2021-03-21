---
title: Ta bort eller inaktivera modern hybridautentisering från Skype för företag och Exchange
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
description: I den här artikeln förklaras hur du tar bort eller inaktiverar modern hybridautentisering från Skype för företag och Exchange.
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927294"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="db904-103">Ta bort eller inaktivera modern hybridautentisering från Skype för företag och Exchange</span><span class="sxs-lookup"><span data-stu-id="db904-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="db904-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="db904-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="db904-105">Om du har aktiverat HMA (Hybrid Modern Authentication) för att hitta den olämplig i din aktuella miljö kan du inaktivera HMA.</span><span class="sxs-lookup"><span data-stu-id="db904-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="db904-106">I den här artikeln förklaras hur.</span><span class="sxs-lookup"><span data-stu-id="db904-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="db904-107">Vem är den här artikeln till för?</span><span class="sxs-lookup"><span data-stu-id="db904-107">Who is this article for?</span></span>

<span data-ttu-id="db904-108">Om du har aktiverat modern autentisering i Skype för företag – Online eller Lokalt och/eller Exchange Online eller lokalt och upptäckt att du måste inaktivera HMA, är de här stegen för dig.</span><span class="sxs-lookup"><span data-stu-id="db904-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db904-109">Läs artikeln Skype för[företag-topologier](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)som stöds med modern autentisering om du är i Skype för företag – Online eller Lokalt, har HMA med blandad topologi och behöver titta på topologier som stöds innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="db904-109">See the '[Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="db904-110">Inaktivera modern hybridautentisering (Exchange)</span><span class="sxs-lookup"><span data-stu-id="db904-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="db904-111">**Lokal Exchange:** Öppna Exchange Management Shell och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="db904-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="db904-112">**Exchange Online:** [Anslut till Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) med fjärr-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db904-112">**Exchange Online**: [Connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="db904-113">Kör följande kommando för att sätta flaggan  *OAuth2ClientProfileEnabled*  till "false":</span><span class="sxs-lookup"><span data-stu-id="db904-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="db904-114">Inaktivera modern hybridautentisering (Skype för företag)</span><span class="sxs-lookup"><span data-stu-id="db904-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="db904-115">**Lokal Skype för företag:** Kör följande kommandon i Skype för företag Management Shell:</span><span class="sxs-lookup"><span data-stu-id="db904-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="db904-116">**Skype för företag – Online:** [Anslut till Skype för företag – Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) med Fjärr-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db904-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="db904-117">Kör följande kommando för att inaktivera modern autentisering:</span><span class="sxs-lookup"><span data-stu-id="db904-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="db904-118">[Länka tillbaka till översikten över Modern autentisering.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="db904-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
