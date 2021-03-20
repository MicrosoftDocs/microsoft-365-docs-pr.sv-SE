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
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916460"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Synkronisera användarcertifikat med Office 365 för S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Innan någon kan skicka S/MIME-skyddade meddelanden i Exchange Online måste lämpliga certifikat konfigureras. För att skicka krypterade meddelanden via Exchange Online använder avsändarens e-postapp mottagarens offentliga certifikat för att kryptera meddelandet. Det här offentliga X.509-certifikatet måste publiceras till Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Så här synkroniserar du certifikat med stöd för S/MIME

Börja konfigurera S/MIME genom att utfärda certifikat och publicera dem i din lokala Active Directory Domain Service. Mer information finns i Översikt [över Active Directory Certificate Services](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

När dina certifikat har publicerats använder du verktyget Azure AD Connect för att synkronisera användardata från din lokala Exchange-miljö till Office 365. Mer information om den här processen finns i [Azure AD Connect-synkronisering: Förstå och anpassa synkronisering](/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Tillsammans med synkronisering av andra katalogdata, i S/MIME-syfte, synkroniserar verktyget  **userCertificate-** och **userSMIMECertificate-attribut** för varje användarobjekt så att data kan användas för att signera och kryptera meddelanden.

## <a name="more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)

[Vad är Azure AD Connect?](/azure/active-directory/hybrid/whatis-azure-ad-connect)