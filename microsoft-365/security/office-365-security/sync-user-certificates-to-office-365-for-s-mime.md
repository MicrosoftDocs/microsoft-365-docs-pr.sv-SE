---
title: Synkronisera användarcertifikat med Office 365 för S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du publicerar lämpliga certifikat till Office 365 innan du skickar S/MIME-skyddade meddelanden i Exchange Online.
ms.openlocfilehash: f9e0bef2f7d2125e2daeb86b3cf44ae433aae117
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035218"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="f5b9f-103">Synkronisera användarcertifikat med Office 365 för S/MIME</span><span class="sxs-lookup"><span data-stu-id="f5b9f-103">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="f5b9f-104">Innan någon kan skicka S/MIME-skyddade meddelanden i Exchange Online måste lämpliga certifikat ställas in.</span><span class="sxs-lookup"><span data-stu-id="f5b9f-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="f5b9f-105">Om du vill skicka krypterade meddelanden via Exchange Online använder avsändarens e-postapp mottagarens offentliga certifikat för att kryptera meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f5b9f-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="f5b9f-106">Det här offentliga X.509-certifikatet måste publiceras i Office 365.</span><span class="sxs-lookup"><span data-stu-id="f5b9f-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="f5b9f-107">Så här synkroniserar du certifikat som stöder S/MIME</span><span class="sxs-lookup"><span data-stu-id="f5b9f-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="f5b9f-108">Börja konfigurera S/MIME genom att utfärda certifikat och publicera dem i den lokala Active Directory Domain-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f5b9f-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="f5b9f-109">Mer information finns i [Översikt över Active Directory-certifikattjänster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="f5b9f-109">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="f5b9f-110">När dina certifikat har publicerats använder du Azure AD Connect-verktyget för att synkronisera användardata från din lokala Exchange-miljö till Office 365.</span><span class="sxs-lookup"><span data-stu-id="f5b9f-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="f5b9f-111">Mer information om den här processen finns i Synkronisering av [Azure AD Connect: Förstå och anpassa synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="f5b9f-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="f5b9f-112">Tillsammans med synkronisering av andra katalogdata synkroniseras attributen **userCertificate** och **userSMIMECertificate** för varje användarobjekt för S/MIME för S/MIME-attribut för S/MIME-attribut.</span><span class="sxs-lookup"><span data-stu-id="f5b9f-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="f5b9f-113">Läs mer</span><span class="sxs-lookup"><span data-stu-id="f5b9f-113">More Information</span></span>

[<span data-ttu-id="f5b9f-114">S/MIME för signering och kryptering av meddelanden</span><span class="sxs-lookup"><span data-stu-id="f5b9f-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="f5b9f-115">Vad är Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="f5b9f-115">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
