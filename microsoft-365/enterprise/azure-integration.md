---
title: Azure-integrering med Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: Integrera Microsoft 365 med Azure AD om du vill ha lösenordssynkronisering eller enkel inloggning i din lokala miljö.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905338"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="3b568-103">Azure-integrering med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b568-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="3b568-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3b568-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3b568-105">Microsoft 365 använder Azure Active Directory (Azure AD) för att hantera användaridentiteter i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="3b568-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="3b568-106">I din Microsoft 365-prenumeration ingår en kostnadsfri Azure AD-prenumeration så att du kan integrera din lokala AD DS (Active Directory Domain Services) för att synkronisera användarkonton och lösenord eller konfigurera enkel inloggning.</span><span class="sxs-lookup"><span data-stu-id="3b568-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="3b568-107">Du kan också köpa avancerade funktioner för att bättre hantera dina konton.</span><span class="sxs-lookup"><span data-stu-id="3b568-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="3b568-108">Azure AD erbjuder även andra funktioner, till exempel hantering av integrerade appar, som du kan använda för att utöka och anpassa Microsoft 365 prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="3b568-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="3b568-109">Du kan använda Azure AD-distributionsrådgivaren för en guidad konfiguration och konfiguration i administrationscentret för Microsoft 365 (du måste vara inloggad för att Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="3b568-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="3b568-110">Azure AD Anslut rådgivare</span><span class="sxs-lookup"><span data-stu-id="3b568-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="3b568-111">DISTRIBUTIONSrådgivaren för AD FS</span><span class="sxs-lookup"><span data-stu-id="3b568-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="3b568-112">Konfigurationsguide för Azure AD</span><span class="sxs-lookup"><span data-stu-id="3b568-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="3b568-113">Azure AD-utgåvor och Microsoft 365 identitetshantering</span><span class="sxs-lookup"><span data-stu-id="3b568-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="3b568-114">Om du har en betald prenumeration på Microsoft 365 har du också en kostnadsfri Azure AD-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="3b568-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="3b568-115">Du kan använda Azure AD för att skapa och hantera användar- och gruppkonton.</span><span class="sxs-lookup"><span data-stu-id="3b568-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="3b568-116">Du måste slutföra en registrering som krävs för att aktivera den här prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="3b568-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="3b568-117">Därefter kan du komma åt Azure AD Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="3b568-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="3b568-118">Instruktioner för hur du registrerar din kostnadsfria Azure AD-prenumeration finns i [använda din kostnadsfria Azure AD-prenumeration.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="3b568-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="3b568-119">Gå inte direkt till azure.microsoft.com för att registrera dig för då kan du få en utvärderingsversion eller betald prenumeration på Microsoft Azure som skiljer sig från din kostnadsfria Azure AD-prenumeration med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b568-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="3b568-120">Med den kostnadsfria prenumerationen kan du synkronisera med lokala kataloger, konfigurera enkel inloggning och synkronisera med många programvaror som tjänstprogram, till exempel Salesforce, DropBox och många fler.</span><span class="sxs-lookup"><span data-stu-id="3b568-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="3b568-121">Om du vill ha förbättrade funktioner i AD DS, dubbelriktad synkronisering och andra hanteringsfunktioner kan du uppgradera din kostnadsfria prenumeration till en betald Premium-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="3b568-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="3b568-122">Mer information finns i [Azure Active Directory utgåvor](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="3b568-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="3b568-123">Mer information om hur du Microsoft 365 och Azure AD finns i skapa [Microsoft 365 identitetsmodeller.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="3b568-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="3b568-124">Utöka funktionerna i Microsoft 365 klientorganisation</span><span class="sxs-lookup"><span data-stu-id="3b568-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="3b568-125">**Funktion**</span><span class="sxs-lookup"><span data-stu-id="3b568-125">**Feature**</span></span>|<span data-ttu-id="3b568-126">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="3b568-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3b568-127">Integrerade appar</span><span class="sxs-lookup"><span data-stu-id="3b568-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="3b568-128">Du kan ge enskilda appar åtkomst till dina Microsoft 365 data, till exempel e-post, kalendrar, kontakter, användare, grupper, filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="3b568-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="3b568-129">Du kan också tillåta apparna på global administratörsnivå och göra dem tillgängliga för hela företaget genom att registrera apparna i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3b568-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="3b568-130">Mer information finns i [Integrerade appar och Azure AD för Microsoft 365 administratörer.](integrated-apps-and-azure-ads.md)</span><span class="sxs-lookup"><span data-stu-id="3b568-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="3b568-131">Se [även Enkel inloggning.](/azure/active-directory/manage-apps/what-is-single-sign-on)</span><span class="sxs-lookup"><span data-stu-id="3b568-131">Also see [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>  <br/> |
|<span data-ttu-id="3b568-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="3b568-132">PowerApps</span></span>  <br/> | <span data-ttu-id="3b568-133">Power-appar är fokuserade appar för mobila enheter som kan ansluta till dina befintliga datakällor, SharePoint till exempel listor och andra dataappar.</span><span class="sxs-lookup"><span data-stu-id="3b568-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="3b568-134">Mer [information finns i Skapa en PowerApp SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) och sidan [PowerApps.](https://powerapps.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="3b568-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3b568-135">Se även</span><span class="sxs-lookup"><span data-stu-id="3b568-135">See also</span></span>

[<span data-ttu-id="3b568-136">Microsoft 365 Enterprise översikt</span><span class="sxs-lookup"><span data-stu-id="3b568-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)