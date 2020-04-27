---
title: 'Fas 4: Microsoft 365-applikationer för företag'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Steg för att distribuera infrastrukturen för Microsoft 365-applikationer för företag för Microsoft 365 Enterprise.
ms.openlocfilehash: fe29b8025a8ccf5babf2c52cd62ebc72860a8a5c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631435"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a>Fas 4: Microsoft 365-applikationer för företag

![Fas 4: Microsoft 365-applikationer för företag](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Det här steget gäller både E3- och E5-versionerna av Microsoft 365 Enterprise och Microsoft 365 Education*

Microsoft 365 Enterprise innehåller Microsoft 365-applikationer för företag, prenumerationsversionen av Office. Precis som Office 2019 innehåller Microsoft 365-applikationer för företag alla Office-programmen, och programmen installeras direkt på klientenheterna. Till skillnad från Office 2019 uppdateras Microsoft 365-applikationer för företag regelbundet med nya funktioner och har en användarbaserad licensieringsmodell som gör det möjligt för användare att installera Office på flera enheter. Mer information finns i [Om Microsoft 365-applikationer för företag i företaget](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).

I den här fasen distribuerar du Microsoft 365-applikationer för företag till klientenheter som en del av Microsoft 365 Enterprise. Utöver den här vägledningen rekommenderar vi att du använder [Microsoft FasTrack](https://fasttrack.microsoft.com/office) för att underlätta distributionen. 

Om du redan har distribuerat Microsoft 365-applikationer för företag kan du läsa [avslutsvillkoren](office365proplus-exit-criteria.md) i den här fasen för att kontrollera att den uppfyller de obligatoriska villkoren för Microsoft 365 Enterprise.

>[!Note]
>Om du vill distribuera både Windows 10 Enterprise och Microsoft 365-applikationer för företag tillsammans hittar du mer information i [Center för skrivbordsdistribution](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Steg 1: Utvärdera miljön

Innan du distribuerar Microsoft 365-applikationer för företag följer du anvisningarna i artikeln om att [utvärdera miljön och kraven för distribution av Microsoft 365-applikationer för företag](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). I den här utvärderingen ingår systemkrav, information om dina klientenheter (till exempel arkitekturer och språk som krävs), licensieringskrav, nätverkskapacitet och programkompatibilitet. Utvärderingen hjälper dig att fatta viktiga beslut som en del av planeringen inför distributionen.

## <a name="step-2-plan-your-deployment"></a>Steg 2: Planera distributionen

När du har utvärderat miljön följer du stegen i artikeln om att [planera distributionen av Microsoft 365-applikationer för företag](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) för att skapa en distributionsplan. I planen ingår följande beslut: 

- Hur du distribuerar Office, till exempel vilket verktyg du ska använda (till exempel Microsoft Endpoint Configuration Manager eller Office-distributionsverktyget) och var Office ska installeras från
- Hantera uppdateringar av Office
- Vilka uppdateringskanaler du ska använda (uppdateringskanaler för Office styr hur ofta användarna får funktionsuppdateringar för Office-program)
- De Office-installationspaket och distributionsgrupper som du vill använda, inklusive vilka Office-program och språk som ska installeras för vilka användare

I [planeringsartikeln](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) finns metodtips för alla dessa alternativ, t. ex. hur du hanterar distribution och uppdateringar, definierar installationspaket och skapar distributionsgrupper. 

## <a name="step-3-deploy"></a>Steg 3: Distribuera

Välj hur du vill distribuera baserat på din distributionsplan:

- **[Distribuera Microsoft 365-applikationer för företag med Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Hantera din distribution med Configuration Manager, och ladda ned och distribuera Office från distributionsplatser i nätverket

- **[Distribuera Microsoft 365-applikationer för företag med ODT från molnet](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Hantera din distribution med ODT och installera Office på klientenheter direkt från Office CDN
 
- **[Självinstallation av Microsoft 365-applikationer för företag från Office-portalen](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Hantera din distribution från Office-portalen och låt användarna installera Office på sina klientenheter direkt från portalen

Många organisationer kommer att använda en kombination av de här alternativen för olika användare. En organisation kan till exempel använda konfigurationshanteraren för att distribuera Office till merparten av sina användare, men erbjuda självinstallation för en mindre grupp medarbetare som inte ansluter till det interna nätverket så ofta. 

Om din organisation använder konfigurationshanteraren rekommenderar vi att du uppgraderar till Current Branch och uppdaterar till den senaste versionen. Mer information finns i [Vilken gren av konfigurationshanteraren ska jag använda?](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hur Microsoft använder Microsoft 365 Enterprise

Ta reda på hur experter på Microsoft [distribuerar och hanterar uppdateringar för Microsoft 365-applikationer för företag](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Så här använder Contoso Microsoft 365 Enterprise

Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [distribuerade Microsoft 365-applikationer för företag](contoso-o365pp.md).

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nästa steg

[Avslutsvillkor för infrastrukturen för Microsoft 365-applikationer för företag](office365proplus-exit-criteria.md)
