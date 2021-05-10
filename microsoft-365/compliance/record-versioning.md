---
title: Använd versionshantering för att uppdatera arkivhandlingar som lagras i SharePoint eller OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Läs mer om arkivhandlingar som hjälper dig att implementera en lösning för hantering av arkivhandlingar i Microsoft 365.
ms.openlocfilehash: 5c828f06f2ce9e2bd18869f897f1f372c1a62f21
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "52162605"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a>Använd versionshantering för att uppdatera arkivhandlingar som lagras i SharePoint eller OneDrive

>*[Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

>[!NOTE] 
> Eftersom regelbaserade arkivhandlingar blockerar redigering är inte versionshantering tillgänglig för regelbaserade arkivhandlingar.

Möjligheten att markera ett dokument som en [arkivhandling](records-management.md#records) och begränsa åtgärder som kan utföras för den är ett viktigt mål för alla lösningar för hantering av arkivhandlingar. Dock kan det även behövas samarbete för att skapa senare versioner.

Du kan till exempel markera ett säljavtal som en arkivhandling, men sedan måste du uppdatera avtalet med nya villkor och markera den senaste versionen som en ny arkivhandling samtidigt som du behåller den tidigare versionen. För de här typerna av scenarier har SharePoint och OneDrive stöd för *versionshantering av arkivhandlingar*. Mappar i OneNote-anteckningsböcker har inte stöd för versionshantering av arkivhandlingar.

Om du vill använda versionshantering för arkivhandlingar [namnger du först dokumentet och markerar det som en arkivhandling](declare-records.md). I det här skedet visas en dokumentegenskap som kallas *Arkivhandlingsstatus* bredvid bevarandeetiketten och den första statusen är **Låst**. 

Nu kan du göra följande:

  - **Redigera kontinuerligt och behåll enskilda versioner av dokumentet som arkivhandlingar genom att låsa upp och låsa egenskapen Arkivhandlingsstatus.** Endast när egenskapen **Arkivhandlingsstatus** är inställd på **Låst** kan en ny version av arkivhandlingen behållas. Genom att växla mellan låsta och olåsta dokument minskar risken att onödiga versioner och kopior behålls av dokumentet.

  - **Lagra arkivhandlingarna automatiskt i en lagringsplats för arkivhandlingar på plats inom webbplatssamlingen.** Varje webbplatssamling i SharePoint och OneDrive bevarar innehållet i sitt bibliotek för bevarande av dokument. Arkivhandlingsversioner lagras i mappen Arkivhandlingar i det här biblioteket.

  - **Bevara ett evighetsdokument som innehåller alla versioner.** Som standard har varje SharePoint- och OneDrive-dokument en versionshistorik tillgänglig på objektmenyn. I den här versionshistoriken kan du enkelt se vilka versioner som är arkivhandlingar och visa dessa dokument.

> [!TIP]
> När du använder versionshantering för arkivhandlingar med en bevarandeetikett som har en borttagningsåtgärd kan du konfigurera bevarandeinställningen **Starta bevarandetiden baserat på:** till **När objekt har etiketter**. Med den här etikettinställningen återställs bevarandetidens början för varje ny arkivhandlingsversion, vilket säkerställer att äldre versioner tas bort innan nyare versioner.

Versionshantering för arkivhandlingar är automatiskt tillgängligt för alla dokument som har en bevarandeetikett som markerar objektet som en arkivhandling. När en användare visar dokumentegenskaperna med hjälp av informationsfönstret kan de växla **Status** från **Låst** till **Olåst**. Den här åtgärden skapar en arkivhandling i mappen Arkivhandlingar i biblioteket för bevarande av dokument, där den finns i resten av bevarandeperioden. 

Även om dokumentet är olåst kan alla användare med standardredigeringsbehörighet redigera filen. Användare kan dock inte ta bort filen eftersom det fortfarande är en arkivhandling. När redigeringen är klar kan en användare sedan växla **Status** från **Olåst** till **Låst**, vilket förhindrar ytterligare redigeringar när denna status har valts.
<br/><br/>

![Egenskapen arkivhandlingsstatus på dokumentet som taggats som arkivhandling](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a>Låsa och låsa upp en arkivhandling

När en bevarandeetikett som markerar innehåll som en arkivhandling tillämpas på ett dokument kan alla användare med behörigheten Delta eller mer begränsad behörighetsnivå låsa upp eller låsa en olåst arkivhandling.
<br/><br/>

![Status visar att arkivhandlingsdokumentet är olåst](../media/recordversioning9.png)

När en användare låser upp en arkivhandling sker följande åtgärder:

1. Om den aktuella webbplatssamlingen inte har ett bibliotek för bevarande av dokument skapas ett sådant.

2. Om biblioteket för bevarande av dokument inte har någon Arkivhandlingar-mapp skapas en sådan.

3. Åtgärden **Kopiera till** kopierar den senaste versionen av dokumentet till mappen Arkivhandlingar. Åtgärden **Kopiera till** inkluderar bara den senaste versionen och inga tidigare versioner. Det kopierade dokumentet anses nu vara en arkivhandlingsversion av dokumentet och filnamnet har formatet: \[Rubrik GUID version\#\]

4. Kopian som skapas i mappen Arkivhandlingar läggs till i versionshistoriken för det ursprungliga dokumentet och i den här versionen visas ordet **Arkivhandling** i kommentarsfältet.

5. Originaldokumentet är en ny version som kan redigeras, men inte tas bort. Kolumnen Dokumentbibliotek **Objektet är en arkivhandling** visar fortfarande värdet **Ja** eftersom dokumentet fortfarande är en arkivhandling, även om det nu kan redigeras.

När en användare låser en arkivhandling kan det ursprungliga dokumentet inte redigeras igen. Men det är åtgärden att låsa upp en arkivhandling som kopierar en version till mappen Arkivhandlingar i biblioteket för bevarande av dokument.

## <a name="record-versions"></a>Arkivhandlingsversioner

Varje gång en användare låser upp en arkivhandling kopieras den senaste versionen till biblioteket för bevarande av dokument och den versionen innehåller värdet för **Arkivhandling** i fältet **Kommentarer** i versionshistoriken.
<br/><br/>

![Arkivhandling som visas i biblioteket för bevarande av dokument](../media/recordversioning10.png)

Om du vill visa versionshistoriken markerar du ett dokument i dokumentbiblioteket och klickar sedan på **Versionshistorik** i objektmenyn.

## <a name="where-records-are-stored"></a>Var arkivhandlingar lagras

Arkivhandlingar lagras i mappen Arkivhandlingar i biblioteket för bevarande av dokument i webbplats på översta nivån i webbplatssamlingen. I det vänstra navigeringsfältet på webbplatsen på översta nivån väljer du **Webbplatsinnehåll** för\> **bibliotek för bevarande av dokument**.
<br/><br/>

![Bibliotek för bevarande av dokument](../media/recordversioning11.png)

<br/><br/>

![Mappen Arkivhandlingar i biblioteket för bevarande av dokument](../media/recordversioning12.png)

Mer information om hur biblioteket för bevarande av dokument fungerar finns i [Hur bevarande fungerar för SharePoint och OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).

## <a name="searching-the-audit-log-for-record-versioning-events"></a>Söka i granskningsloggen efter händelser för versionshantering av arkivhandlingar

Åtgärderna för att låsa och låsa upp arkivhandlingar loggas i granskningsloggen. Från **Fil- och sidaktiviteter** väljer du **Status för arkivhandlingar ändrad till låst** och **Status för arkivhandlingar ändrad till olåst**.

Mer information om hur du söker efter de här händelserna finns [Söka i granskningsloggen i Säkerhets- och efterlevnadscenter](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Nästa steg

Fler scenarier som stöds av hantering av arkivhandlingar hittar du här: [Vanliga scenarier för hantering av arkivhandlingar](get-started-with-records-management.md#common-scenarios-for-records-management).