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
description: Integrera Microsoft 365 med Azure AD om du vill ha Lösenordssynkronisering eller enkel inloggning med din lokala miljö.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384741"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="c873d-103">Azure-integrering med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c873d-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="c873d-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c873d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c873d-105">I Microsoft 365 används Azure Active Directory (Azure AD) för att hantera användar identiteter bakom kulisserna.</span><span class="sxs-lookup"><span data-stu-id="c873d-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="c873d-106">Ditt Microsoft 365-abonnemang innehåller ett kostnads fritt Azure AD-abonnemang så att du kan integrera dina lokala Active Directory Domain Services (AD DS) för att synkronisera användar konton och lösen ord eller konfigurera en enkel inloggning.</span><span class="sxs-lookup"><span data-stu-id="c873d-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="c873d-107">Du kan också köpa avancerade funktioner för att hantera dina konton bättre.</span><span class="sxs-lookup"><span data-stu-id="c873d-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="c873d-108">Azure AD erbjuder även andra funktioner, till exempel att hantera integrerade appar, som du kan använda för att utöka och anpassa dina Microsoft 365-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="c873d-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="c873d-109">Du kan använda Azure AD Advisor för användning av en guidad installation och konfiguration i administrations centret för Microsoft 365 (du måste vara inloggad på Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="c873d-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="c873d-110">Azure AD Connect Advisor</span><span class="sxs-lookup"><span data-stu-id="c873d-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="c873d-111">Distributions rådgivare för AD FS</span><span class="sxs-lookup"><span data-stu-id="c873d-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="c873d-112">Konfigurations guide för Azure AD</span><span class="sxs-lookup"><span data-stu-id="c873d-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="c873d-113">Azure AD-utgåvor och Microsoft 365 Identity Management</span><span class="sxs-lookup"><span data-stu-id="c873d-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="c873d-114">Om du har ett betalt abonnemang på Microsoft 365 har du också ett gratis Azure AD-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="c873d-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="c873d-115">Du kan använda Azure AD för att skapa och hantera användar-och grupp konton.</span><span class="sxs-lookup"><span data-stu-id="c873d-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="c873d-116">Om du vill aktivera det här abonnemanget måste du slutföra en enstaka registrering.</span><span class="sxs-lookup"><span data-stu-id="c873d-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="c873d-117">Därefter kan du få till gång till Azure AD från Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="c873d-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="c873d-118">Anvisningar för hur du registrerar din gratis Azure AD-prenumeration finns i [använda din gratis Azure AD-prenumeration](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c873d-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="c873d-119">Gå inte direkt till azure.microsoft.com för att registrera dig, eller så får du ett utvärderings abonnemang till Microsoft Azure som är åtskilt från din gratis Azure AD-prenumeration med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c873d-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="c873d-120">Med den kostnads fria prenumerationen kan du synkronisera med lokala kataloger, konfigurera enkel inloggning och synkronisera med många program som tjänst program, till exempel Salesforce, DropBox och många fler.</span><span class="sxs-lookup"><span data-stu-id="c873d-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="c873d-121">Om du vill använda förbättrade AD DS-funktioner, dubbelriktad synkronisering och andra hanterings funktioner kan du uppgradera ditt kostnads fria abonnemang till ett betalt Premium-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="c873d-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="c873d-122">Mer information finns i [Azure Active Directory-utgåvor](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="c873d-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="c873d-123">Mer information om Microsoft 365 och Azure AD finns i [microsoft 365-Identity-modeller](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="c873d-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="c873d-124">Utöka funktionerna i din Microsoft 365-klient organisation</span><span class="sxs-lookup"><span data-stu-id="c873d-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="c873d-125">**Funktion**</span><span class="sxs-lookup"><span data-stu-id="c873d-125">**Feature**</span></span>|<span data-ttu-id="c873d-126">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="c873d-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c873d-127">Integrerade appar</span><span class="sxs-lookup"><span data-stu-id="c873d-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="c873d-128">Du kan ge enskilda appar åtkomst till dina Microsoft 365-data, till exempel e-post, kalendrar, kontakter, användare, grupper, filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="c873d-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="c873d-129">Du kan också auktorisera dessa appar på global administratörs nivå och göra dem tillgängliga för hela företaget genom att registrera appar i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c873d-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="c873d-130">Information om Formore finns i [integrerade program och Azure AD för Microsoft 365-administratörer](integrated-apps-and-azure-ads.md).</span><span class="sxs-lookup"><span data-stu-id="c873d-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="c873d-131">Se även [enkel inloggning](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="c873d-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="c873d-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="c873d-132">PowerApps</span></span>  <br/> | <span data-ttu-id="c873d-133">Power Apps är prioriterade appar för mobila enheter som kan ansluta till dina befintliga data källor, till exempel SharePoint-listor och andra dataappar.</span><span class="sxs-lookup"><span data-stu-id="c873d-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="c873d-134">Mer information finns i [skapa en PowerApp för en lista i SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) och [sidan PowerApps](https://powerapps.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="c873d-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c873d-135">Se även</span><span class="sxs-lookup"><span data-stu-id="c873d-135">See also</span></span>

[<span data-ttu-id="c873d-136">Översikt över Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c873d-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
