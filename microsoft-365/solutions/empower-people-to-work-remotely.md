---
title: Konfigurera din infrastruktur för hybridarbete med Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: arbeta hemifrån, arbeta-hemifrån, distansarbetare, hybridarbete, distansmedarbetare, hybridanslutning, fjärråtkomst, distansarbete, distansarbeta, distansarbete, mobilt arbete, distansarbete, arbeta var som helst, flexibel arbetsplats
description: Gå igenom infrastrukturens delar så att dina hybridmedarbetarna har säker åtkomst till lokala och Microsoft 365 resurser.
ms.openlocfilehash: fed23a4607cfb47049a6540dfb592d9a8baf9d21
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229377"
---
# <a name="set-up-your-infrastructure-for-hybrid-work-with-microsoft-365"></a>Konfigurera din infrastruktur för hybridarbete med Microsoft 365

För att säkra och optimera dina arbetares produktivitet och samarbete måste du tillåta lokala- och fjärrarbetare att enkelt och säkert få åtkomst till din organisations lokala och molnbaserade information, verktyg och resurser. Den här lösningen går igenom distributionen av viktiga delar av infrastruktur som ger dina medarbetare möjlighet att arbeta på så bra som möjligt, oavsett var de befinner sig.

Hybridarbetare kan jobba lokalt eller på distans på olika platser. Att låta arbetarna arbeta utanför ett traditionellt kontor är viktigt för många organisationer för att:

- Anställa och behålla arbetare som är villiga att omplaceras eller som kräver en flexibel arbetsmiljö.
- Minska pendlingstid för arbetare vilket ger de mer tid att vara produktiva och kunna utföra stressminskande aktiviteter utanför arbetet.
- Spara på kontorsutrymme.

Microsoft 365 har förmågan att möjliggör för dina hybridarbetare att kunna arbeta antingen lokalt eller på distans.

![Möjliggör för dina hybridarbetare med Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

> [!NOTE]
> Om du är ny på Microsoft 365, se [de här resurserna](https://www.microsoft.com/microsoft-365).

Titta på den här videon för att få en översikt över distributionsprocessen.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

För IT-proffs som hanterar lokal- och molnbaserad infrastruktur för att möjliggöra hybridarbetares produktivitet, erbjuder denna lösning följande viktiga funktioner:

- Ansluten

  Var som helst i världen, och när som helst, kan dina hybridarbetare få åtkomst till:

  - Molnbaserade tjänster och data i din Microsoft 365-prenumeration.

  - Organisationsresurser av samma slag som finns att tillgå med programdatacentraler på plats.

- Säker

  Inloggningarna skyddas med multifaktorautentisering (MFA) och inbyggda säkerhetsfunktioner i Microsoft 365 och Windows 10 skyddar mot skadlig programvara, skadliga attacker och dataförluster.

- Hanteras

  Din hybridarbetares enheter kan hanteras från molnet med säkerhetsinställningar, tillåtna appar och för att kräva efterlevnad av systemhälsan.

- Samarbetsvilliga och produktiva

  Dina hybridarbetare kan vara lika produktiva som de lokala på ett mycket samarbetande sätt med:

  - Onlinemöten och chattsessioner med Teams.

  - Delade arbetsytor för molnbaserad fillagring med global tillgänglighet och samarbete i realtid med SharePoint och OneDrive.

  - Delade uppgifter och arbetsflöden för att dela upp arbetet och få saker gjorda.

För smidig inloggning lokalt bör dina användarkonton i Active Directory Domain Services (AD DS) synkroniseras med Azure Active Directory (Azure AD). För att skydda dina Windows 10-enheter bör de registreras i Intune. Här är en övergripande vy över infrastrukturen.

![Den grundläggande infrastrukturen för hybridarbetare med Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Använd de här Microsoft 365-funktionerna om du vill aktivera funktionerna i Microsoft 365 för dina hybridarbetare.

| Resurs eller funktion | Beskrivning | Licensiering |
|:-------|:-----|:-------|
| MFA som förstärks med säkerhetsstandarder   | Skydda er mot identitetsstölder och komprometterade enheter genom att kräva en andra form av autentisering vid inloggning. Säkerhetsstandarderna kräver MFA för alla användarkonton.   | Microsoft 365 E3 eller E5 |
| MFA som förstärks med villkorsstyrd åtkomst| Använd villkorsstyrda åtkomstprinciper för att kräva MFA baserat på egenskaperna för inloggningen.    | Microsoft 365 E3 eller E5 |
| MFA som förstärks med riskbaserad villkorsstyrd åtkomst   | Använd Microsoft Defender for Identity för att kräva MFA baserat på risken som är kopplad till användarens inloggning. | Microsoft 365 E5 eller E3 med Azure AD Premium P2-licenser |
| Självbetjäning för återställning av lösenord (SSPR)    | Låt användarna återställa eller låsa upp sina lösenord och konton.  | Microsoft 365 E3 eller E5 |
| Azure Active Directory Application Proxy    | Tillhandahåll säker fjärråtkomst till webbaserade program som finns på intranätsservrar.   | För detta krävs en separat, betald Azure-prenumeration |
| Azure Point-to-Site VPN   | Skapa en säker anslutning från en distansarbetares enhet till ert intranät via ett virtuellt Azure-nätverk.   | För detta krävs en separat, betald Azure-prenumeration |
| Windows Virtual Desktop   | Underlätta för distansarbetare som bara kan använda privata och ohanterade enheter med hjälp av virtuella skrivbord som körs i Azure. | För detta krävs en separat, betald Azure-prenumeration |
| Fjärrskrivbordstjänster (RDS) | Låt medarbetarna ansluta till Windows-baserade datorer på intranätet. | Microsoft 365 E3 eller E5 |
| Gateway för fjärrskrivbordstjänster   | Kryptera kommunikationen och hindra värddatorerna för fjärrskrivbordstjänsterna från att exponeras direkt på internet. | För detta krävs separata Windows Server-licenser |
| Microsoft Intune | Hantera enheter och program.   | Microsoft 365 E3 eller E5 |
| Konfigurationshanteraren | Hantera programvaruinstallationer, uppdateringar och inställningar på dina enheter | För detta krävs separata licenser för Konfigurationshanteraren |
| Desktop Analytics | Avgör uppdateringsberedskapen hos dina Windows-klienter.   | För detta krävs separata licenser för Konfigurationshanteraren |
| Windows Autopilot | Förinstallera och konfigurera nya Windows 10-enheter för effektiv användning.   | Microsoft 365 E3 eller E5 |
| Microsoft Teams, Exchange Online, SharePoint Online och OneDrive, Microsoft 365-applikationer, Microsoft Power Platform och Yammer | Skapa, kommunicera och samarbeta. | Microsoft 365 E3 eller E5 |
||||

För kriterier för säkerhet och efterlevnad, se [Distribuera säkerhet och efterlevnad för fjärrarbetare](empower-people-to-work-remotely-security-compliance.md).

<a name="poster"></a> För en 2-sidor sammanfattning av denna lösning, se[Möjliggör för hybridarbetare affischen](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf).

[![Möjliggör för hybridarbetare affisch](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)

Du kan också ladda ner den här affischen i [PowerPoint](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pptx)-format och skriva ut den på brev, legal eller tabloid papper i storlek (11 x 17).

## <a name="provide-hybrid-working-for-all-of-your-workers"></a>Tillhandahålla hybridarbete för alla dina medarbetare

Du kan göra så alla dina medarbetare kan vara produktiva var de än befinner sig med dessa enheter:

- En modern enhet, till exempel en Surface laptop och Windows 10, som har funktioner, säkerhet och prestanda för att få tillgång till Microsoft 365-molnprogram och -tjänster direkt över webben.

- Alla enheter, inklusive äldre laptops eller stationära datorer, som kan få tillgång till Microsoft 365-molnprogram och -tjänster indirekt via en snabb distribution av [Windows 10-baserade virtuella skrivbord](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices). Med det här alternativet får du hög prestanda, stark säkerhet och förenklad IT-hantering.

## <a name="next-steps"></a>Nästa steg

Följ dessa steg för att säkra och optimera åtkomsten till din organisations servrar och molntjänster, och maximera din hybridarbetares produktivitet.

1. [Öka inloggningssäkerheten med MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Ge fjärråtkomst till lokala appar och tjänster](empower-people-to-work-remotely-remote-access.md)
3. [Distribuera säkerhets- och efterlevnadstjänster](empower-people-to-work-remotely-security-compliance.md)
4. [Distribuera slutpunktshantering för enheter, datorer och andra slutpunkter](empower-people-to-work-remotely-manage-endpoints.md)
5. [Använd produktivitetsappar och -tjänster för hybridarbetare](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Träna dina medarbetare och få feedback om användningen](empower-people-to-work-remotely-train-monitor-usage.md)

[![Stegen för att konfigurera din infrastruktur för hybridarbete med Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)

För att se hur en fiktiv men representativ multinationell organisation har konfigurerat sin infrastruktur för hybridarbete, gå till [Contosos svar på COVID-19 och infrastruktur för hybridarbete](contoso-remote-onsite-work.md).
