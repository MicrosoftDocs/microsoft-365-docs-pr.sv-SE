---
title: Synkronisera användarcertifikat till Office 365 för S/MIME
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
description: Innan någon kan skicka S/MIME-skyddade meddelanden måste lämpliga certifikat ställas in. För att skicka krypterade meddelanden via Exchange Online använder avsändarens e-postprogram mottagarens offentliga certifikat för att kryptera meddelandet. Det här offentliga X.509-certifikatet måste publiceras i Office 365.
ms.openlocfilehash: a62af3b176f29ec2bd8c97ae02178c87b7a63544
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808623"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Synkronisera användarcertifikat till Office 365 för S/MIME

Innan någon kan skicka S/MIME-skyddade meddelanden i Exchange Online måste lämpliga certifikat ställas in. Om du vill skicka krypterade meddelanden via Exchange Online använder avsändarens e-postapp mottagarens offentliga certifikat för att kryptera meddelandet. Det här offentliga X.509-certifikatet måste publiceras i Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Så här synkroniserar du certifikat som stöder S/MIME

Börja konfigurera S/MIME genom att utfärda certifikat och publicera dem i den lokala Active Directory Domain-tjänsten. Mer information finns i [Översikt över Active Directory-certifikattjänster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

När dina certifikat har publicerats använder du Azure AD Connect-verktyget för att synkronisera användardata från din lokala Exchange-miljö till Office 365. Mer information om den här processen finns i Synkronisering av [Azure AD Connect: Förstå och anpassa synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Tillsammans med synkronisering av andra katalogdata synkroniseras attributen **userCertificate** och **userSMIMECertificate** för varje användarobjekt för S/MIME för S/MIME-attribut för S/MIME-attribut.

## <a name="more-information"></a>Läs mer

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)

[Vad är Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
