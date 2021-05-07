---
title: Set up Information Rights Management (IRM) in SharePoint admin center
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Lär dig hur du SharePoint online-IRM via Microsoft Azure Active Directory Rights Management Services (RMS) för att skydda SharePoint och dokumentbibliotek.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162039"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Set up Information Rights Management (IRM) in SharePoint admin center

I SharePoint Online tillämpas IRM-skyddet på filer på list- och biblioteksnivå. Innan din organisation kan använda IRM-skydd måste du först konfigurera Rättighetshantering. IRM använder sig av tjänsten Azure Rights Management från Azure Information Protection för att kryptera och tilldela användningsbegränsningar. Vissa Microsoft 365 omfattar Azure Rights Management, men inte alla. Mer information finns i Hur [Office program och tjänster har stöd för Azure Rights Management.](/azure/information-protection/understand-explore/office-apps-services-support)
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Aktivera IRM-tjänsten i SharePoint administrationscenter

Innan din organisation kan IRM-skydda SharePoint och bibliotek måste du först aktivera rättighetshanteringstjänsten för din organisation. Mer information finns i [Aktivera Azure Rights Management](/information-protection/deploy-use/activate-service). Du måste använda ett arbets- eller skolkonto som har global administratörsbehörighet för att aktivera rättighetshanteringstjänsten. Annars kan du inte använda IRM-funktioner med SharePoint Online.
  
När du har aktiverat rättighetshanteringstjänsten loggar du in på SharePoint för att aktivera IRM.
  
1. Logga in som global administratör SharePoint administratör.
    
2. Välj ikonen för startprogrammet Ikonen för startprogrammet i Office 365 i det övre vänstra hörnet och välj Admin för att ![ ](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) öppna Microsoft 365 administrationscenter.  (Om du inte ser administratörspanelen har du inte administratörsbehörighet i din organisation.) 
    
3. I den vänstra rutan väljer du **Administrationscenter** \> **SharePoint**.
    
4. I det vänstra fönstret väljer **du inställningar** och sedan sidan för **klassiska inställningar.**
    
5. I avsnittet **IRM (Information Rights Management)** väljer du Använd **IRM-tjänsten** som angetts i konfigurationen och sedan **Uppdatera IRM-Inställningar**. När du har uppdaterat IRM-inställningarna kan personer i organisationen börja använda IRM i sina SharePoint-listor och dokumentbibliotek. Det kan dock ta upp till en timme innan alternativen för att göra det visas i Inställningar och Lista Inställningar.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>Aktivera IRM för SharePoint dokumentbibliotek och listor
<a name="__toc220831191"> </a>

När IRM-inställningarna har uppdaterats kan webbplatsägare IRM-skydda SharePoint-listor och dokumentbibliotek. Mer information finns i Tillämpa [IR (Information Rights Management) på en lista eller ett bibliotek.](apply-irm-to-a-list-or-library.md)
  
Om webbplatsägare aktiverar IRM för en lista eller ett bibliotek skyddas alla filtyper som stöds i listan eller biblioteket. När IRM har aktiverats för ett bibliotek tillämpas rättighetshantering på alla filerna i biblioteket. När du aktiverar IRM för en lista gäller rättighetshantering endast filer som är kopplade till listobjekt, inte de faktiska listobjekten.
  
När personer laddar ned filer i en lista eller ett bibliotek med IRM krypteras filerna så att endast behöriga personer kan visa dem. Alla rättighet hanterade filer innehåller också en utfärdningslicens som begränsningar för de personer som kan visa filen. Vanliga begränsningar är att skrivskydda en fil, inaktivera textkopiering, hindra andra från att spara lokala kopior och hindra personer från att skriva ut filen. I klientprogram som kan läsa filtyper med IRM-stöd används utfärdningslicensen för att tillämpa begränsningarna i den rättighetsbaserade filen. På så sätt bibehålls skyddet för de rättighetsskyddade filer även efter att de hämtats. Information om hur du aktiverar IRM för en lista eller ett bibliotek finns [i Tillämpa IRM (Information Rights Management) på en lista eller ett bibliotek.](apply-irm-to-a-list-or-library.md)
  
Du kan inte skapa eller redigera dokument i ett IRM-aktiverat bibliotek Office i en webbläsare. I stället kan en person i taget ladda ned och redigera IRM-krypterade filer. Använd incheckning och utcheckning för att hantera samtidig redigering  *eller*  redigering för flera användare. 
  
När du laddar ned en PDF-fil från ett IRM-skyddat bibliotek Microsoft 365 en skyddad PDF-fil. Filens filnamnstillägg ändras inte, men filen är skyddad. För att kunna visa den här filen behöver du Azure Information Protection-visningsprogrammet, den fullständiga Azure Information Protection-klienten eller ett annat program som har stöd för visning av skyddade PDF-filer. 
  
SharePoint Online har stöd för kryptering av följande filtyper:
  
- PDF
    
- 97–2003-filformaten för följande Microsoft Office program: Word, Excel och PowerPoint
    
- Dialogrutan Office XML-format för följande Microsoft Office program: Word, Excel och PowerPoint
    
- XPS-format (XML Paper Specification)
 
> [!NOTE]
> IRM-skydd kan inte tillämpas på skyddade dokument (t.ex. digitalt signerade PDF-filer) eftersom SharePoint måste öppna dokumentet vid uppladdning. 

## <a name="next-steps"></a>Nästa steg
<a name="__toc220831191"> </a>

När du har aktiverat IRM för SharePoint Online kan du börja tillämpa rättighetshantering på listor och bibliotek. Mer information finns i [Tillämpa IR (Information Rights Management) på en lista eller ett bibliotek.](apply-irm-to-a-list-or-library.md)
  
Den nya OneDrive-synkroniseringsklienten för Windows har nu stöd för synkronisering av IRM-skyddade SharePoint-dokumentbibliotek och OneDrive-platser (så länge IRM-inställningen för biblioteket inte är inställd på att upphöra att gälla för åtkomstbehörigheter för dokument). Mer information och hur du kommer igång med distributionen av den nya synkroniseringsklienten finns i Distribuera den [nya synkroniseringsklienten OneDrive för Windows.](/onedrive/deploy-on-windows)
  
[Top of page](set-up-irm-in-sp-admin-center.md)