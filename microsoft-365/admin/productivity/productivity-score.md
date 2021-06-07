---
title: Microsoft produktivitetspoäng
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Lär dig hur Microsoft Productivity Score återspeglar mått för personer och teknikupplevelser och jämför med organisationer av liknande storlek.
ms.openlocfilehash: 0735fb6d47b475146deade6ab3ca2f8d24ec27a7
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779680"
---
# <a name="microsoft-productivity-score"></a>Microsoft produktivitetspoäng 

Produktivitetspoäng stödjer resan till digital transformation med insikter om hur din organisation använder Microsoft 365 och de tekniska upplevelser som stödjer den. Din organisations poäng speglar personer och tekniska upplevelsemätningar och kan jämföras med riktmärken från organisationer som har liknande storlek som din.

Det tillhandahåller:

- **Mått** för att se var du befinner dig på din resa för digital transformation.
- **Insikter** om data för att hjälpa dig att identifiera möjligheter för att förbättra produktiviteten och tillfredsställelsen i din organisation.
- **Rekommenderade åtgärder** du kan vidta för att hjälpa din organisation använda Microsoft 365-produkter effektivt.

Vi tillhandahåller mått, insikter och rekommendationer på två områden: 

- **Personupplevelser:** kvantifierar hur organisationen fungerar med Microsoft 365-kategorier, t. ex. samarbete, mobilitet, kommunikation, möten och samarbete.  

    För var och en av de nämnda kategorierna tittar vi på offentlig forskning för att identifiera bästa praxis och tillhörande fördelar i form av organisationens effektivitet. Till exempel: Forrester research visar att när personer samarbetar och delar innehåll i molnet (istället för bifogade filer med e-post) kan de spara upp till 100 minuter i veckan. Dessutom kan vi kvantifiera användningen av dessa metoder i din organisation så att du kan se var du är på din resa för digital transformation. 

- **Teknikupplevelser:** din organisations produktivitet beror på pålitlig och högpresterande teknik samt effektiv användning av Microsoft 365. [Slutpunktsanalys](https://aka.ms/endpointanalytics) hjälper dig att förstå hur din organisation kan påverkas av prestanda och problem med din maskinvara och programvara. Microsoft 365-appar kan hjälpa dig att förstå om enheterna i din organisation kör Microsoft 365-appar på rekommenderade kanaler.

## <a name="before-you-begin"></a>Innan du börjar

Se [Vad är Slutpunktsanalys](/mem/analytics/overview) för en översikt och information om förutsättningar. Om du vill veta mer om Microsoft 365 nätverksanslutningsinsikter läser du [översikt över nätverksanslutning](../../enterprise/microsoft-365-networking-overview.md).

För data över personupplevelser måste du ha en Microsoft 365 for Business- eller Office 365 för Enterprise-prenumeration. Om du vill lägga till en slutpunktsanalys för din klientorganisation måste du lägga till Microsoft Intune i prenumerationen. Intune hjälper dig att skydda din organisations data genom att hantera enheter och appar. När du har Intune kan du aktivera slutpunktsanalys i Intune-upplevelsen. Mer information om Microsoft Intune finns i [dokumentation om Microsoft Intune](/mem/intune/). 

> [!NOTE]
> En licens för Microsoft Workplace Analytics krävs inte för att få funktionen produktivitetspoäng.

Produktivitetspoäng är endast tillgängligt i Microsoft 365 Admin Center och kan bara nås av IT-personal som har någon av följande roller:  

- Global administratör
- Exchange-administratörer
- SharePoint-administratör
- Skype för företag-administratör
- Teams-administratör
- Global läsare
- Rapportläsare
- Sammanfattningsrapporter för användning

> [!NOTE]
> Endast en IT-professionell med rollen som global administratör kan registrera sig eller välja en klientorganisation för produktivitetspoäng.

Den rollbaserade åtkomstkontrollmodellen för Productivity Score hjälper organisationer att föra arbetet med digitala omvandlingar vidare med Microsoft 365 genom att ge flexibiliteten att tilldela roller till IT-personal inom en organisation.

Microsoft strävar efter att skydda den personliga integriteten. I den här [sekretessdokumentet](privacy.md)  beskrivs de kontroller vi tillhandahåller dig, som din organisations IT-administratör, för att säkerställa att informationen är åtgärdbar utan att äventyrar ditt förtroende för Microsoft.

Du kan komma åt upplevelsen från Startsida för Microsoft 365 Admin under **Rapporter** > **Produktivitetspoäng**.
  
## <a name="how-the-score-is-calculated"></a>Så beräknas din poäng

Produktivitetspoängen baseras på de kombinerade poängen i kategorierna person- och teknikupplevelser. Varje kategori viktas lika med totalt 100 poäng. Den högsta möjliga produktivitetspoängen är 800.

### <a name="score-categories"></a>Poängkategorier 

- Kommunikation (100 poäng)
- Möten (100 poäng)
- Samarbetsinnehåll (100 poäng)
- Samarbete (100 poäng)
- Mobilitet (100 poäng)
- Slutpunktsanalys (100 punkter)
- Nätverksanslutning (100 poäng)
- Hälsa för Microsoft 365-applikationer (100 poäng)
- **Totalt antal möjliga = 800 poäng**
 
I varje poängkategori kvantifierar vi de nyckelindikatorerna för hur din organisation använder Microsoft 365 i resan mot digital transformation. Vi tillhandahåller 28-dagars och 180-dagars vyer av nyckelaktiviteter. Vi tillhandahåller även stödjande mått som inte ingår i poängberäkningen men som är viktigt för att hjälpa dig att identifiera underliggande användningsstatistik och konfigurationer som du kan adressera.

### <a name="products-included-in-productivity-score"></a>Produkter som ingår i produktivitetspoängen 

Produktivitetspoäng inkluderar data från Exchange, SharePoint, OneDrive, Teams, Word, Excel, PowerPoint, OneNote, Outlook, Yammer och Skype.

Din organisations poäng uppdateras dagligen och återspeglar användaråtgärderna som slutfördes under de senaste 28 (inklusive dagens datum).

## <a name="interpreting-your-organizations-productivity-score"></a>Tolkar din organisations produktivitetspoäng 

På Startsidan för Produktivitetspoäng visas din organisations totala poäng och poänghistorik och huvudsaklig insikt för varje kategori.

:::image type="content" source="../../media/prodscore-landing.png" alt-text="Sidan för Produktivitetspoäng i Rapporter.":::

**Din organisations poäng** visas som ett procentvärde och i poäng. Du kan se dina poäng i täljaren och största möjliga poäng i nämnaren.

**Riktmärke för motpart** tillåter dig att jämföra din organisations poäng med organisationer som din. Riktmärke för motpart för personupplevelsekategorier beräknas som medelvärdet av mått i en uppsättning liknande organisationer. Organisationsuppsättningen består av organisationer i din region med ett liknande antal licensierade användare, licenser, branscher och innehar Microsoft 365.

> [!NOTE]
> Microsoft använder interna data för att fastställa vilken bransch en organisation mappar till. Klientorganisationer i en överordnad organisation mappas till samma bransch som den överordnade organisationen. Organisationer kan inte visa eller ändra branschmappningar.

Slutpunktsanalys för riktmärke för motpart inkluderar mål för uppstartprestanda för enhet och rekommenderad programvarukonfiguration utifrån aggregerade medianvärden för alla klientorganisationer.

För nätverksanslutningar är det rekommenderade riktmärket 80 poäng.

I avsnittet **Detaljnivå för poäng** får du en nedbrytning av din Produktivitetspoäng med riktmärken efter områden för person- och teknikupplevelser.

Poänghistorik visas hur poängen i varje kategori har förändrats under de senaste 6 månaderna.

Områden för **Personupplevelser** och **Teknikupplevelser** innehåller primärinsikter för kategorierna i dessa områden. Du kan klicka på varje kategori för att se djupare insikter.

## <a name="category-details-pages"></a>Sidor med kategoriinformation

På sidan för varje kategoriinformation visas primär information och stödjande mått samt relaterade forskning och åtgärder som du kan vidta för att driva förändringar i organisationen. Forskning stödjer vikten och motiveringen bakom primärinsikterna för respektive kategori. Om du vill ha mer information [läs Forrester-rapporten](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

Detaljsidorna är:
- [Innehållssamarbete – personupplevelser](content-collaboration.md)
- [Kommunikation – personupplevelser](communication.md)
- [Möten – personupplevelser](meetings.md)
- [Mobilitet – personupplevelser](mobility.md)
- [Samarbete – personupplevelser](teamwork.md)
- [Hälsa för Microsoft 365-applikationer – teknikupplevelser](apps-health.md)
- [Slutpunktsanalys](/mem/analytics/productivity-score)

## <a name="business-continuity-special-report"></a>Särskild rapport om affärskontinuitet

Rapporten om affärskontinuitet är en tidsbegränsad Workplace insiktsrapport som är tillgänglig för alla Microsoft 365-kunder och som hjälper dem att vägleda sina organisationer under denna utmanande tid.  

Denna rapport hjälper organisationer förstå: 

- Hur samarbete och kommunikation påverkas av övergången till distansarbete. 

- Effekten på balans mellan arbete och fritid när personer anpassar sig till att arbeta hemifrån. 

- Om distansmöten stödjer effektivt beslutsfattande.

[Läs mer om rapporten om affärskontinuitet](/Workplace-Analytics/tutorials/bcrps)

[Läs mer om Microsoft Graph](/graph/)

> [!NOTE]
> Användare har också möjlighet att få produktivitetsinsikter från [MyAnalytics.instrumentpanelen](/workplace-analytics/myanalytics/use/dashboard-2).


## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Dela med dig av dina tankar om Produktivitetspoäng och idéer om hur den kan förbättras. Använd avsnittet **Feedback** i produkten och/eller kontakta teamet för Produktivitetspoäng på prodscorefeedback@microsoft.com.

## <a name="related-content"></a>Relaterat innehåll

[Övervaka Microsoft 365-aktivitet med hjälp av rapporter](../../admin/activity-reports/activity-reports.md)(artikel)\
[Aktivera Microsoft 365 användningsanalyser](../../admin/usage-analytics/enable-usage-analytics.md) (artikel)\
[Översikt över administrationscenter för Microsoft 365](../../business-video/admin-center-overview.md) (video)