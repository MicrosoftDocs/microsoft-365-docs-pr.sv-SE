---
title: Skapa signaturer och fri skrivningar för hela organisationen
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
- seo-marvel-may2020
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Lär dig hur du hanterar e-postsignaturer, inklusive juridiska fri skrivningar eller undersöknings program för alla e-postmeddelanden som anger eller lämnar din organisation.
ms.openlocfilehash: 9e438b42eb95dced4c3b99d21c66011365b180c9
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906507"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Skapa signaturer och fri skrivningar för hela organisationen

 Du kan hantera e-postsignaturer genom att lägga till ett e-postmeddelande, juridiskt fri skrivning eller meddelande till e-postmeddelanden som anger eller lämnar din organisation. Du kan konfigurera den så att den gäller för alla inkommande och utgående meddelanden som visas nedan. Eller så kan du använda den på vissa meddelanden, till exempel dem som innehåller specifika ord eller textmönster.

 Titta på en kort video om hur du skapar en e-postsignatur för hela företaget. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Skapa en signatur som gäller för alla meddelanden

> [!TIP]
> Alla signaturer kallas för "fri skrivningar", oavsett vad de innehåller. De kan till exempel vara en signatur, eller inkludera din adress, juridiske fri skrivning eller annan information som du vill ha.
    
::: moniker range="o365-worldwide"

Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Välj Start ![ ikon för app Start programmet ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) och välj sedan **admin**.
   
    Hittar du inte appen du söker? Från Start programmet väljer du **alla appar** för att se en alfabetisk lista över de program som är tillgängliga för dig. Därifrån kan du söka efter en specifik app. 
    
2. Välj **administrations Center** och välj sedan **Exchange**.
    
3. Välj **regler** under e-postflöde.
    
4. Välj **+** ikonen (Lägg till) och välj **tillämpa fri skrivningar**.
    
5. Ge regeln ett namn.
    
6. Under **Använd den här regeln** väljer du **[Använd för alla meddelanden]**.
    
    > [!TIP]
    > [Läs mer](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) om att använda villkor om du inte vill ha med ansvarsfriskrivningen i alla meddelanden. (Den här artikeln är avsedd för Exchange Server, men gäller även Microsoft 365.) 
  
7. Under Gör följande lämnar du **Lägg till ansvarsfriskrivningen** markerat. 
    
8.  Välj **Skriv text** och skriv din fri skrivning. 
    
    > [!TIP]
    > [Läs mer](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) om att formatera ansvarsfriskrivningar. (Den här formateringselement är för Exchange Server, men gäller även Microsoft 365.) 

9. Välj **Välj en** och välj **Radbryt** för att hitta ett reserv alternativ. Välj sedan **OK**. Det innebär att om ansvarsfriskrivningen inte kan läggas till på grund av kryptering eller en annan e-postinställning kommer den att inneslutas i ett meddelandekuvert.
    
10. Lämna **Granska den här regeln med allvarlighetsnivå** markerat. Välj sedan **Låg** , **Medium** eller **Hög** för användning i meddelandeloggen. 
    
11. Välj **Tillämpa** för att aktivera ansvarsfriskrivningen direkt, såvida du inte vill testa den först. 
    
12. Välj **Fler alternativ** om du vill inkludera ytterligare villkor eller undantag. 
    
13. När du är klar väljer du **Spara**. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Begränsningar i organisationens olika signaturer

Du kan inte göra följande när du hanterar e-postsignaturer i Microsoft 365:
  
- Infoga signaturen direkt under det senaste svaret eller vidarebefordran
    
- Visa e-postsignaturer från Server sidan i användarnas mappar med skickat
    
- Bädda in bilder i e-postsignaturer
    
- Hoppa över rader som innehåller variabler som inte kunde uppdateras (t. ex för att värdet inte är angivet för en användare)
    
För att få dessa och andra möjligheter att hantera e-postsignaturer kan du använda ett verktyg från tredje part. Gör en Internets ökning för **e-postsignatur**. Ett antal leverantörer är Microsoft Gold-partners och deras program vara erbjuder dessa funktioner. 
  
## <a name="more-resources"></a>Fler resurser

- Information om hur du använder PowerShell finns i "avbeställre [för hela organisationen, signaturer, sid fötter eller rubriker i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) .