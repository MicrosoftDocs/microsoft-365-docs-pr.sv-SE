---
title: Inställningar interaktion mellan Microsoft 365 grupper, Teams och SharePoint
ms.reviewer: ''
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
recommendations: false
description: Läs mer om interaktioner mellan inställningar Microsoft 365 grupper, Teams och SharePoint
ms.openlocfilehash: 14a21cd34fe38b47d93d0cbcec5e9cb2a3bc49c7
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539089"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Inställningar interaktion mellan Microsoft 365 grupper, Teams och SharePoint

Vissa inställningar för Microsoft 365-grupper, Microsoft Teams och SharePoint i Microsoft 365, särskilt relaterade till delning och grupp/grupp och SharePoint skapa webbplatser överlappar varandra. Den här artikeln innehåller beskrivningar av dessa interaktioner och metodtips för hur du arbetar med de här inställningarna.

![Venndiagram över SharePoint, Teams och grupper](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Effekterna av SharePoint i grupper och team

|SharePoint inställning|Beskrivning|Påverkan på Microsoft 365 grupper och Teams|Rekommendation|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Extern delning för organisation och webbplats|Avgör om webbplatser, filer och mappar kan delas med personer utanför organisationen.|Om SharePoint, grupper och Teams-inställningarna inte stämmer överens kan det hända att gäster i teamet blockeras från att komma åt webbplatsen, eller så kan oväntad extern åtkomst uppstå.|När du ändrar delningsinställningar markerar du Gruppinställningar, Teams inställningar SharePoint inställningar för gruppanslutna gruppwebbplatser.<br><br> Se [Samarbeta med gäster i ett team](./collaborate-as-team.md)|
|Tillåt/blockera domän|Tillåter eller förhindrar att innehåll delas med angivna domäner.|Grupper och Teams känner inte igen SharePoint tillåta eller blockera listor. Användare från domäner som inte är tillåtna SharePoint kan få åtkomst SharePoint webbplatser eller innehåll via ett team.|Hantera domänlistor för tillåtna/blockerade domäner för Azure AD SharePoint tillsammans. Skapa en organisationsomfattande styrningsprocess för att tillåta och blockera domäner.<br><br>Se [SharePoint domäninställningar och](/sharepoint/restricted-domains-sharing) Inställningar för Azure [AD-domän](/azure/active-directory/b2b/allow-deny-list)|
|Tillåt endast användare i vissa säkerhetsgrupper att dela externt|Anger säkerhetsgrupper som kan dela SharePoint, mappar och filer externt.|Den här inställningen hindrar inte teamägare från att dela team externt. Gruppgäster har åtkomst till den associerade SharePoint webbplatsen.||
|SharePoint för webbplatsdelning|Avgör vem som kan dela webbplatsen direkt utanför teammedlemskap. Det konfigureras av grupp- eller webbplatsägaren.|Den här inställningen påverkar inte teamet direkt, men det kan göra att användare läggs till på en webbplats och inte har åtkomst till själva teamet eller andra Teams resurser|Du kan använda den här inställningen för att begränsa delning av webbplatsen direkt och hantera webbplatsåtkomst via gruppen.|
|Låta användarna skapa webbplatser från SharePoint startsida och OneDrive|Anger om användare kan skapa nya SharePoint webbplatser.|Om den här inställningen är inaktiverad kan användare fortfarande skapa gruppanslutna gruppwebbplatser genom att skapa ett team.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Effekterna av gruppinställningar i grupper

|Microsoft 365 grupper|Beskrivning|Effekt på Teams|Rekommendation|
|:---------------------------|:----------|:--------------|:-------------|
|Namngivningsprinciper|Anger gruppens namnprefix och suffix och blockerade ord när en grupp skapas|Principer tillämpas för användare som skapar team.||
|Gruppgäståtkomst|Anger om personer utanför organisationen kan läggas till i grupper.|Om varken grupperna eller Teams gästdelningsinställningarna är inaktiverade kan teamet inte delas med gäster.|När du ändrar inställningar för gästdelning ska du kontrollera Teams, Grupper och den SharePoint är kopplad till teamet.<br><br> Se [Samarbeta med gäster i ett team](./collaborate-as-team.md)|
|Skapa grupp efter säkerhetsgrupp|Grupper kan endast skapas av medlemmar i en viss säkerhetsgrupp.|Användare som inte är medlemmar i säkerhetsgruppen kommer inte att kunna skapa ett team.|Se till att processen för att begära en grupp innehåller instruktioner för att begära ett team eller en SharePoint webbplats.|
|Förfalloprincip för grupp|Anger en tidsperiod efter vilken grupper som inte används aktivt kommer att tas bort automatiskt.|När gruppen tas bort, tas även gruppen och SharePoint webbplatsen bort. Innehåll som skyddas av bevarandeprinciper behålls.|Använd förfalloprinciper för att undvika utsmålning av oanvända team, grupper och webbplatser.|

## <a name="related-topics"></a>Relaterade ämnen

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)

[Samarbeta med personer utanför organisationen](./collaborate-with-people-outside-your-organization.md)

[Hantera webbplatsskapande i SharePoint](/sharepoint/manage-site-creation)