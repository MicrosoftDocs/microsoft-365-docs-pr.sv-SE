---
title: Microsoft Information Protection i Microsoft 365.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: Implementera Microsoft Information Protection (MIP) som hjälper dig att skydda känslig information var du än befinner dig eller på språng.
ms.openlocfilehash: 5b9484826f0d3a297dae47c7d140d93297473023
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259304"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection i Microsoft 365.

>*[Licensiering för Microsoft 365 Säkerhetscenter och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implementera Microsoft Information Protection (MIP) som hjälper dig att upptäcka, klassificera och skydda känslig information var du än befinner dig eller på språng.

MIP-funktioner ingår i Microsoft 365 Efterlevnad och ger dig verktygen för att [känna till dina data](#know-your-data), [skydda dina data](#protect-your-data)och [förhindra dataförlust](#prevent-data-loss).

![Bild av hur MIP hjälper dig att upptäcka, klassificera och skydda känsliga data](../media/powered-by-intelligent-platform.png)

:::image type="content" source="../media/data-table1-4638524-new.png" alt-text="Känn till dina data":::

Information om hur du styr dina data finns i [Informationsstyrning i Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Var bekant med dina data

> [!NOTE]
> Information om omfattningen om hur du klassificerar och etiketterar data i Azure Purview, som för närvarande är i förhandsversion, finns i[ Märka innehållet i Azure Purview automatiskt](/azure/purview/create-sensitivity-label).
> 
> Publiceringsmeddelanden för Azure Purview finns i följande blogginlägg: [Microsoft Information Protection och Microsoft Azure Purview: Better Together](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481) och [Azure Purview på Ignite 2021](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919).

För att förstå datalandskapet och identifiera viktiga data i hybridmiljön använder du följande funktioner:

:::image type="content" source="../media/knowyourdata-new.png" alt-text="känn till dina data"::: 


|**Funktion**|**Vilka problem löser den?**|**Komma igång**|**Licensiering**|
|--|--|--|--|
|[Typer av känslig information](sensitive-information-type-entity-definitions.md)| Identifierar känsliga data med inbyggda eller anpassade reguljära uttryck eller en funktion, tillsammans med samarbetsbevis som innehåller nyckelord, konfidensnivåer och närhet. Använd känsliga informationstyper för att identifiera specifika typer av data i organisationen. Använd de förinställda känsliga informationstyperna för att hitta vanliga datatyper, till exempel passnummer. Skapa en anpassad informationstyp för att identifiera information som är unik för din miljö, t.ex. artikelnummer. | [Anpassa en förinställd typ av känslig information](customize-a-built-in-sensitive-information-type.md)| |
|[Utbildningsbara klassificerare (förhandsversion)](classifier-learn-about.md)| Klassificerar data åt dig med en av de inbyggda klassificerarna eller genom att du tränar en klassificerare med ditt eget innehåll. | [Kom igång med utbildningsbara klassificerare (förhandsversion)](classifier-get-started-with.md)| |
|[Dataklassificering](data-classification-overview.md) | Identifierar objekt som har en känslighetsetikett, en bevarandeetikett eller har klassificerats som en känslig informationstyp i organisationen och de åtgärder som användarna utför med dem.  | [Kom igång med innehållsutforskaren](data-classification-content-explorer.md)<br /><br /> [Kom igång med aktivitetsutforskaren](data-classification-activity-explorer.md)| |



## <a name="protect-your-data"></a>Skydda dina data

Om du vill använda flexibla skyddsåtgärder som inkluderar kryptering, åtkomstbegränsningar och visuella markeringar använder du följande funktioner:


:::image type="content" source="../media/protectyourdata-4638524-new.png" alt-text="Skydda dina data":::

|**Funktion**|**Vilka problem löser den?**|**Komma igång**|**Licensiering**|
|--|--|--|--|
|[Känslighetsetiketter](sensitivity-labels.md)| En lösning för alla program, tjänster och enheter som kan etikettera och skydda dina data när de färdas inom och utanför organisationen. <br /><br />Exempelscenario: [Använda och visa känslighetsetiketter i Power BI och skydda data när de exporteras](/power-bi/admin/service-security-apply-data-sensitivity-labels)|[Kom igång med känslighetsetiketter](get-started-with-sensitivity-labels.md) |
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| Identifierar, etiketterar och skyddar känslig information som finns i molnet. | [Upptäck, klassificera, etikettera och skydda känsliga och reglerade data som lagras i molnet](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Azure Information Protection-skanner för enhetliga etiketter](/azure/information-protection/deploy-aip-scanner)| Identifierar, etiketterar och skyddar känslig information som finns i lokala datalager | [Konfigurera och installera Azure Information Protection-skanner för enhetliga etiketter](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Aktivitetsutforskare]()||||


## <a name="transition-from-aip-to-mip"></a>Övergå från AIP till MIP
Den klassiska administrations- och klientversionen av Azure Information Protection tas bort tidigt nästa år. Vi rekommenderar att du går över till Microsoft Information Protection. Det innebär bland annat migrering av alla befintliga etiketter och principer. 

:::image type="content" source="../media/transition-aip2mip-4638524-new.png" alt-text="Övergå från AIP till MIP":::

## <a name="additional-capabilities"></a>Ytterligare funktioner
Microsoft 365 innehåller följande funktioner som skyddar data:

|**Funktion**|**Vilka problem löser den?**|**Komma igång**|
|--|--|--|
| Meddelandekryptering i Office 365 (OME) | Krypterar e-postmeddelanden och bifogade dokument som skickas till användare på olika enheter, så att endast behöriga mottagare kan läsa information som skickas via e-post. <br /><br /> Exempelscenario: Återkalla e-post som krypterats med Advanced Message Encryption | Konfigurera nya funktioner för meddelandekryptering |
| Kryptering med dubbla nycklar | Under alla förhållanden är det bara du som kan dekryptera skyddat innehåll. För att uppfylla gällande bestämmelser måste du ha krypteringsnycklar inom en geografisk gräns | Distribuera kryptering med dubbla nycklar |  
| Krypteringstjänst med kundnyckel | Skyddar mot att data visas av obehöriga system eller personer och kompletterar BitLocker-diskkryptering i Microsofts datacenter. | Konfigurera kundnyckeln för Office 365 |
| SharePoint Information Rights Management (IRM) | Skyddar SharePoint-listor och SharePoint-bibliotek när en användare checkar ut ett dokument så att endast behöriga användare kan visa och använda nedladdade filer enligt principer som du anger. | Konfigurera IRM (Information Rights Management) i SharePoint Online Administrationscenter |
| Rights Management-anslutningsprogram | Enbart skydd för befintliga lokala distributioner som använder Exchange eller SharePoint Server och File Classification Infrastructure (FCI) | Steg för att distribuera RMS-anslutningsprogram |



## <a name="prevent-data-loss"></a>Förhindra dataförlust

Använd följande funktioner för att förhindra att känslig information förs över av misstag:

:::image type="content" source="../media/dlp-4638524-new.png" alt-text="Förhindra dataförlust":::

|**Steg**|**Beskrivning**|**Mer information**|
|--|--|--|
|[Utforma DLP-principer](data-loss-prevention-policies.md)| Planera hur information ska identifieras (känslig informationstyp, etikett, annat) <br /><br /> Planera var principerna ska användas (tjänster, klientprogram, appar från tredje part) <br /><br /> Planera principtips och annat||
||||




|**Funktion**|**Vilka problem löser den?**|**Komma igång**|
|--|--|--|
|[Mer information om dataförlustskydd](dlp-learn-about-dlp.md)| Förhindrar oavsiktlig delning av känsliga objekt. | [Kom igång med DLP-standardprincipen](get-started-with-the-default-dlp-policy.md)|
|[Mer information om dataförlustskydd för slutpunkt](endpoint-dlp-learn-about.md)| Utökar DLP-funktionerna till objekt som används och delas på Windows 10-datorer. | [Komma igång med dataförlustskydd för slutpunkt](endpoint-dlp-getting-started.md)|
|[Läs mer om Microsofts Efterlevnadstillägg (förhandsversion)](dlp-chrome-learn-about.md) | Utökar DLP-funktionerna till webbläsaren Chrome | [Kom igång med Microsofts Efterlevnadstillägg (förhandsversion)](dlp-chrome-get-started.md)|
|[Mer information om Microsoft 365 lokal skanner för dataförlustskydd (förhandsversion)](dlp-on-premises-scanner-learn.md)|Utökar DLP-övervakning av filaktiviteter och skyddsåtgärder för dessa filer till lokala filresurser samt SharePoint-mappar och dokumentbibliotek.|[Kom igång med Microsoft 365 lokal skanner för dataförlustskydd (förhandsversion)](dlp-on-premises-scanner-get-started.md)|
|[Skydda känslig information i Teams-chatt och -kanalmeddelanden i Microsoft Teams](dlp-microsoft-teams.md) | Utökar vissa DLP-funktioner till Teams chatt- och kanalmeddelanden | [Läs mer om standardprincipen för dataförlustskydd i Microsoft Teams (förhandsversion)](dlp-teams-default-policy.md)| 


## <a name="additional-resources"></a>Ytterligare resurser

Många organisationer använder de här funktionerna för informationsskydd för att uppfylla datasekretessföreskrifter. För att hjälpa har vi utformat ett arbetsflöde som vägleder dig genom en hela processen för att planera och implementera funktioner i Microsoft 365, inklusive säker åtkomst, skydd mot hot, informationsskydd och datastyrning. Mer information finns i [Distribuera informationsskydd för föreskrifter för datasekretess med Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy). 

Om du dessutom vill planera en integrerad strategi för att implementera informationsskyddsfunktioner kan du ladda ned uppsättningen av bilder i *Microsoft 365 informationsskydd och efterlevnadsfunktioner*.  Du kan anpassa illustrationerna för eget bruk.

| Objekt | Beskrivning |
|:-----|:------------|
|[![Modellaffisch: Microsoft 365 illustrationer för informationsskydd och efterlevnadsfunktioner](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> [Ladda ned som PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)\| [Hämta som Visio](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Japanska[Ladda ned som PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)\| [Hämta som Visio](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> Uppdaterades: Oktober 2020|Innehåller: <ul><li>  Microsoft Informationsskydd och dataförlustskydd </li><li>Kvarhållningsprinciper och -etiketter </li><li>Informationsbarriärer</li><li>Kommunikationsefterlevnad</li><li>Hantering av insiderrisk</li><li>Datainmatning för tredje part</li>|

