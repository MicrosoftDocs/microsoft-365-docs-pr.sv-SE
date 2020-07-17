---
title: Skapa organisationsomfattande signaturer och ansvarsfriskrivningar
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Lär dig att lägga till e-postsignatur, ansvarsfriskrivning eller avslöjandeutdrag i alla e-postmeddelanden som kommer in i eller lämnar organisationen.
ms.openlocfilehash: d7e19c6e3f425f95429aefd769d2b8992fde141e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779887"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Skapa organisationsomfattande signaturer och ansvarsfriskrivningar

 Du kan lägga till en e-postsignatur, en juridisk ansvarsfriskrivning eller en policy om konfidentialitet i e-postmeddelanden som skickas till eller från din organisation. Du kan konfigurera den så att den gäller för alla inkommande och utgående meddelanden som visas nedan. Eller så kan du använda den på vissa meddelanden, till exempel dem som innehåller specifika ord eller textmönster.

 Titta på en kort video om hur du skapar en företagsomfattande e-postsignatur. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Skapa en signatur som gäller för alla meddelanden

> [!TIP]
> Organisationsomfattande signaturer kallas "ansvarsfriskrivningar", oavsett vad de innehåller. De kan till exempel bara vara en signatur, eller även inkludera din adress, ansvarsfriskrivning eller annan information som du vill ha.
    
::: moniker range="o365-worldwide"

Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Välj startprogrammet ![ Ikonen för startprogrammet ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) och välj sedan **Admin**.
   
    Hittar du inte appen du söker? I startprogrammet väljer du **Alla appar** för att se en alfabetisk lista över de appar som är tillgängliga för dig. Därifrån kan du söka efter en specifik app. 
    
2. Välj **Administrationscenter**och välj sedan **Exchange**.
    
3. Under E-postflöde väljer du **Regler**.
    
4. Markera **+** ikonen (Lägg till) och välj **Använd ansvarsfriskrivningar**.
    
5. Ge regeln ett namn.
    
6. Under **Använd den här regeln**väljer du **[Använd på alla meddelanden]**.
    
    > [!TIP]
    > [Läs mer](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) om att använda villkor om du inte vill ha med ansvarsfriskrivningen i alla meddelanden. (Den här artikeln gäller Exchange Server, men den gäller även Microsoft 365.) 
  
7. Under Gör följande lämnar du **Lägg till ansvarsfriskrivningen** markerat. 
    
8.  Välj **Ange text** och skriv ansvarsfriskrivningen. 
    
    > [!TIP]
    > [Läs mer](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) om att formatera ansvarsfriskrivningar. (Den här formateringsartikeln är avsedd för Exchange Server, men den gäller även Microsoft 365.) 

9. Välj **Välj ett** och välj **Radbryt** som reservalternativ. Välj sedan **OK**. Det innebär att om ansvarsfriskrivningen inte kan läggas till på grund av kryptering eller en annan e-postinställning kommer den att inneslutas i ett meddelandekuvert.
    
10. Lämna **Granska den här regeln med allvarlighetsnivå** markerat. Välj sedan **Låg**, **Medium** eller **Hög** för användning i meddelandeloggen. 
    
11. Välj **Tillämpa** för att aktivera ansvarsfriskrivningen direkt, såvida du inte vill testa den först. 
    
12. Välj **Fler alternativ** om du vill inkludera ytterligare villkor eller undantag. 
    
13. När du är klar väljer du **Spara**. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Begränsningar av organisationsomfattande signaturer

Du kan inte göra följande med Microsoft 365-signaturer:
  
- Infoga signaturen direkt under det senaste e-postmeddelandet eller vidarebefordra
    
- Visa e-postsignaturer på serversidan i mapparna Skickat objekt
    
- Bädda in bilder i e-postsignaturer
    
- Hoppa över rader som innehåller variabler som inte kunde uppdateras (t.ex. eftersom värdet inte angavs för en användare)
    
Använd ett verktyg från tredje part för att få dessa och andra funktioner. Gör en sökning på Internet efter **e-signatur programvara**. Ett antal av dessa leverantörer är Microsoft Gold Partners och deras programvara tillhandahåller dessa funktioner. 
  
## <a name="more-resources"></a>Fler resurser

- Mer information om hur du använder PowerShell finns [i ansvarsfriskrivningar för hela organisationen, signaturer, sidfötter eller sidhuvuden i Microsoft 365.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) 
    

