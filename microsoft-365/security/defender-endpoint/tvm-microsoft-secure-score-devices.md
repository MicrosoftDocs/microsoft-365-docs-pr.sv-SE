---
title: Microsoft Secure Score för enheter
description: Poängen för enheter visar den samlade säkerhetskonfigurationstillståndet för dina enheter i olika program, operativsystem, nätverk, konton och säkerhetskontroller.
keywords: Microsoft Secure Score för enheter, mdatp Microsoft Secure Score för enheter, secure score, konfigurationsresultat, hantering av hot och sårbarhet, säkerhetskontroller, förbättringsmöjligheter, poäng för säkerhetskonfiguration över tid, säkerhetskonfigurationsresultat, baslinje
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d9ccd4f7dcc8b1546772a756aaf850dadfc87905
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071786"
---
# <a name="microsoft-secure-score-for-devices"></a>Microsoft Secure Score för enheter

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hantering av hot och sårbarhet](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> Konfigurationsresultat är nu en del av hantering av hot och problem som Microsoft Secure Score för enheter.

Din poäng för enheter är synlig i instrumentpanelen [för hantering av hot och sårbarhet](tvm-dashboard-insights.md) i Microsoft Defender Säkerhetscenter. Ett högre Microsoft Secure Score för enheter innebär att dina slutpunkter är mer flexibel mot attacker mot hot om cyberhot. Den återspeglar den kollektiva säkerhetskonfigurationstillståndet för dina enheter i följande kategorier:

- Program
- Operativsystem
- Nätverk
- Konton
- Säkerhetskontroller

Välj en kategori för att gå till sidan [**Säkerhetsrekommendationer**](tvm-security-recommendation.md) och visa relevanta rekommendationer.

## <a name="turn-on-the-microsoft-secure-score-connector"></a>Aktivera Microsoft Secure Score-kopplingen

Vidarebefordra Microsoft Defender för Endpoint-signaler och ge Microsoft Secure Score insyn i enhetssäkerhet. Vidarebefordrade data lagras och bearbetas på samma plats som dina Microsoft Secure Score-data.

Det kan ta några timmar innan ändringarna har återspeglas i instrumentpanelen.

1. I navigeringsfönstret går du till **Avancerade**  >  **inställningar** 

2. Rulla ned till **Microsoft Secure Score** och ändra inställningen till **På**.

3. Välj **Spara inställningar**.

## <a name="how-it-works"></a>Så här fungerar det

>[!NOTE]
> Microsoft Secure Score för enheter stöder för närvarande konfigurationer som har ställts in via Grupprincip. På grund av det aktuella stödet för Intune kan konfigurationer som har konfigurerats via Intune visas som felkonfigurerade. Kontakta IT-administratören för att kontrollera den faktiska konfigurationsstatusen om din organisation använder Intune för säker konfigurationshantering.

Data i kortet Microsoft Secure Score för enheter är produkten av noggrann och pågående sårbarhetsidentifieringsprocess. Den sammanställs med kontinuerliga konfigurationsidentifieringsutvärderingar:

- Jämför insamlade konfigurationer med insamlade riktmärken för att upptäcka felkonfigurerade tillgångar
- Mappa konfigurationer till säkerhetsproblem som kan åtgärdas eller delvis åtgärdas (riskminskning)
- Samla in och underhålla bästa möjliga prestanda vid konfigurationer (leverantörer, säkerhetsflöden, interna forskningsteam)
- Samla in och övervaka ändringar av konfigurationstillståndet för säkerhetskontroller för alla tillgångar

## <a name="improve-your-security-configuration"></a>Förbättra din säkerhetskonfiguration

Förbättra säkerhetskonfigurationen genom att åtgärda problem från listan med säkerhetsrekommendationer. Samtidigt som du gör det förbättras ditt Microsoft Secure Score för enheter och din organisation blir mer flexibel mot hot och säkerhetsproblem mot cybersäkerhet.

1. Från kortet Microsoft Secure Score för enheter med instrumentpanelen för hot och sårbarhetshantering väljer du en av kategorierna. Du ser en lista med rekommendationer för den kategorin. Du kommer då till sidan [**Säkerhetsrekommendationer.**](tvm-security-recommendation.md) Om du vill se alla säkerhetsrekommendationer rensar du sökfältet när du kommer till sidan Säkerhetsrekommendationer.

2. Markera ett objekt i listan. Den utfällna panelen öppnas med information om rekommendationen. Välj **Alternativ för åtgärder.**

   ![Säkerhetskontroller relaterade rekommendationer om säkerhet](images/tvm_security_controls.png)

3. Läs beskrivningen för att förstå kontexten för problemet och vad du ska göra härnäst. Välj ett förfallodatum, lägg till anteckningar och välj Exportera alla åtgärdsaktivitetsdata i **CSV** så att du kan bifoga dem i ett e-postmeddelande för uppföljning.

4. **Skicka begäran**. Ett bekräftelsemeddelande visas om att åtgärden har skapats.
   ![Bekräftelse för att åtgärd har skapats](images/tvm_remediation_task_created.png)

5. Spara CSV-filen.
   ![Spara CSV-fil](images/tvm_save_csv_file.png)

6. Skicka ett uppföljande e-postmeddelande till IT-administratören och tillåt den tid som du har tilldelats för åtgärd för att spridas i systemet.

7. Gå tillbaka **till kortet Microsoft Secure Score för enheter** på instrumentpanelen. Antalet rekommendationer om säkerhetskontroller kommer att minska. När du **väljer Säkerhetskontroller** för  att gå tillbaka till sidan Säkerhetsrekommendationer visas inte objektet som du har adresserat längre. Ditt Microsoft Secure Score för enheter bör öka.

>[!IMPORTANT]
>Du kan förbättra utvärderingsfrekvensen för sårbarhet genom att ladda ned följande obligatoriska säkerhetsuppdateringar och distribuera dem i nätverket:
>- 19H1-kunder | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)
>- RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
>- RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
>- RS3-| [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
>
>Så här laddar du ned säkerhetsuppdateringarna:
>1. Gå till [Microsoft Update-katalogen.](https://www.catalog.update.microsoft.com/home.aspx)
>2. Key-in the security update KB number that you need to download, then click **Search**.  

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över hot- och sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)
- [Instrumentpanelen](tvm-dashboard-insights.md)
- [Exponeringsresultat](tvm-exposure-score.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)
