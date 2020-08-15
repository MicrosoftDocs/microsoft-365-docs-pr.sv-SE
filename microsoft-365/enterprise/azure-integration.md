---
title: Azure-integrering med Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integrera Microsoft 365 med Azure AD om du vill ha Lösenordssynkronisering eller enkel inloggning med din lokala miljö.
ms.openlocfilehash: 045760f000abdbf053e09d89b296fbafa4c24786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694870"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="9e741-103">Azure-integrering med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e741-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="9e741-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9e741-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9e741-105">I Microsoft 365 används Azure Active Directory (Azure AD) för att hantera användar identiteter bakom kulisserna.</span><span class="sxs-lookup"><span data-stu-id="9e741-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="9e741-106">Ditt Microsoft 365-abonnemang inkluderar ett gratis abonnemang på Azure AD så att du kan integrera Microsoft 365 med Azure AD om du vill synkronisera lösen ord eller konfigurera en enkel inloggning med din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="9e741-106">Your Microsoft 365 subscription includes a free subscription to Azure AD so that you can integrate Microsoft 365 with Azure AD if you want to sync passwords or set up single sign-on with your on-premises environment.</span></span> <span data-ttu-id="9e741-107">Du kan också köpa avancerade funktioner för att hantera dina konton bättre.</span><span class="sxs-lookup"><span data-stu-id="9e741-107">You can also buy advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="9e741-108">Dessutom erbjuder Azure andra funktioner, till exempel att hantera integrerade appar, som du kan använda för att utöka och anpassa dina Microsoft 365-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="9e741-108">Azure also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="9e741-109">Du kan använda Azure AD Advisor för en interaktiv konfiguration och konfigurering (du måste vara inloggad i Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="9e741-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="9e741-110">Azure AD Connect Advisor</span><span class="sxs-lookup"><span data-stu-id="9e741-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="9e741-111">Distributions rådgivare för AD FS</span><span class="sxs-lookup"><span data-stu-id="9e741-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="9e741-112">Konfigurations guide för Azure AD</span><span class="sxs-lookup"><span data-stu-id="9e741-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="9e741-113">Azure AD-utgåvor och Microsoft 365 Identity Management</span><span class="sxs-lookup"><span data-stu-id="9e741-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="9e741-114">Om du har ett betalt abonnemang på Microsoft 365 har du även ett gratis abonnemang på Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9e741-114">If you have a paid subscription to Microsoft 365, you also have a free subscription to Azure AD.</span></span> <span data-ttu-id="9e741-115">Du kan använda Azure AD för att skapa och hantera användar-och grupp konton.</span><span class="sxs-lookup"><span data-stu-id="9e741-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="9e741-116">För att aktivera detta abonnemang måste du slutföra en registrering med en gång.</span><span class="sxs-lookup"><span data-stu-id="9e741-116">To activate this subscription you have to complete a one-time registration.</span></span> <span data-ttu-id="9e741-117">Därefter kan du få till gång till Azure AD från Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="9e741-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="9e741-118">Anvisningar finns i [använda din gratis Azure AD-prenumeration](https://go.microsoft.com/fwlink/p/?LinkId=617127).</span><span class="sxs-lookup"><span data-stu-id="9e741-118">For instructions, see [use your free Azure AD subscription](https://go.microsoft.com/fwlink/p/?LinkId=617127).</span></span> <span data-ttu-id="9e741-119">Följ instruktionerna för att registrera den kostnads fria Azure AD-prenumeration som medföljer ditt abonnemang på Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e741-119">Follow the instructions to register the free Azure AD subscription that comes with your subscription to Microsoft 365.</span></span> <span data-ttu-id="9e741-120">Gå inte direkt till azure.microsoft.com för att registrera dig, eller så får du ett utvärderings abonnemang till Microsoft Azure som är åtskilt från din gratis Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e741-120">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free one for Microsoft 365.</span></span> 
  
<span data-ttu-id="9e741-121">Med den kostnads fria prenumerationen kan du synkronisera med lokala kataloger, konfigurera enkel inloggning och synkronisera med många program som tjänst program, till exempel Salesforce, DropBox och många fler.</span><span class="sxs-lookup"><span data-stu-id="9e741-121">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox and many more.</span></span>
  
<span data-ttu-id="9e741-122">Om du vill ha förbättrade funktioner för Active Directory Domain Services (AD DS), dubbelriktad synkronisering och andra hanterings funktioner kan du uppgradera ditt kostnads fria abonnemang till ett betalt Premium-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="9e741-122">If you want enhanced Active Directory Domain Services (AD DS) functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="9e741-123">Mer information finns i [Azure Active Directory-utgåvor](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="9e741-123">For details see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="9e741-124">Mer information om Microsoft 365 och Azure AD finns i [förstå microsoft 365-identitet och Azure Active Directory](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="9e741-124">For more information about Microsoft 365 and Azure AD, see [Understanding Microsoft 365 Identity and Azure Active Directory](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="9e741-125">Utöka funktionerna i din Microsoft 365-klient organisation</span><span class="sxs-lookup"><span data-stu-id="9e741-125">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="9e741-126">**Funktion**</span><span class="sxs-lookup"><span data-stu-id="9e741-126">**Feature**</span></span>|<span data-ttu-id="9e741-127">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="9e741-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e741-128">Integrerade appar</span><span class="sxs-lookup"><span data-stu-id="9e741-128">Integrated apps</span></span>  <br/> |<span data-ttu-id="9e741-129">Du kan ge enskilda appar åtkomst till dina Microsoft 365-data, som e-post, kalendrar, kontakter, användare, grupper, filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="9e741-129">You can grant individual apps access to your Microsoft 365 data, like mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="9e741-130">Du kan också auktorisera dessa appar på global administratörs nivå och göra dem tillgängliga för hela företaget genom att registrera appar i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9e741-130">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="9e741-131">Mer information finns i [integrerade program och Azure AD för Microsoft 365-administratörer](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).</span><span class="sxs-lookup"><span data-stu-id="9e741-131">For details see [Integrated Apps and Azure AD for Microsoft 365 administrators](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).</span></span>  <br/> <span data-ttu-id="9e741-132">Se även [enkel inloggning till program](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="9e741-132">Also see [single sign-on to applications](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="9e741-133">PowerApps</span><span class="sxs-lookup"><span data-stu-id="9e741-133">PowerApps</span></span>  <br/> | <span data-ttu-id="9e741-134">Power Apps är prioriterade appar för mobila enheter som kan ansluta till befintliga data källor, till exempel SharePoint-listor och andra dataappar.</span><span class="sxs-lookup"><span data-stu-id="9e741-134">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists, and other data apps.</span></span> <span data-ttu-id="9e741-135">Mer information finns i [skapa en PowerApp för en lista på SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) och [PowerApps-sidan](https://powerapps.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="9e741-135">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
<span data-ttu-id="9e741-136">Läs mer i [integrerade appar och Azure AD för Microsoft 365-administratörer](integrated-apps-and-azure-ads.md) och [Azure AD-programgalleriet och enkel inloggning](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="9e741-136">Learn more at [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md) and [Azure AD application gallery and single-sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e741-137">Se även</span><span class="sxs-lookup"><span data-stu-id="9e741-137">See also</span></span>

[<span data-ttu-id="9e741-138">Översikt över Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9e741-138">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
