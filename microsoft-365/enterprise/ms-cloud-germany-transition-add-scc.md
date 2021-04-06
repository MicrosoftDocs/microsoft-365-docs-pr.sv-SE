---
title: Information om eDiscovery-upplevelsen under migreringen från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Sammanfattning: eDiscovery-migreringssteg för migreringen från Microsoft Cloud Deutschland.'
ms.openlocfilehash: 16da6e6d1994ae107b62ff1f915454568a35344d
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592145"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a>Information om eDiscovery-upplevelsen under migreringen från Microsoft Cloud Deutschland
Följande avsnitt innehåller ytterligare information om eDiscovery-upplevelsen när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.

## <a name="ediscovery-administration-until-phase-4"></a>eDiscovery-administration fram till fas 4
Fram till fas 4 är Säkerhets- och efterlevnadscenter helt tillgängligt. Allt innehåll finns kvar i Microsoft Cloud Germany och kan hanteras av Säkerhets- och efterlevnadscenter för Microsoft Cloud Germany ( https://protection.office.de/) .

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a>eDiscovery-upplevelsen mellan fas 4 till slutet av fas 9
Från början av fas 4 tills fas 9 är slutförd kommer eDiscovery-sökningar att misslyckas eller returnera 0 resultat för SharePoint Online-, OneDrive för företag- och Exchange Online-platser som har migrerats.

> [!NOTE]
> Under migreringen kan kunder fortsätta att skapa ärenden, innehåll, sökningar och exporter i Säkerhets- [&,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)inklusive [Innehållssökning.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content) Men sökningar mot SharePoint Online-, OneDrive för företag- och Exchange Online-platser som har migrerats returnerar antingen 0 resultat eller resulterar i ett fel.

Om en sökning returnerar noll resultat eller ett fel under migreringen kan du vidta följande åtgärd för SharePoint Online: 
- Ladda ned webbplatser direkt från SharePoint Online- eller OneDrive för företag-webbplatsen genom att följa anvisningarna i Ladda ned filer och [mappar från OneDrive eller SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Den här metoden kräver administratörsbehörigheter för SharePoint Online eller skrivskyddsbehörigheter på webbplatsen.
- Om gränserna överskrids, vilket förklaras i Ladda ned filer och mappar från OneDrive eller [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)kan kunder använda synkroniseringsklienten för OneDrive för företag genom att följa vägledning i Synkronisera [SharePoint-](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)och Teams-filer med din dator.

- Mer information finns i [EDiscovery på plats i Exchange Server.](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery)


## <a name="ediscovery-administration-after-phase-9"></a>eDiscovery-administration efter fas 9

**Gäller för:** Alla kunder som använder eDiscovery

I fas 9 slutförs de sista stegen för att flytta över till det nya tyska datacentret. I den här fasen migreras alla återstående tjänstkomponenter. Efter fas 9 stöds inte längre användning av säkerhets- och efterlevnadscentret i Microsoft Cloud Germany (protection.office.de). Använd det nya [säkerhetscentret eller](https://security.microsoft.com/) [efterlevnadscentret i](https://compliance.microsoft.com/) stället. Alla data har migrerats till de nya administrationsportalerna. 

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
|  Alla SharePoint Online-, OneDrive för företag- och Exchange Online-platser har migrerats tillsammans med Säkerhets- och efterlevnadscenter (SCC). | All eDiscovery-aktivitet bör köras från den globala klientorganisationen. Sökningarna lyckas nu till 100 %. Eventuella fel bör följa vanliga supportkanaler. | Ingen |
||||

### <a name="ediscovery-retention-policy"></a>eDiscovery-bevarandeprincip
**Gäller för:**  Alla kunder som har tillämpat en bevarandeprincip som en del av före migreringen

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Ta bort bevarandeprinciper för hela organisationen som skapades före migreringen | Kunder kan ta bort de organisationsomfattande bevarandeprinciper som skapades under kundernas arbete före migreringen. | Ingen |
||||
