---
title: Samarbeta med personer utanför organisationen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: Lär dig hur du konfigurerar Microsoft 365-appar som Teams, OneDrive och SharePoint för samarbete med personer utanför organisationen.
ms.openlocfilehash: 85aa77982fa15adb62bd587856546d2828edb942
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599825"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="733d0-103">Samarbeta med personer utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="733d0-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="733d0-104">Funktionerna för extern delning i Microsoft 365 ger personer i organisationen möjlighet att samarbeta med partner, leverantörer, kunder och andra som inte har något konto i katalogen.</span><span class="sxs-lookup"><span data-stu-id="733d0-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="733d0-105">Du kan dela hela team eller webbplatser med personer utanför organisationen eller bara enskilda filer.</span><span class="sxs-lookup"><span data-stu-id="733d0-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="733d0-106">Samarbetet med personer utanför organisationen består av två huvudkomponenter:</span><span class="sxs-lookup"><span data-stu-id="733d0-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="733d0-107">**Aktivera delning** – Konfigurera delningskontrollerna i Azure Active Directory, Teams, Microsoft 365-grupper och SharePoint så att rätt delningsnivå tillåts för organisationen.</span><span class="sxs-lookup"><span data-stu-id="733d0-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="733d0-108">**Aktivera ytterligare** säkerhet – De grundläggande delningsfunktionerna kan konfigureras så att personer utanför din organisation måste autentisera, men Microsoft 365 tillhandahåller många ytterligare säkerhets- och efterlevnadsfunktioner som hjälper dig att skydda dina data och underhålla dina styrningsprinciper medan du delar externt.</span><span class="sxs-lookup"><span data-stu-id="733d0-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

<span data-ttu-id="733d0-109">Läs [Konfigurera säkert samarbete med Microsoft 365](/microsoft-365/solutions/setup-secure-collaboration-with-teams) och Microsoft Teams om du vill veta hur extern delning kan delas med den övergripande vägledningen för Microsoft 365-samarbete.</span><span class="sxs-lookup"><span data-stu-id="733d0-109">Read [Set up secure collaboration with Microsoft 365 and Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams) to learn how external sharing ties in with the overall Microsoft 365 collaboration guidance.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="733d0-110">Aktivera delning</span><span class="sxs-lookup"><span data-stu-id="733d0-110">Enable sharing</span></span>

<span data-ttu-id="733d0-111">Delning med personer utanför organisationen är aktiverat som standard i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="733d0-111">By default, in Microsoft 365, sharing with people outside your organization is enabled.</span></span> <span data-ttu-id="733d0-112">Många scenarier med extern delning fungerar utan ytterligare konfiguration.</span><span class="sxs-lookup"><span data-stu-id="733d0-112">Many external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="733d0-113">Bekräfta inställningarna för ett scenario som du använder eller aktivera ett nytt genom att välja bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="733d0-113">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="733d0-114">[Samarbeta i dokument](collaborate-on-documents.md) – Lär dig hur du konfigurerar Microsoft 365 för att tillåta delning och samarbete med personer utanför organisationen (både gäster och oauthenticerade användare) i filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="733d0-114">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="733d0-115">[Samarbeta på en webbplats –](collaborate-in-site.md) Lär dig hur du konfigurerar Microsoft 365 för att aktivera delning av SharePoint-webbplatser med gäster.</span><span class="sxs-lookup"><span data-stu-id="733d0-115">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="733d0-116">[Samarbeta som ett team](collaborate-as-team.md) – Lär dig hur du konfigurerar Microsoft 365 för att möjliggöra gästsamarbete i Teams.</span><span class="sxs-lookup"><span data-stu-id="733d0-116">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="733d0-117">Mer detaljerad information om vilka gästdelningsinställningar som är tillgängliga i Microsoft 365 finns i Referens för [gästdelningsinställningar i Microsoft 365.](microsoft-365-guest-settings.md)</span><span class="sxs-lookup"><span data-stu-id="733d0-117">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="733d0-118">Aktivera ytterligare säkerhet</span><span class="sxs-lookup"><span data-stu-id="733d0-118">Enable additional security</span></span>

<span data-ttu-id="733d0-119">När du har aktiverat det scenario som du vill använda för delning med personer utanför organisationen kan du överväga ytterligare säkerhetsåtgärder för att skydda innehållet från oavsiktlig eller avsiktlig olämplig delning.</span><span class="sxs-lookup"><span data-stu-id="733d0-119">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="733d0-120">Rekommendationer för att dela filer och mappar med [oauthenticerade](best-practices-anonymous-sharing.md) användare – Lär dig mer om de bästa metoderna för att dela med oauthenticerade användare.</span><span class="sxs-lookup"><span data-stu-id="733d0-120">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="733d0-121">[Begränsa oavsiktlig exponering](share-limit-accidental-exposure.md) – Lär dig hur du minskar risken för att råka dela känsligt innehåll med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="733d0-121">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="733d0-122">[Skapa en säker](create-secure-guest-sharing-environment.md) gästdelningsmiljö – Läs mer om verktygen i Microsoft 365 för att se till att delning med personer utanför organisationen görs på ett säkert sätt och uppfyller dina styrningskrav.</span><span class="sxs-lookup"><span data-stu-id="733d0-122">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="733d0-123">Samarbeta med partnerföretag</span><span class="sxs-lookup"><span data-stu-id="733d0-123">Collaborate with partner companies</span></span>

<span data-ttu-id="733d0-124">När du arbetar med ett stort projekt som involverar många gäster från en annan organisation, eller om du har en pågående leverantörsrelation där gäster ofta ändras, kan du använda hantering av berättigande i Azure Active Directory för att förenkla gästhantering och låta partnerföretaget dela på det ansvaret.</span><span class="sxs-lookup"><span data-stu-id="733d0-124">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="733d0-125">Mer [information finns i Skapa ett B2B-extranät med](b2b-extranet.md) hanterade gäster.</span><span class="sxs-lookup"><span data-stu-id="733d0-125">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="733d0-126">Begränsa delning</span><span class="sxs-lookup"><span data-stu-id="733d0-126">Limit sharing</span></span>

<span data-ttu-id="733d0-127">Om några av delningsfunktionerna i Microsoft 365 är i konflikt med dina styrningsprinciper kan du läsa Mer information om alternativ för att begränsa delning i [Microsoft 365.](microsoft-365-limit-sharing.md)</span><span class="sxs-lookup"><span data-stu-id="733d0-127">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="733d0-128">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="733d0-128">Related topics</span></span>

[<span data-ttu-id="733d0-129">Introduktion till filsamarbete i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="733d0-129">Intro to file collaboration in Microsoft 365</span></span>](/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="733d0-130">Planera samarbete i filer i SharePoint med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="733d0-130">Plan file collaboration in SharePoint with Microsoft 365</span></span>](/sharepoint/deploy-file-collaboration)
