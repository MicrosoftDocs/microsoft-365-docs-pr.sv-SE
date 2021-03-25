---
title: Felsöka problem med SIEM-verktygsintegrering i Microsoft Defender ATP
description: Felsöka problem som kan uppstå när du använder SIEM-verktyg med Microsoft Defender ATP.
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
ms.openlocfilehash: c1c8fdb0b6e84d4265defb95d91b59a584b7f4c2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185785"
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

2. Välj **Azure Active Directory.**

3. Välj klientorganisation.

4. Klicka **på Appregistreringar.** Välj sedan programmet i programlistan.

5. Välj  nyckelavsnittet, ange sedan en nyckelbeskrivning och ange hur lång nyckellängden ska vara.

6. Klicka på **Spara**. Nyckelvärdet visas.

7. Kopiera värdet och spara det på ett säkert ställe.


## <a name="error-when-getting-a-refresh-access-token"></a>Felmeddelande när en token för uppdateringsåtkomst visas
Om du får ett felmeddelande när du försöker få en uppdateringstoken när du använder verktygen threat intelligence API eller SIEM måste du lägga till svars-URL för relevant program i Azure Active Directory.

1. Logga in på [Azure-hanteringsportalen](https://ms.portal.azure.com).

2. Välj **Azure Active Directory.**

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
