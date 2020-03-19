---
title: Dataklassificering för microsoft 365 Enterprise-testmiljön
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
description: Använd den här testlabbet-guiden om du vill skapa och använda lagringsetiketter för Office 365 i dokument i testmiljön för Microsoft 365 Enterprise.
ms.openlocfilehash: 6534eff67e9c91423eb6f81415cb3ef2e965dcc1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809680"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Dataklassificering för microsoft 365 Enterprise-testmiljön

*Den här testlabbet-guiden kan användas för testmiljöer för Både Microsoft 365 Enterprise och Office 365 Enterprise.*

Med instruktionerna i den här artikeln konfigurerar du dataklassificering med hjälp av Lagringsetiketter för Office 365 i Microsoft 365 Enterprise-testmiljön.

![Testlabbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill ha en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide-stacken.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygg ut testmiljön för Microsoft 365 Enterprise

Om du bara vill konfigurera Lagringsetiketter för Office 365 på ett lätt väg med minimikraven följer du anvisningarna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera Lagringsetiketter för Office 365 i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av Office 365-kvarhållningsetiketter kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation. 

## <a name="phase-2-create-office-365-retention-labels"></a>Fas 2: Skapa lagringsetiketter för Office 365

I den här fasen skapar du kvarhållningsetiketterna för de olika nivåerna för kvarhållning för SharePoint Online-dokumentmappar.

1. Logga in på [Microsoft 365-säkerhetscentret](https://security.microsoft.com/homepage) med ditt globala administratörskonto.
    
2. Klicka på **Klassificering > lagringsetiketter**på **fliken Start - Microsoft 365** i webbläsaren .
    
3. Klicka på **Skapa en etikett**.
    
4. Skriv **Internt offentligt** i Namn **på etiketten**i fönstret Namn på **etiketten** och klicka sedan på **Nästa**.

5. Klicka på **Nästa**i fönstret **Filplansbeskrivningar** .
    
6. Ställ in **Kvarhållning** till **På**i fönstret **Etikettinställningar** och klicka sedan på **Nästa**.
    
7. Klicka på Skapa etiketten **i**fönstret **Granska dina inställningar** .
    
8. Upprepa steg 3-7 för ytterligare etiketter med följande namn:
    
  - Privat
    
  - Känsliga
    
  - Mycket konfidentiellt
  
9. Klicka på Publicera etiketter i fönstret **Kvarhållningsetiketter.** **Publish labels**
    
10. Klicka på Välj etiketter att publicera i fönstret **Välj etiketter** som **ska publiceras.**
    
11. Klicka på **Lägg till** i fönstret **Välj etiketter** och markera alla fyra etiketterna.
    
12. Klicka på **Lägg till**och sedan på **Klar**.
    
13. Klicka på **Nästa**i fönstret **Välj etiketter att publicera** .
    
14. Klicka på **Nästa**i fönstret **Välj platser** .
    
15. Skriv **Exempelorganisation** i Namn **Example organization** i **namnfönstret**och klicka sedan på **Nästa**.
    
16. Klicka på **Publicera etiketter**i fönstret **Granska inställningar** .
 
Observera att det kan ta några minuter innan lagringsetiketterna publiceras.

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>Fas 3: Använda Lagringsetiketter för Office 365 på dokument

I den här fasen identifierar du standardetiketten för lagringsetikett för filer i mappen Dokument på en SharePoint Online-webbplats och ändrar ett dokuments kvarhållningsetikett manuellt.

Skapa först en sharepoint-gruppwebbplats på känslig nivå:
  
1. Logga in på [Office 365-portalen](https://portal.office.com) med hjälp av en privat instans av webbläsaren med ditt globala administratörskonto.
    
2. Klicka på **SharePoint**i listan med paneler.
    
3. Klicka på **Skapa webbplats**på den nya **fliken SharePoint** i webbläsaren .
    
4. Klicka på **Gruppwebbplats**på sidan **Skapa en webbplats** .
    
5. Skriv **Känsliga filer**i **Gruppwebbplatsnamn**.
    
6. Skriv **SharePoint-webbplats för känsliga filer i** **Gruppwebbplatsbeskrivning**.
    
7.  I **Sekretessinställningar**väljer du **Privat – endast medlemmar kan komma åt den här webbplatsen**och klicka sedan på **Nästa**.
    
8. Klicka på **Slutför**i fönstret **Vem vill du lägga till?**
    
Konfigurera sedan mappen Dokument på teamplatsen SensitiveFiles för etiketten Känslig kvarhållning.
  
1. Klicka på **Dokument**på fliken **Känsliga filer** i webbläsaren .
    
2. Klicka på inställningsikonen och sedan på **Biblioteksinställningar**.
    
3. Klicka på **Använd etikett på objekt i listan eller biblioteket under** **Behörigheter och hantering.** Om det här alternativet inte visas har behållaniketterna ännu inte publicerats. Prova det här steget vid ett senare tillfälle.
    
4. I **Inställningsansöka etikett**väljer du **Känslig** i listrutan och klickar sedan på **Spara**.

Skapa sedan ett nytt dokument på plats SensitiveFiles och ändra dess kvarhållningsetikett.
    
1. Klicka på Nytt **> Word-dokument i dokumentmappen**.
    
2. Skriv text i det tomma dokumentet. Vänta tills texten har sparats.
    
3. Klicka på Delade **dokument**på menyraden.
    
4. Klicka på den lodräta ellipsen bredvid filnamnet **Document.docx** och klicka sedan på **Detaljer**.
    
5. I det högra fönstret, i avsnittet **Egenskaper,** under **Använd kvarhållningsetikett,** bör du tänka på att dokumentet har tillämpat etiketten **Känslig** kvarhållning automatiskt.
    
6. Klicka på **Redigera alla**.
    
7. Markera etiketten **Mycket konfidentiell** under **Använd kvarhållningsetikett**i fönstret **Document.docx** och klicka sedan på **Spara**.

Mer information och länkar till hur du distribuerar Office 365-kvarhållningsetiketter i produktion finns i steget [Konfigurera klassificering för din miljö](infoprotect-configure-classification.md) i **informationsskyddsfasen.**

## <a name="next-step"></a>Nästa steg

Utforska ytterligare funktioner och funktioner för [informationsskydd](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.

## <a name="see-also"></a>Se även

[Testlaboratorikguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation från Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

 
