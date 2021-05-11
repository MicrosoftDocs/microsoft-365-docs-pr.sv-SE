---
title: Felsöka problem med SIEM-verktygsintegrering i Microsoft Defender för Endpoint
description: Felsöka problem som kan uppstå när du använder SIEM-verktyg med Microsoft Defender för Slutpunkt.
keywords: felsökning, siem, klienthemlighet, hemlig
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 9c4f3da57796903fc22314574f389bcdd92ca4b3
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311994"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>Felsöka problem med SIEM-verktygsintegrering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Du kan behöva felsöka problem när du drar identifieringar i dina SIEM-verktyg.

På den här sidan finns detaljerade anvisningar för felsökning av problem som kan uppstå.


## <a name="learn-how-to-get-a-new-client-secret"></a>Lär dig hur du får en ny klienthemlighet
Om klienthemligheten går ut eller om du har tappat bort kopian som angavs när du aktiverar sieM-verktygsprogrammet måste du få en ny hemlig kopia.

1. Logga in på [Azure-hanteringsportalen](https://portal.azure.com).

2. Välj **Azure Active Directory**.

3. Välj klientorganisation.

4. Klicka **på Appregistreringar.** Välj sedan programmet i programlistan.

5. Välj **Certifikat & Secrets,** Klicka på Ny klienthemlighet, ange sedan en beskrivning och ange varaktigheten.

6. Klicka på **Spara**. Nyckelvärdet visas.

7. Kopiera värdet och spara det på ett säkert ställe.


## <a name="error-when-getting-a-refresh-access-token"></a>Felmeddelande när en token för uppdateringsåtkomst visas
Om du får ett felmeddelande när du försöker få en uppdateringstoken när du använder verktygen threat intelligence API eller SIEM måste du lägga till svars-URL för relevant program i Azure Active Directory.

1. Logga in på [Azure-hanteringsportalen](https://ms.portal.azure.com).

2. Välj **Azure Active Directory**.

3. Välj klientorganisation.

4. Klicka **på Appregistreringar.** Välj sedan programmet i programlistan.

5. Lägg till följande URL:
   - För EU: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - För Storbritannien: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - För USA:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .
 
6. Klicka på **Spara**.

## <a name="error-while-enabling-the-siem-connector-application"></a>Fel när DU aktiverar SIEM-kopplingsprogrammet
Om det uppstår ett fel när du försöker aktivera SIEM-kopplingsprogrammet kontrollerar du inställningarna för blockering av popup-fönster i webbläsaren. Det kan blockera det nya fönstret som öppnas när du aktiverar funktionen.




>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a>Relaterade ämnen
- [Aktivera SIEM-integrering i Microsoft Defender för Slutpunkt](enable-siem-integration.md)
- [Konfigurera ArcSight för att hämta Microsoft Defender för identifiering av slutpunkter](configure-arcsight.md)
- [Dra identifieringar till dina SIEM-verktyg](configure-siem.md)
- [Fälten Microsoft Defender för identifiering av slutpunkt](api-portal-mapping.md)
- [Hämta Microsoft Defender för slutpunktsidentifiering med REST API](pull-alerts-using-rest-api.md)
