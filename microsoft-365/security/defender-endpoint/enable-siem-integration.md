---
title: Aktivera SIEM-integrering i Microsoft Defender för Slutpunkt
description: Aktivera SIEM-integrering för att ta emot identifieringar i din säkerhetsinformations- och händelsehanteringslösning (SIEM).
keywords: aktivera siem-koppling, siem, anslutare, säkerhetsinformation och händelser
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 87078bb7bfc6b38788fea2a6a4c3c9108be1d5b4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842968"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a>Aktivera SIEM-integrering i Microsoft Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)


>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

Aktivera integrering av säkerhetsinformation och händelsehantering (SIEM) så att du kan hämta identifieringar Microsoft Defender Säkerhetscenter. Dra identifieringar med hjälp av din SIEM-lösning eller genom att ansluta direkt till identifieringarna REST API.

>[!NOTE]
>- [Microsoft Defender för slutpunktsavisering](alerts.md) består av en eller flera identifieringar.
>- [Microsoft Defender för identifiering av slutpunkt](api-portal-mapping.md) består av den misstänkta händelsen som inträffade på enheten och tillhörande aviseringsinformation.
>- Microsoft Defender för slutpunktsaviserings-API är det senaste API:t för aviseringsanvändning och innehåller en detaljerad lista med relaterade bevis för varje avisering. Mer information finns i [Aviseringsmetoder och egenskaper](alerts.md) och [Listaviseringar.](get-alerts.md)

## <a name="prerequisites"></a>Förutsättningar

- Den användare som aktiverar inställningen måste ha behörighet att skapa en app i Azure Active Directory (AAD). Det här är någon med följande roller: 

  - Säkerhetsadministratör och antingen global administratör
  - Administratör för molnprogram
  - Programadministratör
  - Ägaren till tjänstens huvudnamn

- Under den första aktiveringen visas en popup-skärm där du kan lägga till autentiseringsuppgifter. Se till att du tillåter popup-fönster för den här webbplatsen.

## <a name="enabling-siem-integration"></a>Aktivera SIEM-integrering 
1. I navigeringsfönstret väljer du **Inställningar**  >  **SIEM.**

    ![Bild av SIEM-integrering Inställningar meny1](images/enable_siem.png)

    >[!TIP]
    >Om det uppstår ett fel när du försöker aktivera SIEM-kopplingsprogrammet kontrollerar du inställningarna för blockering av popup-fönster i webbläsaren. Det kan blockera det nya fönstret som öppnas när du aktiverar funktionen. 

2. Välj **Aktivera SIEM-integrering.** Detta aktiverar **informationsavsnittet** för SIEM-koppling med ifyllda värden och ett program skapas under Azure Active Directory (Azure AD) klientorganisation.

    > [!WARNING]
    >Klienthemligheten visas bara en gång. Se till att spara en kopia av den på ett säkert ställe.<br>
     

    ![Bild av SIEM-integrering Inställningar meny2](images/siem_details.png)

3. Välj den SIEM-typ som du använder i organisationen.

   > [!NOTE]
   > Om du väljer HP ArcSight måste du spara de här två konfigurationsfilerna:<br>
   > - WDATP-connector.jsonparser.properties
   > - WDATP-connector.properties <br>

   Om du vill ansluta direkt till identifieringarna REST API via programmatisk åtkomst väljer du **Allmänt API.**

4. Kopiera de enskilda värdena eller välj **Spara information till fil om** du vill ladda ned en fil som innehåller alla värden.

5. Välj **Generera token för att** få en åtkomst- och uppdateringstoken.
  
   > [!NOTE]
   > Du måste skapa en ny Uppdateringstoken var 90:e dag. 

6. Följ instruktionerna för [att skapa en azure AD-appregistrering för Microsoft Defender](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) för Endpoint och tilldela rätt behörigheter till den för att läsa aviseringar.

Du kan nu fortsätta med att konfigurera din SIEM-lösning eller ansluta till identifieringen av REST API via programmeringsåtkomst. Du måste använda tokens när du konfigurerar din SIEM-lösning så att den kan ta emot identifieringar från Microsoft Defender Säkerhetscenter.

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a>Integrera Microsoft Defender för slutpunkt med IBM QRadar 
Du kan konfigurera IBM QRadar att samla in identifieringar från Microsoft Defender för Endpoint. Mer information finns i [IBM Knowledge Center.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)

## <a name="see-also"></a>Se även
- [Konfigurera HP ArcSight att hämta Microsoft Defender för identifiering av slutpunkter](configure-arcsight.md)
- [Fälten Microsoft Defender för identifiering av slutpunkt](api-portal-mapping.md)
- [Hämta Microsoft Defender för slutpunktsidentifiering med REST API](pull-alerts-using-rest-api.md)
- [Felsöka problem med SIEM-verktygsintegrering](troubleshoot-siem.md)
