---
title: Avslutsvillkor för informationsskyddets infrastruktur
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Kontrollera villkoren för informationsskyddsbaserade tjänster och infrastruktur för att säkerställa att din konfiguration uppfyller kraven för Microsoft 365 Enterprise.
ms.openlocfilehash: c0b4ff6a0d289b8a8c63255d817ea455df00bf13
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631639"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Avslutsvillkor för informationsskyddets infrastruktur

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Kontrollera att infrastrukturen för informationsskydd uppfyller följande krav och att du har bedömt vilka villkor som kan vara valfria.

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Obligatoriskt: Säkerhets- och informationsskyddsnivåer för din organisation har definierats

Du har planerat för och avgjort vilka säkerhetsnivåer din organisation behöver. Dessa nivåer definierar en lägsta säkerhetsnivå och ytterligare nivåer för känsligare information och den datasäkerhet den kräver.

Som minst använder du tre säkerhetsnivåer:

- Baslinje
- Känslig
- Strikt reglerad

Vid behov kan [Steg 1](infoprotect-define-sec-infoprotect-levels.md) hjälpa dig med detta krav. 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>Obligatoriskt: Ökad säkerhet för Microsoft 365 har konfigurerats

Du har konfigurerat följande inställningar för [ökad säkerhet i Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):

- Principer för hothantering i Microsoft 365 Säkerhetscenter
- Ytterligare inställningar för hela Exchange Online-klientorganisationen
- Delningsprinciper för hela klientorganisationen i administrationscentret för SharePoint Online
- Inställningar i Azure Active Directory (Azure AD)

Du har även [aktiverat Office 365 Advanced Threat Protection för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Vid behov kan [Steg 3](infoprotect-configure-increased-security-office-365.md) hjälpa dig med detta krav. 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Valfritt: Klassificering har konfigurerats i hela din miljö

Du har samarbetat med dina juridiska team och efterlevnadsteam för att utveckla ett lämpligt klassificerings- och märkningsschema för organisationens datastyrning och säkerhetsprinciper. 

Dessa principer motsvarar konfigurationen och distributionen av:

- Känsliga datatyper
- Kvarhållningsetiketter
- Känslighetsetiketter
- Azure Information Protection-etiketter

Vid behov kan [Steg 2](infoprotect-configure-classification.md) hjälpa dig med detta krav. 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>Valfritt: Windows Information Protection distribueras i hela din miljö

Dina registrerade Windows 10 Enterprise-enheter innehåller en Intune-princip som definierar:

- Vilka appar som ska skyddas.
- Skyddsnivån.
- Hur långt skyddet sträcker sig.

Vid behov kan [Steg 4](infoprotect-deploy-windows-information-protection.md) hjälpa dig med detta krav. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-data-loss-prevention-dlp-is-deployed"></a>Valfritt: Dataförlustskydd (DLP) har distribuerats

Du har analyserat, testat och distribuerat en uppsättning DLP-principer – som innehåller platser och regler med villkor och åtgärder – som din organisation behöver för att skydda kunddata och andra typer av privata data, samt för att kunna följa branschbaserade och regionala regler och föreskrifter.

Din personal inom dataefterlevnad och säkerhet använder instrumentpanelen för säkerhet och efterlevnad till att övervaka DLP-incidenter.

Vid behov kan [Steg 5](infoprotect-data-loss-prevention.md) hjälpa dig med detta krav. 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a>Valfritt: E-postkryptering har konfigurerats

Du har konfigurerat följande e-postkryptering vid behov för din organisation:

|||
|:-------|:-----|
| **Krypteringsmetod** | **För e-post som skickas** |
| [Meddelandekryptering i Office 365 (OME)](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | Utanför organisationen med kryptering |
| [IRM (Information Rights Management)](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | Med både kryptering och behörigheter |
| [S/MIME (Secure/Multipurpose Internet Mail Extensions)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | Med både kryptering och digitala signaturer som använder kryptering med offentliga nycklar |
|||

Vid behov kan [Steg 6](infoprotect-email-encryption.md) hjälpa dig med detta krav.

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Valfritt: Konfigurera Privileged Access Management i Office 365

Du har använt informationen i [Konfigurera Privileged Access Management i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) för att aktivera privilegierad åtkomst och skapa en eller flera principer för privilegierad åtkomst inom organisationen. Du har konfigurerat dessa principer och just-in-time-åtkomst är aktiverad för åtkomst till känsliga data eller kritiska konfigurationsinställningar.

Vid behov kan [Steg 7](infoprotect-configure-privileged-access-management.md) hjälpa dig med detta krav. 

## <a name="results-and-next-steps"></a>Resultat och nästa steg

Din infrastruktur för informationsskydd i Microsoft 365 Enterprise använder definierade säkerhetsnivåer, ökad säkerhet för Office 365, klassificering med känsliga datatyper och etiketter, Windows Information Protection, dataförlustskydd, e-postkryptering och Privileged Access Management.

Om du har följt distributionen från slutpunkt till slutpunkt för Microsoft 365 Enterprise, är du nu redo att låta [arbetsbelastningar och scenarier](deploy-workloads.md) utnyttja funktioner och konfiguration av den grundläggande infrastrukturen.
