---
title: Samar beta med personer utanför organisationen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: Lär dig hur du konfigurerar Microsoft 365-appar som team, OneDrive och SharePoint för samarbete med personer utanför organisationen.
ms.openlocfilehash: 9a15ea06cec6982977ec88edf5ee95b35591a33c
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906995"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="e0183-103">Samar beta med personer utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="e0183-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="e0183-104">Funktionerna för extern delning i Microsoft 365 ger en möjlighet för personer i organisationen att samar beta med partners, leverantörer, kunder och andra som inte har något konto i katalogen.</span><span class="sxs-lookup"><span data-stu-id="e0183-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="e0183-105">Du kan dela hela team eller webbplatser med personer utanför organisationen eller bara enskilda filer.</span><span class="sxs-lookup"><span data-stu-id="e0183-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="e0183-106">Samarbete med personer utanför din organisation består av två huvud komponenter:</span><span class="sxs-lookup"><span data-stu-id="e0183-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="e0183-107">**Aktivera delning** – konfigurera delnings kontrollerna i Azure Active Directory, teams, Microsoft 365 Groups och SharePoint för att tillåta delnings nivån som du vill använda för din organisation.</span><span class="sxs-lookup"><span data-stu-id="e0183-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="e0183-108">**Aktivera ytterligare säkerhet** -medan funktionerna för grundläggande delning kan konfigureras så att personer utanför din organisation behöver autentiseras kan Microsoft 365 få många fler funktioner för säkerhet och efterlevnad som hjälper dig att skydda dina data och underhålla styrnings principer samtidigt som du delar externt.</span><span class="sxs-lookup"><span data-stu-id="e0183-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="e0183-109">Aktivera delning</span><span class="sxs-lookup"><span data-stu-id="e0183-109">Enable sharing</span></span>

<span data-ttu-id="e0183-110">I Microsoft 365 är det normalt aktiverat att dela med personer utanför organisationen för SharePoint och OneDrive, men inte inaktiverat för Teams.</span><span class="sxs-lookup"><span data-stu-id="e0183-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="e0183-111">Många scenarier för extern delning av SharePoint och OneDrive fungerar utan ytterligare konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e0183-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="e0183-112">Kontrol lera inställningarna för ett scenario som du använder eller aktivera ett nytt genom att välja bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="e0183-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="e0183-113">[Samar beta i dokument](collaborate-on-documents.md) – lär dig hur du konfigurerar Microsoft 365 så att du kan dela och samar beta med personer utanför organisationen (både gäster och overifierade användare) på filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="e0183-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="e0183-114">[Samar beta på en webbplats](collaborate-in-site.md) – lär dig hur du konfigurerar Microsoft 365 så att du kan dela SharePoint-webbplatser med gäster.</span><span class="sxs-lookup"><span data-stu-id="e0183-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="e0183-115">[Samar beta som ett team](collaborate-as-team.md) -Läs om hur du konfigurerar Microsoft 365 för att aktivera gäst samarbete i Teams.</span><span class="sxs-lookup"><span data-stu-id="e0183-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="e0183-116">En omfattande titt på de inställningar för gäst delning som är tillgängliga i Microsoft 365 finns i [Inställningar för gäst delning i microsoft 365](microsoft-365-guest-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e0183-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="e0183-117">Aktivera ytterligare säkerhet</span><span class="sxs-lookup"><span data-stu-id="e0183-117">Enable additional security</span></span>

<span data-ttu-id="e0183-118">När du har aktiverat det scenario du vill använda för att dela med personer utanför organisationen bör du överväga ytterligare säkerhetsfunktioner för att skydda innehållet mot oavsiktlig eller avsiktlig olämplig delning.</span><span class="sxs-lookup"><span data-stu-id="e0183-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="e0183-119">[Metod tips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md) – lär dig mer om metod tips för delning med oautentiserade användare.</span><span class="sxs-lookup"><span data-stu-id="e0183-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="e0183-120">[Begränsa oavsiktlig exponering](share-limit-accidental-exposure.md) – lär dig hur man oavsiktligt delar känsligt innehåll med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="e0183-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="e0183-121">[Skapa en säker gäst delnings miljö](create-secure-guest-sharing-environment.md) – lär dig mer om verktygen i Microsoft 365 för att säkerställa att delning med personer utanför din organisation sker på ett säkert sätt och uppfyller dina styrnings krav.</span><span class="sxs-lookup"><span data-stu-id="e0183-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="e0183-122">Samar beta med partner företag</span><span class="sxs-lookup"><span data-stu-id="e0183-122">Collaborate with partner companies</span></span>

<span data-ttu-id="e0183-123">När du arbetar i ett stort projekt som innehåller många gäster från en annan organisation, eller om du har en pågående leverantörs relation där gäster ofta förändras, kan du använda hantering av avrop i Azure Active Directory för att förenkla gäst hanteringen och låta partner företaget dela detta ansvar.</span><span class="sxs-lookup"><span data-stu-id="e0183-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="e0183-124">Mer information finns i [skapa ett B2B-extra nät med hanterade gäster](b2b-extranet.md) .</span><span class="sxs-lookup"><span data-stu-id="e0183-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="e0183-125">Begränsa delning</span><span class="sxs-lookup"><span data-stu-id="e0183-125">Limit sharing</span></span>

<span data-ttu-id="e0183-126">Om några av delnings funktionerna i Microsoft 365 står sig mot dina styrnings principer kan du läsa [begränsa delning i microsoft 365](microsoft-365-limit-sharing.md) för att få reda på alternativ för att begränsa delning.</span><span class="sxs-lookup"><span data-stu-id="e0183-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e0183-127">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e0183-127">Related topics</span></span>

[<span data-ttu-id="e0183-128">Introduktion till filsamarbete i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0183-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="e0183-129">Planera filsamarbete i SharePoint med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0183-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
