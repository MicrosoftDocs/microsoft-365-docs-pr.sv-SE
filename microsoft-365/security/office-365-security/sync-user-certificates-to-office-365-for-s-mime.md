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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du publicerar lämpliga certifikat till Office 365 innan du skickar S/MIME-skyddade meddelanden i Exchange Online.
ms.openlocfilehash: 3551dbacc3cc6279d319860f1133d059216ae591
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202109"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Synkronisera användarcertifikat med Office 365 för S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Innan någon kan skicka S/MIME-skyddade meddelanden i Exchange Online måste lämpliga certifikat vara konfigurerade. För att skicka krypterade meddelanden via Exchange Online använder avsändarens e-postprogram det offentliga certifikatet för mottagaren för att kryptera meddelandet. Det här offentliga 509-certifikatet måste publiceras till Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Så här synkroniserar du certifikat som stöder S/MIME

Börja konfigurera S/MIME genom att utfärda certifikat och publicera dem i din lokala Active Directory Domain Service. Mer information finns i [Översikt över Active Directory-certifikattjänster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

När du har publicerat dina certifikat kan du använda Azure AD Connect-verktyget för att synkronisera användar data från din lokala Exchange-miljö till Office 365. Mer information om den här processen finns i [Azure AD Connect-synkronisering: förstå och anpassa synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

När du synkroniserar andra katalog data med S/MIME-funktioner synkroniserar verktyget  **userCertificate** och **userSMIMECertificate** för varje User-objekt så att data kan användas för att signera och kryptera meddelanden.

## <a name="more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)

[Vad är Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
