---
title: Hantering av arkivhandlingar i Microsoft 365
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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Med hantering av arkivhandlingar i Microsoft 365 kan du använda kvarhållningsscheman i en filplan som hanterar kvarhållning, arkivhandlingsdeklaration och borttagning.
ms.openlocfilehash: 853303dcaffcbacfcf805b8617b836254cf31ad8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245438"
---
# <a name="learn-about-records-management-in-microsoft-365"></a>Mer information om hantering av arkivhandlingar i Microsoft 365

>*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Organisationer av alla typer kräver en lösning för hantering av arkivhandlingar för att hantera regelverk, juridiska och affärskritiska arkivhandlingar i företagets data. Hantering av arkivhandlingar i Microsoft 365 hjälper en organisation att hantera sina juridiska åtaganden, ger möjlighet att visa regelefterlevnad och ökar effektiviteten med regelbunden disposition av objekt som inte längre måste behållas, inte längre har något värde eller inte längre krävs för affärsändamål.

Använd följande funktioner för att få stöd för din lösning för hantering av arkivhandlingar i Microsoft 365:

- **Märka innehåll som en arkivhandling**. Skapa och konfigurera kvarhållningsetiketter för att markera innehåll som en [arkivhandling](#records) som sedan kan tillämpas av användarna eller tillämpas automatiskt genom att identifiera känslig information, nyckelord eller innehållstyper.

- **Migrera och hantera dina kvarhållningskrav med en filplan**. Med hjälp av en [filplan](file-plan-manager.md) kan du ta med en befintlig kvarhållningsplan till Microsoft 365 eller skapa en ny för förbättrade hanteringsfunktioner.

- **Konfigurera inställningar för kvarhållning och borttagning med kvarhållningsetiketter**. Konfigurera [kvarhållningsetiketter](retention.md#retention-labels) med kvarhållningsperioder och -åtgärder baserat på olika faktorer som inkluderar datum då de senast ändrades eller skapades.

- **Starta olika kvarhållningsperioder när en händelse inträffar** med [händelsebaserad kvarhållning](event-driven-retention.md).

- **Granska och verifiera borttagning** med [borttagningsgranskning](disposition.md#disposition-reviews) och bevis på [borttagning av arkivhandlingar](disposition.md#disposition-of-records).

- **Exportera information om alla borttagna objekt** med [exportalternativet](disposition.md#filter-and-export-the-views).

- **Ange specifika behörigheter** för funktioner för arkivhandlingshanterare i organisationen för att [ha rätt åtkomst](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

Med de här funktionerna kan du införliva organisationens kvarhållningsscheman och -krav i en lösning för hantering av arkivhandlingar som hanterar kvarhållning, arkivhandlingsdeklaration och borttagning, för att stödja hela livscykeln för ditt innehåll.

Förutom onlinedokumentationen kan det vara bra att lyssna på [webbseminariuminspelningen](https://aka.ms/MIPC/Video-RecordsManagementWebinar) för hantering av arkivhandlingar och att ladda ned det tillhörande [fristående bildspelet med vanliga frågor och svar](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).

## <a name="records"></a>Arkivhandlingar

När innehåll deklareras som en arkivhandling:

- Begränsningar läggs på objekten när det gäller vilka [åtgärder som tillåts eller blockeras](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Ytterligare aktiviteter om objektet loggas.

- Du har bevis på borttagningen när objekten tas bort i slutet av kvarhållningsperioden.

Du använder [kvarhållningsetiketter](retention.md#retention-labels) för att markera innehåll som en **arkivhandling** eller en **regelbaserad arkivhandling**. Skillnaden mellan dessa två förklaras i nästa avsnitt. Du kan antingen publicera etiketterna så att användare och administratörer kan tillämpa dem manuellt på innehåll, eller så kan du tillämpa etiketterna automatiskt på innehåll som du vill markera som en arkivhandling eller en regelbaserad arkivhandling.

Genom att använda kvarhållningsetiketter för att deklarera arkivhandlingar kan du implementera en enda och konsekvent strategi för hantering av arkivhandlingar i Microsoft 365-miljön.

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Jämföra begränsningar för vilka åtgärder som tillåts eller blockeras

I följande tabell kan du se vilka begränsningar som sätts på innehåll på grund av att en standardkvarhållningsetikett används och kvarhållningsetiketter som markerar innehåll som en arkivhandling eller en regelbaserad arkivhandling. 

En standardkvarhållningsetikett har kvarhållningsinställningar och -åtgärder men markerar inte innehåll som en arkivhandling eller en regelbaserad arkivhandling.

>[!NOTE] 
> Tabellen innehåller kolumner för en låst och olåst arkivhandling, som gäller för SharePoint och OneDrive, men inte Exchange. Möjligheten att låsa och låsa upp en arkivhandling använder [versionshantering av arkivhandlingar](record-versioning.md) som inte stöds för Exchange-objekt. För alla Exchange-objekt som är markerade som en arkivhandling mappas därför beteendet till kolumnen **Arkivhandling – låst**, och kolumnen **Arkivhandling – olåst** är inte relevant.


|Åtgärd| Kvarhållningsetikett |Arkivhandling – låst| Arkivhandling – olåst| Regelbaserad arkivhandling |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Redigera innehåll|Tillåts | **Blockeras** | Tillåts | **Blockeras**|
|Redigera egenskaper, inklusive byta namn|Tillåts |Tillåts | Tillåts| **Blockeras**|
|Radera|Tillåts <sup>1</sup> |**Blockeras** |**Blockeras**| **Blockeras**|
|Kopiera|Tillåts |Tillåts | Tillåts| Tillåts|
|Flytta inom behållare <sup>2</sup>|Tillåts |Tillåts | Tillåts| Tillåts|
|Flytta mellan behållare <sup>2</sup>|Tillåts |Tillåts om aldrig olåst | **Blockeras** | **Blockeras**|
|Öppna/läsa|Tillåts |Tillåts | Tillåts| Tillåts|
|Ändra etikett|Tillåts |Tillåts – endast behållaradministratör | Tillåts – endast behållaradministratör| **Blockeras**
|Ta bort etikett|Tillåts |Tillåts – endast behållaradministratör | Tillåts – endast behållaradministratör| **Blockeras**

Fotnoter:

<sup>1</sup> Stöds av OneDrive och Exchange genom att behålla en kopia på en säker plats, men blockeras av SharePoint.

När du använder en kvarhållningsetikett på ett listobjekt som har en dokumentbilaga ärver inte dokumentet kvarhållningsinställningarna och kan tas bort från listobjektet. Om listobjektet däremot har deklarerats som en arkivhandling med en kvarhållningsetikett ärver dokumentbilagan kvarhållningsinställningarna och kan inte tas bort. 

<sup>2</sup> Behållare inkluderar SharePoint-dokumentbibliotek, OneDrive-konton och Exchange-postlådor.

>[!IMPORTANT] 
> Den viktigaste skillnaden för en regelbaserad arkivhandling är att ingen, inte ens en global administratör, kan ta bort etiketten när den har tillämpats på innehåll. 
>
> Kvarhållningsetiketter som konfigurerats för regelbaserade arkivhandlingar har också följande administratörsbegränsningar:
> - Kvarhållningsperioden kan inte göras kortare när etiketten har sparats, utan kan bara utökas.
> - De här etiketterna stöds inte av principer för automatisk etikettering, och måste tillämpas genom att använda [principer för kvarhållningsetiketter](create-apply-retention-labels.md). 
>
> En kvarhållningsetikett kan inte heller tillämpas på ett dokument som är utcheckat i SharePoint.
> 
> På grund av begränsningarna och åtgärder som inte går att ångra ska du vara säker på att du verkligen behöver använda regelbaserade arkivhandlingar innan du väljer det här alternativet för kvarhållningsetiketter. För att förhindra oavsiktlig konfiguration är det här alternativet inte tillgängligt som standard, utan måste först aktiveras med hjälp av PowerShell. Instruktioner finns i [Deklarera arkivhandlingar med hjälp av kvarhållningsetiketter](declare-records.md).

## <a name="configuration-guidance"></a>Konfigurationsvägledning

Se [Komma igång med hantering av arkivhandlingar](get-started-with-records-management.md). Den här artikeln innehåller information om prenumerationer, behörigheter och länkar till hela konfigurationsvägledningen för scenarier med hantering av arkivhandlingar.