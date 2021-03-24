---
title: Synkronisera användarcertifikat med Office 365 för S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig att publicera lämpliga certifikat till Office 365 innan du skickar S/MIME-skyddade meddelanden i Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 387f9f405afd45254c6568aa92334a7ee5b4171f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071185"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="50504-103">Synkronisera användarcertifikat med Office 365 för S/MIME</span><span class="sxs-lookup"><span data-stu-id="50504-103">Sync user certificates to Office 365 for S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="50504-104">Innan någon kan skicka S/MIME-skyddade meddelanden i Exchange Online måste lämpliga certifikat konfigureras.</span><span class="sxs-lookup"><span data-stu-id="50504-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="50504-105">För att skicka krypterade meddelanden via Exchange Online använder avsändarens e-postapp mottagarens offentliga certifikat för att kryptera meddelandet.</span><span class="sxs-lookup"><span data-stu-id="50504-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="50504-106">Det här offentliga X.509-certifikatet måste publiceras till Office 365.</span><span class="sxs-lookup"><span data-stu-id="50504-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="50504-107">Så här synkroniserar du certifikat med stöd för S/MIME</span><span class="sxs-lookup"><span data-stu-id="50504-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="50504-108">Börja konfigurera S/MIME genom att utfärda certifikat och publicera dem i din lokala Active Directory Domain Service.</span><span class="sxs-lookup"><span data-stu-id="50504-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="50504-109">Mer information finns i Översikt [över Active Directory Certificate Services](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="50504-109">For more information, see [Active Directory Certificate Services Overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="50504-110">När dina certifikat har publicerats använder du verktyget Azure AD Connect för att synkronisera användardata från din lokala Exchange-miljö till Office 365.</span><span class="sxs-lookup"><span data-stu-id="50504-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="50504-111">Mer information om den här processen finns i [Azure AD Connect-synkronisering: Förstå och anpassa synkronisering](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="50504-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="50504-112">Tillsammans med synkronisering av andra katalogdata, i S/MIME-syfte, synkroniserar verktyget  **userCertificate-** och **userSMIMECertificate-attribut** för varje användarobjekt så att data kan användas för att signera och kryptera meddelanden.</span><span class="sxs-lookup"><span data-stu-id="50504-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="50504-113">Mer information</span><span class="sxs-lookup"><span data-stu-id="50504-113">More Information</span></span>

[<span data-ttu-id="50504-114">S/MIME för signering och kryptering av meddelanden</span><span class="sxs-lookup"><span data-stu-id="50504-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="50504-115">Vad är Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="50504-115">What is Azure AD Connect?</span></span>](/azure/active-directory/hybrid/whatis-azure-ad-connect)