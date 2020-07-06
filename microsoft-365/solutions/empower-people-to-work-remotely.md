---
title: Underlätta för distansarbetare med Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/08/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Konfigurera säkerhets- och tjänstinfrastrukturen som gör att dina arbetare kan arbeta på distans på valfri plats och när som helst.
ms.openlocfilehash: d4dded6c08e665a2756c45659f179e8252fcacc1
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844876"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Underlätta för distansarbetare med Microsoft 365

Ditt företag kan behöva upprätta säker åtkomst till organisationens lokala och molnbaserade information, verktyg och resurser för anställda som arbetar hemifrån. Att låta arbetarna arbeta utanför kontoret är viktigt för många organisationer för att:

- Spara på kontorsutrymme.
- Anställa och behålla arbetare som inte vill omlokalisera.
- Minska pendlingstid för arbetare vilket ger de mer tid att vara produktiva och kunna utföra stressminskande aktiviteter utanför arbetet.

Microsoft 365 har förmågan att låta dina medarbetare att arbeta på distans.

![Underlätta för distansarbetare med Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)


| | |
|:-------|:-----|
| Ansluten | Oavsett tid och plats kan distansarbetare komma åt: <ul><li>Molnbaserade tjänster och data i din Microsoft 365-prenumeration. </li><li>Organisationsresurser av samma slag som finns att tillgå med programdatacentraler på plats.</li></ul> |
| Säker | Inloggningarna skyddas med multifaktorautentisering (MFA) och inbyggda säkerhetsfunktioner i Microsoft 365 och Windows 10 skyddar mot skadlig programvara, skadliga attacker och dataförluster. |
| Hanteras | Din distansarbetares enheter kan hanteras från molnet med säkerhetsinställningar, tillåtna appar och för att kräva överensstämmelse med systemsäkerheten. |
| Samarbetsvilliga och produktiva | Dina distansarbetare kan vara lika produktiva som på plats på ett mycket samarbetande sätt med: <ul><li>Onlinemöten och chattsessioner med Teams. </li><li>Delade arbetsytor för molnbaserad fillagring med global tillgänglighet och samarbete i realtid med SharePoint och OneDrive. </li><li>Delade uppgifter och arbetsflöden för att dela upp arbetet och få saker gjorda. </li></ul> |
|||

För smidig inloggning lokalt bör dina användarkonton i Active Directory Domain Services (AD DS) synkroniseras med Azure Active Directory (Azure AD). För att skydda dina Windows 10-enheter bör de registreras i Intune. Här är en övergripande vy över infrastrukturen.

![Grundläggande infrastruktur för distansarbetare som använder Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Använd dessa Microsoft 365-funktioner för att uppfylla de här kriterierna för distansarbete.

| Resurs eller funktion | Beskrivning | Licensiering |
|:-------|:-----|:-------|
| MFA som förstärks med säkerhetsstandarder   | Skydda er mot identitetsstölder och komprometterade enheter genom att kräva en andra form av autentisering vid inloggning. Säkerhetsstandarderna kräver MFA för alla användarkonton.   | Microsoft 365 E3 och E5 |
| MFA som förstärks med villkorsstyrd åtkomst| Använd villkorsstyrda åtkomstprinciper för att kräva MFA baserat på egenskaperna för inloggningen.    | Microsoft 365 E3 och E5 | 
| MFA som förstärks med riskbaserad villkorsstyrd åtkomst   | Använd Azure Advanced Threat Protection för att kräva MFA baserat på risken som är kopplad till användarens inloggning. | Microsoft 365 E5 eller E3 med Azure AD Premium P2-licenser | 
| Självbetjäning för återställning av lösenord (SSPR)    | Låt användarna återställa eller låsa upp sina lösenord och konton.  | Microsoft 365 E3 och E5 |
| Azure Active Directory Application Proxy    | Tillhandahåll säker fjärråtkomst till webbaserade program som finns på intranätsservrar.   | För detta krävs en separat, betald Azure-prenumeration |
| Azure Point-to-Site VPN   | Skapa en säker anslutning från en distansarbetares enhet till ert intranät via ett virtuellt Azure-nätverk.   | För detta krävs en separat, betald Azure-prenumeration |
| Windows Virtual Desktop   | Underlätta för distansarbetare som bara kan använda privata och ohanterade enheter med hjälp av virtuella skrivbord som körs i Azure. | För detta krävs en separat, betald Azure-prenumeration |
| Fjärrskrivbordstjänster (RDS) | Låt medarbetarna ansluta till Windows-baserade datorer på intranätet. | Microsoft 365 E3 och E5 | 
| Gateway för fjärrskrivbordstjänster   | Kryptera kommunikationen och hindra värddatorerna för fjärrskrivbordstjänsterna från att exponeras direkt på internet. | För detta krävs separata Windows Server-licenser |
| Microsoft Intune | Hantera enheter och program.   | Microsoft 365 E3 och E5 | 
| Konfigurationshanteraren | Hantera programvaruinstallationer, uppdateringar och inställningar på dina enheter | För detta krävs separata licenser för Konfigurationshanteraren |
| Desktop Analytics | Avgör uppdateringsberedskapen hos dina Windows-klienter.   | För detta krävs separata licenser för Konfigurationshanteraren |
| Windows Autopilot | Förinstallera och konfigurera nya Windows 10-enheter för effektiv användning.   | Microsoft 365 E3 och E5 |
| Microsoft Teams, Exchange Online, SharePoint Online och OneDrive, Microsoft 365 Apps, Microsoft Power Platform, Yammer, Power Apps | Skapa, kommunicera och samarbeta. | Microsoft 365 E3 och E5 |
||||

Följ dessa steg för att skydda och optimera åtkomsten till organisationens servrar, data och molntjänster och för att maximera produktiviteten för medarbetarna.

1. [Öka inloggningssäkerheten med MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Ge fjärråtkomst till lokala appar och tjänster](empower-people-to-work-remotely-remote-access.md)
3. [Distribuera säkerhets- och efterlevnadstjänster](empower-people-to-work-remotely-security-compliance.md)
4. [Distribuera slutpunktshantering för enheter, datorer och andra slutpunkter](empower-people-to-work-remotely-manage-endpoints.md)
5. [Distribuera produktivitetsappar och tjänster för distansarbetare](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Träna distansarbetare och få feedback om användningen](empower-people-to-work-remotely-train-monitor-usage.md)

![Stegen för att underlätta för distansarbetare med Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

Om du vill ha den senaste informationen från Microsoft om support för distansarbetare går du till [Tech Communityn för att möjliggöra distansarbete](https://resources.techcommunity.microsoft.com/enabling-remote-work/).
