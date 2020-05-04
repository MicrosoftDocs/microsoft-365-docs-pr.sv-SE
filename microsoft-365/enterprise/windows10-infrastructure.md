---
title: Windows 10 Enterprise-infrastruktur för Microsoft 365 Enterprise
description: Ger vägledning på hög nivå om de steg du behöver för att distribuera Windows 10 Enterprise på datorer som en del av Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-dokumentation, Windows 10 Enterprise, distribution
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: d1019547fb16fd4fd5669ebd5286e8c9e32668fe
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011929"
---
# <a name="phase-3-windows-10-enterprise"></a>Fas 3: Windows 10 Enterprise

![Fas 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise innehåller Windows 10 Enterprise, som ger dig verktygen för att göra mer och vara säker. Windows 10 Företag:

- **Är integrerad för enkelhetens skull** - Utnyttja kraften i molnet för att minska komplexiteten i att hantera dagens moderna IT-enhetsmiljö, oavsett storlek.
- **Har intelligent säkerhet** – Det är den säkraste versionen av Windows någonsin, med intelligenta säkerhetsfunktioner som är utformade för att fungera tillsammans för att bättre skydda din organisation.
- **Möjliggör kreativitet och lagarbete** - Låser upp kreativitet och lagarbete för att leverera den mest produktiva upplevelsen som både användare och IT kommer att älska.

Du måste förstå olika sätt att distribuera operativsystemet Windows 10 och välja det rätta för din organisation. Beroende på din Microsoft 365 Enterprise-prenumeration finns det också Windows 10-tjänster och säkerhetsfunktioner som du måste konfigurera för att få ut det mesta av Windows 10.

>[!Note]
>Information om hur du distribuerar både Windows 10 Enterprise och Microsoft 365 Apps för företag tillsammans och byter till ett [modernt skrivbord](https://www.microsoft.com/microsoft-365/modern-desktop)finns i [Modern Desktop Deployment Center](https://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Windows 10-distribution

Det finns flera sätt att distribuera Windows 10 Enterprise för din organisation. Här fokuserar vi på hur du kan konfigurera och distribuera en Windows 10 Enterprise-avbildning genom dessa moderna distributionsscenarier.

| Distributionsscenario | När du ska använda den |
|:--- |:--- |
| [Använda Microsoft Endpoint Configuration Manager som en uppgradering på plats](windows10-deploy-inplaceupgrade.md) | Välj det här alternativet om du behöver uppgradera Windows 7- eller Windows 8.1-datorer till den <a href="https://aka.ms/windows-10-release-information" target="_blank">aktuella versionen</a> av Windows 10 Enterprise och dina datorer för närvarande hanteras med <a href="https://docs.microsoft.com/mem/configmgr/core/understand/introduction" target="_blank">Configuration Manager (aktuell gren).</a> |
| [Använda Windows Autopilot](windows10-deploy-autopilot.md) | Välj det här alternativet om du konfigurerar nya Windows-datorer med Windows 10 Enterprise, version 1703 eller senare förinstallerat. Slutanvändare initierar installationen med önskad konfiguration genom att ange sina autentiseringsuppgifter för arbets- eller skolkonto. |

Om dessa distributionsscenarier inte passar organisationens behov kan du lära dig mer om andra scenarier och förstå funktionerna och begränsningarna för varje i [Windows 10-distributionsscenarier](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). Du kan också <a href="https://aka.ms/planforwin10deployment" target="_blank">planera för distribution av Windows 10</a> på egen hand.

Du kan läsa mer om Windows 10 med följande artiklar:

- [Produktsida för Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Distribuera och uppdatera Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Ytterligare tjänster och funktioner
Som en del av distributionen av Windows 10 Enterprise kan du lägga till dessa ytterligare tjänster och funktioner.

### <a name="windows-analytics"></a>Windows-analys

Windows använder diagnostikdata för att tillhandahålla omfattande och användbar information som hjälper dig att få djup insikt i driftseffektivitet och hälsa för Windows 10-enheter i din miljö.

* Uppgraderingsberedskap - Uppgraderingsberedskap hjälper dig att flytta till Windows 10 och hålla dig uppdaterad med nya windows 10-funktionsuppdateringar. 
* Uppdateringsefterlevnad – Uppdateringsefterlevnad riktar sig till IT-administratören som vill få en helhetsbild av alla sina Windows 10-enheter, utan några ytterligare infrastrukturkrav.
* Enhetshälsa – Du kan använda Enhetshälsa för att proaktivt identifiera och åtgärda problem med att påverka slutanvändaren.

Mer information finns i [Översikt över Windows Analytics.](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)

### <a name="windows-security"></a>Windows-säkerhet

Windows 10 innehåller funktioner som skyddar mot hot, hjälper dig att skydda dina enheter och hjälp med åtkomstkontroll. Med Windows 10 får du viktiga säkerhetsfunktioner som skyddar din enhet redan från början. Microsoft 365 E3 lägger till säkerhetsfunktioner som Windows Hello för företag, Windows Defender Application Control och Windows Information Protection. Med Microsoft 365 E5 får du allt skydd från Microsoft 365 E3-säkerhet plus molnbaserade säkerhetsfunktioner och Microsoft Defender Advanced Threat Protection. 

Mer information om de säkerhetsfunktioner som du får med Windows 10 Enterprise och få vägledning om hur du kan distribuera, hantera, konfigurera och felsöka tre viktiga säkerhetsfunktioner finns i [Steg 5: Distribuera säkerhetsfunktioner för Windows 10 Enterprise](windows10-enable-security-features.md).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hur Microsoft använder Microsoft 365 Enterprise

Kika in i Microsoft och lär dig hur företaget [distribuerade Windows 10 Enterprise och använder stark autentisering, Intune och Microsoft Defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Så här använder Contoso Microsoft 365 Enterprise

Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [distribuerade Windows 10 Enterprise](contoso-win10.md).

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 1](../media/stepnumbers/Step1.png)| [Förbereda din organisation för Windows 10 Enterprise](windows10-prepare-your-org.md) |
