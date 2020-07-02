---
title: 'Steg 2: Konfigurera klassificering för din miljö'
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
description: Förstå och konfigurera flera olika sätt att klassificera data i din organisation.
ms.openlocfilehash: 57d4c692630826f371ea825d86fc64b959b71df2
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005816"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Steg 2: Konfigurera klassificering för din miljö

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

I det här steget arbetar du med dina team för lag- och regelefterlevnad för att definiera ett klassificeringsschema för organisationens data.

## <a name="microsoft-365-classification-types"></a>Klassificeringstyper för Microsoft 365

I Microsoft 365 finns fyra typer av klassificering:

- Typer av känslig information
- Kvarhållningsetiketter
- Markera som känsligt
- Azure Information Protection-etiketter och -skydd

### <a name="sensitive-information-types"></a>Typer av känslig information

Känsliga informationstyper för Microsoft 365 definierar hur automatiserade processer, t. ex. sökning, ska identifiera vissa typer av information. Här ingår känslig information för medarbetare eller kunder, t. ex. nummer till sjukvården och kreditkortsnummer. Du kan använda känsliga informationstyper för att hitta känsliga data och tillämpa regler och principer för DLP (dataförlustskydd) för att skydda dessa data. Mer information finns i avsnittet om [vad en DLP-princip innehåller](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains). 

Olika typer av känsliga uppgifter är särskilt användbara för att uppfylla kraven på efterlevnad och föreskrifter, t. ex. för den allmänna dataskyddsförordningen (GDPR).

### <a name="retention-labels"></a>Kvarhållningsetiketter

En del av att definiera en datastyrningsstrategi är att ange hur länge vissa typer av dokument eller dokument med specifikt innehåll ska behållas i enlighet med organisationens principer och regionala bestämmelser. Exempelvis ska vissa typer av dokument bevaras under en viss tidsperiod och sedan tas bort, och andra måste behållas för alltid.

För dokument som lagrats i Microsoft 365 definierar och tillämpar du kvarhållandet av etiketter för dokument och data som lagras i Exchange-e-post, SharePoint Online, OneDrive för företag och Teams-chattar och kanalmeddelanden. 

Om du använder kvarhållningsetiketter ska du konfigurera en etikett för varje filkategori som behöver ha en tillämpad kvarhållningsprincip. I kvarhållningsetiketter kan du ange:

- En uppsättning beskrivningar för filerna (t. ex. efter företagsavdelning, filkategori eller förordning).
- Inställningarna för kvarhållande för de filer som har kvarhållningsetiketten bifogad, t. ex. kvarhållningstider och beteenden efter att kvarhållningstiden har uppnåtts.

Du kan också använda en kvarhållningsetikett för filer automatiskt genom att konfigurera en SharePoint Online-webbplats för att lägga till en standardkvarhållningsetikett på alla nya dokument på webbplatsen. 

Mer information finns i [översikten över kvarhållningsetiketter](https://docs.microsoft.com/office365/securitycompliance/labels).

### <a name="sensitivity-labels"></a>Markera som känsligt

En del av skyddet och implementeringen av säkerheten för vissa typer av dokument eller dokument med ett särskilt innehåll markeras med en etikett så att den ytterligare säkerheten kan användas. Med känslighetsetiketter i Microsoft 365 kan du göra följande:

- Använda skyddsinställningar som kryptering, behörigheter eller lägga till en vattenstämpel.
- Använd WIP-slutpunktsskydd (Windows Endpoint Protection) för att förhindra att innehåll kopieras till ett program från tredje part, t. ex. Twitter och Gmail, eller kopieras till flyttbara lagringsmedier, t. ex. en USB-enhet.
- Använd Microsoft Cloud App Security (CAS) för att skydda innehåll i program och tjänster från tredje part. 
- Klassificera innehåll utan att använda skyddsinställningar.

Om du använder känslighetsetiketter måste du konfigurera en etikett för varje säkerhets-och informationsskyddsnivå. Skapa exempelvis tre känslighetsetiketter för:

- Grundläggande
- Känslig
- Strikt reglerad

Om du lagrar filer med strikt reglerade data i en SharePoint Online-webbplats och vill att filerna ska ha samma behörighet som webbplatsen om filerna lämnar webbplatsen måste du skapa en extra känslighetsetikett vars behörigheter är desamma som webbplatsen.

Mer information finns i den här [översikten över känslighetsetiketter](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).

### <a name="azure-information-protection-labels-and-protection"></a>Azure Information Protection-etiketter och -skydd

Du kan använda Azure information Protection-etiketter för att klassificera och eventuellt skydda organisationens dokument och e-postmeddelanden. Etiketterna kan användas för dokument som är lagrade utanför Microsoft 365. De här etiketterna kan användas automatiskt av administratörer som definierar regler och villkor, manuellt av användare, eller en kombination där användarna får rekommendationer.

Om du vill planera och distribuera Azure Information Protection-etiketter och -skydd gör du så här:

1. Granska [kraven för Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Följ [distributionsöversikten för klassificering, märkning och skydd](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Mer information finns i [biblioteket med dokumentation för Azure Information Protection](https://docs.microsoft.com/information-protection/).

Befintliga etiketter för Azure Information Protection fungerar smidigt med känslighetsetiketter. Du kan till exempel behålla dina befintliga etiketter för Azure Information Protection och de etiketter som används i dokument och e-post.

Om du har både känslighets- och Azure Information Protection-etiketter ska du [migrera Azure Information Protection-etiketterna till känslighetsetiketter](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#sensitivity-labels-and-azure-information-protection).

## <a name="example-classification-for-gdpr"></a>Exempel: klassificering för GDPR

Ett exempel på ett klassificeringsschema som innehåller personliga data för GDPR finns i [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data) (Skapa ett klassificeringsschema för personliga data).

## <a name="take-it-for-a-test-drive"></a>Kör en provomgång

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: dataklassificering](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](infoprotect-exit-criteria.md#crit-infoprotect-step2) som motsvarar det här steget.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 3](../media/stepnumbers/Step3.png)|[Konfigurera ökad säkerhet för Office 365](infoprotect-configure-increased-security-office-365.md)|

