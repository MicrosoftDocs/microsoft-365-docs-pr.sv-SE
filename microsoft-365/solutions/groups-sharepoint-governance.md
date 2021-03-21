---
title: Interaktion mellan inställningar mellan Microsoft 365-grupper och SharePoint
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Läs mer om interaktioner mellan inställningar mellan Microsoft 365-grupper och SharePoint
ms.openlocfilehash: e1aeaca792fb551de503bd4c68256ccf14f45022
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921042"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Interaktion mellan inställningar mellan Microsoft 365-grupper och SharePoint

Vissa inställningar för Microsoft 365-grupper och SharePoint i Microsoft 365, särskilt relaterade till delning, grupp- och gruppwebbplatsskapande, överlappar med varandra. Den här artikeln innehåller beskrivningar av dessa interaktioner och metodtips för hur du arbetar med de här inställningarna.

![Venndiagram över funktioner i SharePoint, Yammer och grupper](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Effekterna av SharePoint-inställningar i Microsoft 365-grupper

|SharePoint-inställning|Beskrivning|Påverka Microsoft 365-grupper|Rekommendation|
|:-----------------|:----------|:-----------------------------|:-------------|
|Extern delning för organisation och webbplats|Avgör om webbplatser, filer och mappar kan delas med personer utanför organisationen.|Om inställningarna för SharePoint och grupper inte matchar kan gäster i gruppen blockeras från att komma åt webbplatsen, eller också kan extern åtkomst vara tillgänglig på webbplatsen men inte i gruppen.|När du ändrar inställningarna för delning ska du kontrollera både gruppinställningar och SharePoint-webbplatsinställningar för gruppanslutna gruppwebbplatser.<br><br>Se [Samarbeta med gäster på en webbplats.](./collaborate-in-site.md)|
|Tillåt/blockera domän|Tillåter eller förhindrar att innehåll delas med angivna domäner.|Grupper känner inte igen tillåta- eller blockeringslistor i SharePoint. Användare från domäner som inte är tillåtna i SharePoint kan få åtkomst till SharePoint via en grupp.|Hantera domänlistor för tillåtna/blockerade domäner för Azure AD och SharePoint tillsammans. Skapa en organisationsomfattande styrningsprocess för att tillåta och blockera domäner.<br><br>Se [SharePoint-domäninställningar och](/sharepoint/restricted-domains-sharing) [Azure AD-domäninställningar](/azure/active-directory/b2b/allow-deny-list)|
|Tillåt endast användare i vissa säkerhetsgrupper att dela externt|Anger säkerhetsgrupper som kan dela webbplatser, mappar och filer externt.|Den här inställningen påverkar inte gruppägare som delar grupper externt. Gruppgäster har åtkomst till den associerade SharePoint-webbplatsen.||
|Delningsinställningar för SharePoint-webbplatser|Avgör vem som kan dela webbplatsen direkt utanför gruppmedlemskap. Detta konfigureras av gruppen eller webbplatsägaren.|Den här inställningen påverkar inte gruppen direkt, men det kan tillåta att användare läggs till på en webbplats och inte har åtkomst till andra gruppresurser|Du kan använda den här inställningen för att begränsa delning av webbplatsen direkt och hantera webbplatsåtkomst via gruppen.|
|Låta användare skapa webbplatser från startsidan för SharePoint och OneDrive|Anger om användare kan skapa nya SharePoint-webbplatser.|Om den här inställningen är inaktiverad kan användare fortfarande skapa gruppanslutna gruppwebbplatser genom att skapa en grupp.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Effekterna av inställningen Microsoft 365-grupper i SharePoint

|Inställning för Microsoft 365-grupper|Beskrivning|Effekt på SharePoint|Rekommendation|
|:---------------------------|:----------|:-------------------|:-------------|
|Namngivningsprinciper|Anger gruppens namnprefix och suffix och blockerade ord när en grupp skapas|Principer tillämpas för användare som skapar gruppanslutna gruppwebbplatser, men inte kommunikationswebbplatser eller webbplatser med andra mallar.|Skapa separata namngivningsvägledning för kommunikationswebbplatser om det behövs.|
|Gruppgäståtkomst|Anger om personer utanför organisationen kan läggas till i grupper.|Om inställningarna för SharePoint och grupper inte matchar kan gäster i gruppen blockeras från att komma åt webbplatsen, eller också kan extern åtkomst vara tillgänglig på webbplatsen men inte i gruppen.|När du ändrar inställningarna för delning ska du kontrollera både gruppinställningar och SharePoint-webbplatsinställningar för gruppanslutna gruppwebbplatser.<br><br>Se [Samarbeta med gäster på en webbplats](./collaborate-in-site.md)|
|Skapa grupp efter säkerhetsgrupp|Grupper kan endast skapas av medlemmar i en viss säkerhetsgrupp.|Användare som inte är medlemmar i säkerhetsgruppen kommer inte att kunna skapa en gruppansluten gruppwebbplats.|Se till att processen för att begära en grupp innehåller instruktioner för att begära en webbplats.|
|Förfalloprincip för grupp|Anger en tidsperiod efter vilken grupper som inte används aktivt kommer att tas bort automatiskt.|När gruppen tas bort tas den associerade SharePoint-webbplatsen också bort. Innehåll som skyddas av bevarandeprinciper behålls.|Använd förfalloprinciper för att undvika utsmålning av oanvända grupper och webbplatser.|

## <a name="related-topics"></a>Relaterade ämnen

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)

[Samarbeta med personer utanför organisationen](./collaborate-with-people-outside-your-organization.md)

[Hantera webbplatsskapande i SharePoint](/sharepoint/manage-site-creation)