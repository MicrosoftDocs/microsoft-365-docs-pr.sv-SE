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
description: I den här artikeln lär du dig att publicera lämpliga certifikat till Office 365 innan du skickar S/MIME-skyddade meddelanden i Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8c6d3968d617bcb503057c47567182091010c726
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290207"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Synkronisera användarcertifikat med Office 365 för S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Innan någon kan skicka S/MIME-skyddade meddelanden i Exchange Online måste lämpliga certifikat konfigureras. För att skicka krypterade meddelanden via Exchange Online använder avsändarens e-postapp mottagarens offentliga certifikat för att kryptera meddelandet. Det här offentliga X.509-certifikatet måste publiceras i Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Så här synkroniserar du certifikat med stöd för S/MIME

Börja konfigurera S/MIME genom att utfärda certifikat och publicera dem i din lokala Active Directory Domain Service. Mer information finns i Active [Directory Certificate Services – översikt.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))

När certifikaten har publicerats använder du verktyget Azure AD Connect för att synkronisera användardata från din lokala Exchange-miljö till Office 365. Mer information om den här processen finns i [Azure AD Connect-synkronisering: Förstå och anpassa synkronisering.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

Tillsammans med synkronisering av andra katalogdata, i S/MIME-syften, synkroniserar verktyget  **attributen userCertificate** och **userSMIMECertificate** för varje användarobjekt så att data kan användas för att signera och kryptera meddelanden.

## <a name="more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)

[Vad är Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
