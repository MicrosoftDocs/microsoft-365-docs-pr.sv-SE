---
title: Dataklassificering för din Microsoft 365 för företagstestmiljö
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Använd den här testlabbguiden för att skapa och använda bevarandeetiketter på dokument i Microsoft 365 för företagstestmiljö.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919194"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Dataklassificering för din Microsoft 365 för företagstestmiljö

*Den här testlabbguiden kan användas för både Microsoft 365 för företag Office 365 Enterprise för testmiljöer.*

I den här artikeln beskrivs hur du konfigurerar dataklassificering med hjälp av bevarandeetiketter i Microsoft 365 för företagstestmiljö.

Klassificering av data i testmiljön omfattar tre faser:
- [Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: Skapa bevarandeetiketter](#phase-2-create-retention-labels)
- [Fas 3: Använda bevarandeetiketter i dokument](#phase-3-apply-retention-labels-to-documents)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö

Om du bara vill konfigurera bevarandeetiketter på ett lätt sätt med minimikraven följer du anvisningarna i Enkel [baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Om du vill konfigurera bevarandeetiketter i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> För testning av bevarandeetiketter krävs inte den simulerade företagstestmiljön, som omfattar ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Här finns ett alternativ så att du kan testa automatisk licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en vanlig organisation.

## <a name="phase-2-create-retention-labels"></a>Fas 2: Skapa bevarandeetiketter

I den här fasen skapar du bevarandeetiketter för de olika bevarandenivåerna för de SharePoint mapparna i Online-dokument:

1. Logga in på [säkerhetscentret Microsoft 365 ditt](https://security.microsoft.com/homepage) globala administratörskonto.
1. På fliken **Start – Microsoft 365 i** webbläsaren väljer du Klassificeringslagringsetiketter.   >  
1. Välj **Skapa en etikett**.
1. I fönstret **Namnge din etikett** anger du Intern **offentlig** i Namnge **din etikett** och väljer sedan **Nästa.**
1. I fönstret **Filplansbeskrivningar** väljer du **Nästa.**
1. Om det **behövs går** du till fönstret Etikettinställningar och ställer **in Bevarande** **på** och väljer sedan **Nästa.**
1. I fönstret **Granska dina** inställningar väljer du **Skapa etiketten**.
1. Upprepa steg 3–7 för ytterligare etiketter med följande namn:
  - Privat
  - Känslig
  - Strikt konfidentiellt
1. I fönstret **Bevarandeetiketter** väljer du **Publicera etiketter.**
1. I fönstret **Välj etiketter som ska publiceras** väljer du Välj etiketter att **publicera.**
1. I fönstret **Välj etiketter** väljer du Lägg **till och** markerar alla fyra etiketterna.
1. Välj **Lägg** till och välj sedan **Klar**.
1. Välj Nästa **i fönstret Välj etiketter** som ska **publiceras.**
1. I **fönstret Välj platser** väljer du **Nästa**.
1. I fönstret **Namnge principen** anger du Exempel **på organisation** **i Namn** och väljer sedan **Nästa**.
1. I fönstret **Granska dina inställningar** väljer du Publicera **etiketter**.
 
Det kan ta några minuter innan de bevarandeetiketter som publiceras publiceras.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fas 3: Använda bevarandeetiketter i dokument

I den här fasen upptäcker du standardbeteendet för bevarandeetiketter för filer i mappen Dokument på en SharePoint Online-webbplats och ändrar manuellt bevarandeetiketten för ett dokument.

Skapa först en gruppwebbplats med känslig SharePoint nivå:
  
1. Med en privat instans av webbläsaren loggar du in på Microsoft 365 [administrationscenter med](https://admin.microsoft.com) ditt globala administratörskonto.
1. I listan med paneler väljer du **SharePoint**.
1. På den **nya SharePoint** i webbläsaren väljer du Skapa **webbplats**.
1. På sidan **Skapa en webbplats** väljer du **Gruppwebbplats**.
1. I rutan **Gruppwebbplatsens** namn anger du **SensitiveFiles**.
1. I rutan **Beskrivning av gruppwebbplats** anger du **SharePoint webbplats för känsliga filer**.
1. I **Sekretessinställningar** väljer du **Privat – endast medlemmar kan komma åt den här** webbplatsen och väljer sedan **Nästa**.
1. I Vem **vill du lägga till? väljer** du **Slutför**.
    
Konfigurera sedan mappen Dokument på gruppwebbplatsen SensitiveFiles för bevarandeetiketten Känslig.
  
1. På **fliken KänsligaFiler** i webbläsaren väljer du **Dokument**.
1. Välj **Inställningar** och välj sedan **Biblioteksinställningar**.
1. Under **Behörigheter och hantering** väljer du Använd etikett för objekt i listan eller **biblioteket**. Om det här alternativet inte visas har dina kvarhållningsetiketter ännu inte publicerats. Prova det här steget senare.
1. I **Inställningar-Använd etikett** väljer **du** Känslig i listrutan och väljer sedan **Spara**.

Skapa sedan ett nytt dokument på webbplatsen SensitiveFiles och ändra dess bevarandeetikett.
    
1. Välj Nytt Word-dokument **i**  >  **dokumentmappen.**
1. Skriv lite text i det tomma dokumentet. Vänta tills texten har sparats.
1. På menyraden väljer du **Delade dokument**.
1. Markera de **lodrätaDocument.docx** bredvid filnamnet och välj sedan **Information**.
1. Observera att bevarandeetiketten  Känslig har använts automatiskt **i** dokumentet under  Använd bevarandeetikett i den högra rutan i avsnittet Egenskaper.
1. Klicka **på Redigera alla**.
1. I **Document.docx** under Använd **bevarandeetikett** väljer du etiketten **Konfidentiellt** och sedan **Spara**.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [informationsskyddsfunktioner](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)