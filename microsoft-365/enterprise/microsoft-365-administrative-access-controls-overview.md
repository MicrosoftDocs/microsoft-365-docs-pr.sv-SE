---
title: Kontroller för administrativ åtkomst i Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Den här artikeln innehåller en översikt över kontroller för administrativ åtkomst och data kategorisering i Microsoft 365.
ms.openlocfilehash: 817a5907566435d021fe78d89b5c9476c04318d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332598"
---
# <a name="administrative-access-controls-in-microsoft-365"></a>Kontroller för administrativ åtkomst i Microsoft 365 

Microsoft har investerat i system och kontroller som automatiserar de flesta Microsoft 365-operationer samtidigt som det begränsar åtkomsten till kund innehållet via Microsoft. Människor styr tjänsten och program varan fungerar med tjänsten. Detta gör att Microsoft kan hantera Microsoft 365 på skala och hantera riskerna med interna hot för kund innehållet.

Som standard har Microsoft-tekniker inga stå för administratörs behörighet och ingen ständig åtkomst till kund innehåll i Microsoft 365. En Microsoft-tekniker kan ha begränsad, granskad och skyddad till gång till kundens innehåll under en begränsad tid. Access är bara när det behövs för tjänste åtgärder och endast när det godkänns av en medlem i Microsofts chefs hantering. För att få kund säkra kunder får kunden åtkomst godkännande till innehållet på Microsoft 365.

Microsoft tillhandahåller online tjänster med hjälp av flera former av moln leverans:

- **Offentliga moln:** Inkluderar multi-Tenant-versioner av Microsoft 365, Azure och andra tjänster i Nord Amerika, Sydamerika, Europa, Asien, Australien, etc.
- **Nationella moln:** Inkluderar alla suveräna och tredje parts drivna moln utanför USA (förutom dem som nämns ovan), till exempel Microsoft 365 i Kina (drivs av 21Vianet) och Microsoft 365 i Tyskland (drivs av Microsoft, men under en modell där en tysk data förvaltare, tyska telekom, styr och övervakar Microsofts åtkomst till kunddata och system som innehåller kunddata).
- **Statliga moln:** Innehåller Microsoft 365 och Azure-tjänster som är tillgängliga för kunder i USA.

I den här artikeln gäller följande för Microsoft 365-tjänster:

- [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)
- [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [OneDrive för företag](https://docs.microsoft.com/OneDrive/onedrive)
- [Skype för företag](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a>Microsoft 365 Access-kontroller

I syfte med åtkomst kontroll kategoriseras Microsoft 365-data som kunddata eller andra typer av data.

### <a name="customer-data"></a>Kunddata

Kunddata är alla data tillhandahålls av eller på uppdrag av en kund vid användning av Microsoft 365-tjänster. Det här är kund innehållet som skapas eller laddas upp direkt av Microsoft 365-användare, inklusive:

- E-postmeddelanden
- SharePoint Online-innehåll
- Snabb meddelanden
- Kalender objekt
- Dokumentationen
- Kontakter
- Specifik information för slutanvändare (EUII) (data som är unika för en användare eller som är länkad till en enskild användare, men som inte inkluderar kund innehåll)

### <a name="other-types-of-data"></a>Andra typer av data

Andra typer av data är:

- **Konto data:** Inkluderar administrativa uppgifter (information som tillhandahålls av administratörer när de loggar in eller köper tjänster) och betalnings uppgifter (information om betalnings instrument, till exempel kreditkorts uppgifter).
- **Identifierbar information från organisationen:** Inkluderar data som används för att identifiera en klient organisation, användnings data och inte länkas till en enskild användare eller ingår i kund innehållet.
- **Systemmetadata:** Innehåller tjänst loggar som innehåller konfigurations inställningar, system status, Microsoft IP-adresser och teknisk information om abonnemang och innehavare.

Microsoft har fastställt mekanismer för åtkomst kontroll för att säkerställa att ingen har godkänt åtkomst till kunddata eller åtkomst kontroll data. Åtkomst kontroll data hanterar åtkomst till andra typer av data eller funktioner i miljön, inklusive åtkomst till kund innehåll eller EUII, Microsoft-lösenord, säkerhets certifikat och andra säkerhetsrelaterade data. Åtkomst kontroll mekanismer skyddar också mot icke godkänd fysisk, logisk eller fjärråtkomst till Microsoft 365-produktions miljön.

Det finns tre kategorier av Access-kontroller som används av Microsoft för att använda Microsoft 365:

- Isolerings kontroller
- Personal kontroller
- Teknik kontroller

När de kombineras kan de här kontrollerna förhindra och upptäcka skadliga åtgärder i Microsoft 365. Utöver de isolerings-, personal-och teknik kontroller som används av Microsoft finns det en fjärde kategori med kontroller: de som implementeras av kunder.

Med Microsoft 365 kan du hantera data på samma sätt som data hanteras i lokala miljöer. Personen som registrerar sig för Microsoft 365 blir automatiskt global administratör. Den globala administratören har till gång till alla funktioner i hanterings portaler och kan:

- Skapa eller redigera användare
- Tilldela administratörs roller till andra
- Återställa användar lösen ord
- Hantera användar licenser
- Hantera domäner
- Godkänn begäranden för kund frågor

Vi rekommenderar att varje organisation konfigurerar minst två administratörs konton. För stora företags organisationer rekommenderar vi specialiserade administratörs konton med olika funktioner.

Information om hur du tilldelar administratörs roller och behörigheter finns i [tilldela administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) och [om administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="related-links"></a>Relaterade länkar

- [Isoleringskontroller](microsoft-365-isolation-controls.md)
- [Personalkontroller](microsoft-365-personnel-controls.md)
- [Teknik kontroller](microsoft-365-technology-controls.md)
- [Övervakning och granskning av åtkomstkontroller](microsoft-365-monitoring-and-auditing-access-controls.md)
- [Åtkomstkontroller för Yammer Enterprise](microsoft-365-yammer-enterprise-access-controls.md)
