---
title: Samarbeta med personer utanför organisationen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- M365solutions
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Lär dig hur du konfigurerar Microsoft 365 för samarbete med personer utanför organisationen.
ms.openlocfilehash: 5d85b164133d235dce410cd6cbda778588fd093a
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160021"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="61b56-103">Samarbeta med personer utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="61b56-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="61b56-104">Funktionerna för extern delning i Microsoft 365 ger personer i organisationen möjlighet att samarbeta med partner, leverantörer, kunder och andra som inte har ett konto i katalogen.</span><span class="sxs-lookup"><span data-stu-id="61b56-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="61b56-105">Du kan dela hela team eller webbplatser med personer utanför organisationen eller bara enskilda filer.</span><span class="sxs-lookup"><span data-stu-id="61b56-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="61b56-106">Att samarbeta med personer utanför organisationen består av två huvudkomponenter:</span><span class="sxs-lookup"><span data-stu-id="61b56-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="61b56-107">**Aktivera delning** – Konfigurera delningskontrollerna i Azure Active Directory, Teams, Microsoft 365 Groups och SharePoint så att den delningsnivå som du vill ha för din organisation kan tillåtas.</span><span class="sxs-lookup"><span data-stu-id="61b56-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="61b56-108">**Aktivera ytterligare säkerhet** – Även om de grundläggande delningsfunktionerna kan konfigureras så att personer utanför organisationen autentiseras, innehåller Microsoft 365 många ytterligare säkerhets- och efterlevnadsfunktioner som hjälper dig att skydda dina data och underhålla dina styrningsprinciper samtidigt som du delar externt.</span><span class="sxs-lookup"><span data-stu-id="61b56-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="61b56-109">Aktivera delning</span><span class="sxs-lookup"><span data-stu-id="61b56-109">Enable sharing</span></span>

<span data-ttu-id="61b56-110">I Microsoft 365 är som standard delning med personer utanför organisationen aktiverad för SharePoint och OneDrive, men inaktiverad för Teams.</span><span class="sxs-lookup"><span data-stu-id="61b56-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="61b56-111">Många externa delningsscenarier i SharePoint och OneDrive fungerar utan ytterligare konfiguration.</span><span class="sxs-lookup"><span data-stu-id="61b56-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="61b56-112">Så här bekräftar du inställningarna för ett scenario som du använder eller aktiverar ett nytt alternativ:</span><span class="sxs-lookup"><span data-stu-id="61b56-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="61b56-113">[Samarbeta i dokument](collaborate-on-documents.md) – Lär dig hur du konfigurerar Microsoft 365 så att du kan dela och samarbeta med personer utanför organisationen (både gäster och oautentiserade användare) i filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="61b56-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="61b56-114">[Samarbeta på en webbplats](collaborate-in-site.md) – Lär dig hur du konfigurerar Microsoft 365 så att du kan dela SharePoint-webbplatser med gäster.</span><span class="sxs-lookup"><span data-stu-id="61b56-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="61b56-115">[Samarbeta som ett team](collaborate-as-team.md) – Lär dig hur du konfigurerar Microsoft 365 så att gästsamarbete i Teams kan aktiveras.</span><span class="sxs-lookup"><span data-stu-id="61b56-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="61b56-116">En omfattande titt på de inställningar för gästdelning som finns tillgängliga i Microsoft 365 finns i [Microsoft 365-referens för gästdelningsinställningar](microsoft-365-guest-settings.md).</span><span class="sxs-lookup"><span data-stu-id="61b56-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="61b56-117">Aktivera ytterligare säkerhet</span><span class="sxs-lookup"><span data-stu-id="61b56-117">Enable additional security</span></span>

<span data-ttu-id="61b56-118">När du har aktiverat det scenario som du vill använda för att dela med personer utanför organisationen bör du överväga ytterligare skyddsåtgärder för att skydda ditt innehåll från oavsiktlig eller avsiktlig olämplig delning.</span><span class="sxs-lookup"><span data-stu-id="61b56-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="61b56-119">[Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md) – Lär dig mer om metodtips för delning med oautentiserade användare.</span><span class="sxs-lookup"><span data-stu-id="61b56-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="61b56-120">[Begränsa oavsiktlig exponering](share-limit-accidental-exposure.md) – Lär dig hur du minskar risken för att oavsiktligt dela känsligt innehåll med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="61b56-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="61b56-121">[Skapa en säker gästdelningsmiljö](create-secure-guest-sharing-environment.md) – Lär dig mer om de verktyg som finns i Microsoft 365 för att se till att delning med personer utanför organisationen sker på ett tryggt och säkert sätt och uppfyller dina styrningskrav.</span><span class="sxs-lookup"><span data-stu-id="61b56-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="61b56-122">Samarbeta med partnerföretag</span><span class="sxs-lookup"><span data-stu-id="61b56-122">Collaborate with partner companies</span></span>

<span data-ttu-id="61b56-123">När du arbetar med ett stort projekt som involverar många gäster från en annan organisation, eller om du har en pågående leverantörsrelation där gäster ofta förändras, kan du använda berättigandehantering i Azure Active Directory för att förenkla gästhantering och låta partnerföretaget dela det ansvaret.</span><span class="sxs-lookup"><span data-stu-id="61b56-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="61b56-124">Mer information finns i [Skapa ett B2B-extranät med hanterade gäster.](b2b-extranet.md)</span><span class="sxs-lookup"><span data-stu-id="61b56-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="61b56-125">Begränsa delning</span><span class="sxs-lookup"><span data-stu-id="61b56-125">Limit sharing</span></span>

<span data-ttu-id="61b56-126">Om vissa delningsfunktioner i Microsoft 365 står i konflikt med dina styrningsprinciper läser du [Begränsa delning i Microsoft 365](microsoft-365-limit-sharing.md) om du vill veta mer om alternativ för att begränsa delning.</span><span class="sxs-lookup"><span data-stu-id="61b56-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="see-also"></a><span data-ttu-id="61b56-127">Se även</span><span class="sxs-lookup"><span data-stu-id="61b56-127">See Also</span></span>

[<span data-ttu-id="61b56-128">Intro till filsamarbete i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="61b56-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="61b56-129">Planera filsamarbete i SharePoint med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="61b56-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
