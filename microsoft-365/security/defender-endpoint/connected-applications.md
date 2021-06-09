---
title: Anslutna program i Microsoft Defender för Slutpunkt
ms.reviewer: ''
description: Visa anslutna partnerprogram som använder OAuth 2.0-standardprotokoll för att autentisera och ange token som ska användas med Microsoft Defender för slutpunkts-API:er.
keywords: partner, program, tredje part, anslutningar, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, bättre mobil
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 06ef716e9deee7b20e8615bd22c93130ee18b77f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845588"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Anslutna program i Microsoft Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Anslutna program integreras med Defender för slutpunktsplattformen med API:er. 

Program använder standard-OAuth 2.0-protokollet för att autentisera och tillhandahålla token för användning med Microsoft Defender för slutpunkts-API:er.  Dessutom tillåter Azure Active Directory (Azure AD) att innehavaradministratörer kan ställa in explicit kontroll över vilka API:er som kan nås med hjälp av motsvarande app.
 
Du måste följa de här [anvisningarna för att](/microsoft-365/security/defender-endpoint/apis-intro) använda API:erna med det anslutna programmet.
 
## <a name="access-the-connected-application-page"></a>Öppna sidan för det anslutna programmet
I den vänstra navigeringsmenyn väljer du **Partners & API:er**  >  **anslutna AAD-program.**

 
## <a name="view-connected-application-details"></a>Visa information om anslutna program
Sidan Anslutna program innehåller information om de Azure AD-program som är anslutna till Microsoft Defender för Slutpunkt i din organisation. Du kan granska användningen av anslutna program: senast sedd, antal begäranden under de senaste 24 timmarna och begär trender under de senaste 30 dagarna.

![Bild på anslutna appar](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>Redigera, konfigurera om eller ta bort ett anslutet program
Länken **Öppna programinställningar** öppnar motsvarande sida för Hantering av Azure AD-program i Azure-portalen. Från Azure Portal kan du hantera behörigheter, konfigurera om eller ta bort anslutna program.
