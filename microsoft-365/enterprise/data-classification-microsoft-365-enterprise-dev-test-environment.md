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
ms.openlocfilehash: 171fcb74b09a1f2e5c80f23e010640dce55660bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686412"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Data klassificering för test miljön av Microsoft 365 för företag

*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*

Med instruktionerna i den här artikeln konfigurerar du data klassificering med hjälp av lagrings etiketter i test miljön för Microsoft 365 för företag.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill konfigurera behållnings etiketter på ett sätt som uppfyller minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera behållnings etiketter i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Det krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalog-synkronisering för en AD DS-skog (Active Directory Domain Services). Det tillhandahålls här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation. 

## <a name="phase-2-create-retention-labels"></a>Fas 2: skapa behållnings etiketter

I den här fasen skapar du lagrings etiketterna för de olika nivåerna av bevarande för SharePoint Online-dokument.

1. Logga in på [Microsoft 365 säkerhets Center](https://security.microsoft.com/homepage) med ditt globala administratörs konto.
    
2. Klicka på **klassificering > behållnings etiketter**på fliken **hem-Microsoft 365-säkerhet** i webbläsaren.
    
3. Klicka på **Skapa en etikett**.
    
4. Ange **intern allmän** i **namn på etiketten**i rutan **namn** på etikett och klicka sedan på **Nästa**.

5. Klicka på **Nästa**i fönstret **fil Plans beskrivningar** .
    
6. I fönstret **etikett inställningar** , om det behövs, ange **behållningen** till **den**och klicka sedan på **Nästa**.
    
7. I fönstret **Granska inställningar** klickar **du på skapa etiketten**.
    
8. Upprepa steg 3-7 för ytterligare etiketter med följande namn:
    
  - Privat
    
  - Känslig
    
  - Strikt konfidentiellt
  
9. Klicka på **publicera etiketter**i fönstret **bevarande etiketter** .
    
10. Klicka på **Välj Etiketter**för publicering i fönstret **Välj etiketter för publicering** .
    
11. Klicka på **Lägg till** i fönstret **Välj Etiketter** och markera alla fyra etiketterna.
    
12. Klicka på **Lägg till** och sedan på **Klart**.
    
13. I fönstret **Välj etiketter att publicera** klickar du på **Nästa**.
    
14. Klicka på **Nästa** i fönstret **Välj platser**.
    
15. I fönstret **Namnge principen** skriver du **Organisationsexempel** i **Namn** och klickar sedan på **Nästa**.
    
16. Klicka på **publicera etiketter**i fönstret **Granska inställningar** .
 
Det kan ta några minuter innan bevarande etiketterna kan publiceras.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fas 3: tillämpa behållnings etiketter i dokument

I den här fasen får du reda på standard beteendet för kvarhållande av filer i mappen dokument på en SharePoint Online-webbplats och manuellt ändra etiketten för ett dokument.

Börja med att skapa en grupp webbplats på känslig nivå:
  
1. Använd en privat instans av webbläsaren och logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) med ditt globala administratörs konto.
    
2. Klicka på **SharePoint** i listan med paneler.
    
3. Klicka på **Skapa webbplats** **på fliken nytt** i webbläsaren.
    
4. På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.
    
5. I **grupp webbplatsens namn**skriver du **SensitiveFiles**.
    
6. I **grupp webbplats Beskrivning**skriver du **SharePoint-webbplats för känsliga filer**.
    
7.  I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.
    
8. I fönstret **vem vill du lägga till? klickar du** på **Slutför**.
    
Sedan konfigurerar du mappen dokument på SensitiveFiles-grupp webbplatsen efter den känsliga behållnings etiketten.
  
1. Klicka på **dokument**på **SensitiveFiles** -fliken i webbläsaren.
    
2. Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. 
    
3. Under **behörigheter och hantering**klickar **du på tillämpa etikett på objekt i den här listan eller det här biblioteket**. Om det här alternativet inte visas har dina bevarande etiketter ännu inte publicerats. Prova det här steget senare.
    
4. I **Inställningar – Använd etikett**, Välj **känslig** i list rutan och klicka sedan på **Spara**.

Skapa sedan ett nytt dokument på SensitiveFiles-webbplatsen och ändra etikettens etikett.
    
1. Klicka på **nytt > Word-dokument**i mappen dokument.
    
2. Skriv lite text i det tomma dokumentet. Vänta tills texten har sparats.
    
3. Klicka på **delade dokument**i meny raden.
    
4. Klicka på den lodräta ellipsen bredvid **Document.docx** fil namn och klicka sedan på **information**.
    
5. I det högra fönstret, i avsnittet **Egenskaper** , under **tillämpa bevarande etikett**, ser du att dokumentet har den **känsliga** behållnings etiketten automatiskt tillämpad.
    
6. Klicka på **Redigera alla**.
    
7. Markera den **mycket konfidentiella** etiketten under **Använd bevarande etikett**i **Document.docx** fönstret och klicka sedan på **Spara**.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare funktioner för [informations skydd](m365-enterprise-test-lab-guides.md#information-protection) i test miljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)

 
