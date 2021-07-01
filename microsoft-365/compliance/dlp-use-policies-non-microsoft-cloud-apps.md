---
title: Använda principer för skydd mot dataförlust för molnappar som inte kommer från Microsoft (förhandsversion)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du använder dlp-principer för program som inte är Microsoft-molnappar.
ms.openlocfilehash: 3c3c687bd1362182d35891ed1ebbfae12416d5d4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226845"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Använda principer för skydd mot dataförlust för molnappar som inte kommer från Microsoft (förhandsversion)

Principer för skydd mot dataförlust (DLP) för icke-Microsoft-molnappar är en del Microsoft 365 DLP-paketet med funktioner. med dessa funktioner kan du identifiera och skydda känsliga objekt i Microsoft 365 tjänster. Mer information om alla Microsoft DLP-erbjudanden finns i [Läs mer om skydd mot dataförlust.](dlp-learn-about-dlp.md)

Du kan använda DLP-principer till andra molnappar än Microsoft för att övervaka och identifiera när känsliga objekt används och delas via andra molnappar än Microsoft. Med de här principerna får du den synlighet och kontroll som du behöver för att säkerställa att de används och skyddas korrekt, och det hjälper till att förhindra riskabelt beteende som kan avslöja dem.

## <a name="before-you-begin"></a>Innan du börjar

### <a name="skusubscriptions-licensing"></a>Licensiering av SKU/prenumerationer

Innan du börjar använda DLP-principer för andra program än Microsoft-molnappar måste [Microsoft 365 din](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) prenumeration och eventuella tillägg. För att komma åt och använda den här funktionen måste du ha någon av dessa prenumerationer eller tillägg:

- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 Security

### <a name="prepare-your-cloud-app-security-environment"></a>Förbereda din Cloud App Security miljö

DLP-principer för icke-Microsoft-molnappar Cloud App Security DLP-funktioner. Om du vill använda den bör du förbereda Cloud App Security miljön. Anvisningar finns i Ange [åtgärder för snabb synlighet, skydd och styrning för dina appar.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)

### <a name="connect-a-non-microsoft-cloud-app"></a>Anslut ett molnapp som inte är ett Microsoft-program

Om du vill använda DLP-principen för en viss app som inte är en Microsoft-molnapp måste programmet vara anslutet till Cloud App Security. Mer information finns i:

- [Anslut Box](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Anslut Dropbox](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Anslut G-Suite](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Anslut Salesforce](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Anslut Cisco Webex](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

När du har anslutt dina molnprogram till Cloud App Security kan du skapa Microsoft 365 DLP-principer för dem.

> [!NOTE]
> Det går också bra att använda Microsoft Cloud App Security för att skapa DLP-principer för Microsoft-molnappar. Vi rekommenderar dock att du använder Microsoft 365 att skapa och hantera DLP-principer för Microsoft-molnappar.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Skapa en DLP-princip i en molnbaserad app som inte är en Microsoft-app

När du väljer en plats för DLP-principen aktiverar du **Microsoft Cloud App Security** plats.

- Om du vill välja en viss app eller instans väljer du **Välj instans**.
- Om du inte väljer en instans används alla anslutna appar i din klientorganisation Microsoft Cloud App Security princip.

   ![Platser där principen ska tillämpas](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US och Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

Du kan välja olika åtgärder för alla program som inte stöds i Microsoft-molnprogrammet. Det finns olika möjliga åtgärder för varje program (beror på molnapp-API:t).

![Skapa regel](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

När du skapar en regel i DLP-principen kan du välja en åtgärd för icke-Microsoft-molnappar. Om du vill begränsa appar från tredje part **väljer du Begränsa appar från tredje part.**

![Begränsa appar från tredje part](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [OBS] De DLP-principer som tillämpas på icke-Microsoft-appar Microsoft Cloud App Security. När DLP-principen för en app som inte är en Microsoft-app skapas samma princip automatiskt Microsoft Cloud App Security.

Information om hur du skapar och konfigurerar DLP-principer finns [i Skapa testa och finjustera en DLP-princip.](./create-test-tune-dlp-policy.md)

## <a name="see-also"></a>Se även

- [Skapa testa och finjustera en DLP-princip](./create-test-tune-dlp-policy.md)
- [Kom igång med DLP-standardprincipen](./get-started-with-the-default-dlp-policy.md)
- [Skapa en DLP-princip från en mall](./create-a-dlp-policy-from-a-template.md)
