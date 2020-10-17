---
title: Data klassificering för test miljön av Microsoft 365 för företag
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
description: Använd den här test laboratorie guiden för att skapa och använda behållnings etiketter i dokument i test miljön för Microsoft 365 för företag.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487738"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Data klassificering för test miljön av Microsoft 365 för företag

*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*

I den här artikeln beskrivs hur du konfigurerar data klassificering med hjälp av lagrings etiketter i test miljön för Microsoft 365 för företag.

Att klassificera data i test miljön inbegriper tre faser:
- [Fas 1: bygga ut test miljön för Microsoft 365 för företag](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: skapa behållnings etiketter](#phase-2-create-retention-labels)
- [Fas 3: tillämpa behållnings etiketter i dokument](#phase-3-apply-retention-labels-to-documents)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill konfigurera behållnings etiketter på ett sätt som uppfyller minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera behållnings etiketter i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Det krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalog-synkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation.

## <a name="phase-2-create-retention-labels"></a>Fas 2: skapa behållnings etiketter

I den här fasen skapar du lagrings etiketterna för de olika nivåerna av bevarande för dokument i SharePoint Online:

1. Logga in på [Microsoft 365 säkerhets Center](https://security.microsoft.com/homepage) med ditt globala administratörs konto.
1. Välj **klassificerings**etiketter på fliken **Start-Microsoft 365-säkerhet** i webbläsaren  >  **Retention labels**.
1. Välj **skapa en etikett**.
1. Ange **intern offentlig** i **namn på etiketten**i rutan **namn på etiketten** och välj sedan **Nästa**.
1. I fönstret **fil Plans beskrivningar** väljer du **Nästa**.
1. I fönstret **etikett inställningar** , om det behövs, ange **Retention** **behållning till på**och välj sedan **Nästa**.
1. I fönstret **Granska inställningar** väljer du **skapa etiketten**.
1. Upprepa steg 3-7 för ytterligare etiketter med följande namn:
  - Privat
  - Känslig
  - Strikt konfidentiellt
1. Välj **publicera etiketter**i fönstret **bevarande etiketter** .
1. Välj vilka **etiketter du vill publicera**i fönstret **Välj etiketter för publicering** .
1. Välj **Lägg till** i fönstret **Välj Etiketter** och markera alla fyra etiketterna.
1. Välj **Lägg till**och välj sedan **klar**.
1. I fönstret **Välj etiketter för publicering väljer du** **Nästa**.
1. I fönstret **Välj platser** väljer du **Nästa**.
1. Ange **exempel organisation** i **namn**i fönstret **namn** och välj sedan **Nästa**.
1. Välj **publicera etiketter**i fönstret **Granska inställningar** .
 
Det kan ta några minuter innan bevarande etiketterna kan publiceras.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fas 3: tillämpa behållnings etiketter i dokument

I den här fasen får du reda på standard beteendet för kvarhållande av filer i mappen dokument på en SharePoint Online-webbplats och manuellt ändra etiketten för ett dokument.

Börja med att skapa en grupp webbplats på känslig nivå:
  
1. Använd en privat instans av webbläsaren och logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) med ditt globala administratörs konto.
1. I listan över brickor väljer du **SharePoint**.
1. Välj **Skapa webbplats**på fliken ny **SharePoint** i webbläsaren.
1. Välj **grupp webbplats**på sidan **skapa en webbplats** .
1. I rutan **grupp webbplatsens namn** skriver du **SensitiveFiles**.
1. I rutan **grupp webbplats Beskrivning** anger du **SharePoint-webbplats för känsliga filer**.
1. Välj **privata medlemmar**i **Sekretess inställningar**och välj sedan **Nästa**.
1. I fönstret **vem vill du lägga till? väljer du** **Slutför**.
    
Sedan konfigurerar du mappen dokument på SensitiveFiles-grupp webbplatsen efter den känsliga behållnings etiketten.
  
1. På fliken **SensitiveFiles** i webbläsaren väljer du **dokument**.
1. Välj ikonen för **Inställningar** och välj sedan **biblioteks inställningar**.
1. Under **behörigheter och hantering**väljer **du Använd etikett för objekt i den här listan eller det här biblioteket**. Om det här alternativet inte visas har dina lagrings etiketter ännu inte publicerats. Prova det här steget senare.
1. I **Inställningar – Använd etikett**, Välj **känslig** i list rutan och välj sedan **Spara**.

Skapa sedan ett nytt dokument på SensitiveFiles-webbplatsen och ändra etikettens etikett.
    
1. Välj **nytt**  >  **Word-dokument**i mappen dokument.
1. Skriv text i det tomma dokumentet. Vänta tills texten har sparats.
1. På Meny raden väljer du **delade dokument**.
1. Bredvid **Document.docx** fil namn väljer du den lodräta ellipsen och väljer sedan **information**.
1. I det högra fönstret, i avsnittet **Egenskaper** , under **tillämpa bevarande etikett**, ser du att dokumentet har den **känsliga** behållnings etiketten automatiskt tillämpad.
1. Klicka på **Redigera alla**.
1. Markera den **mycket konfidentiella** etiketten under **Använd bevarande etikett**i **Document.docx** fönstret och välj sedan **Spara**.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare funktioner för [informations skydd](m365-enterprise-test-lab-guides.md#information-protection) i test miljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
