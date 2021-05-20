---
title: Skapa signaturer och ansvarsfriskrivningar för hela organisationen
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Hantera e-postsignaturer, inklusive ansvarsfriskrivningar eller avslöjanden för alla e-postmeddelanden som skickas till eller från organisationen.
ms.openlocfilehash: 05cfeeb01231e7f99d2a96fc37581b4c9a23f5aa
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582758"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Skapa signaturer och ansvarsfriskrivningar för hela organisationen

 Du kan hantera e-postsignaturer genom att lägga till en e-postsignatur, en juridisk ansvarsfriskrivning eller en policy om avslöjande i e-postmeddelanden som skickas till eller från organisationen. Du kan konfigurera den så att den gäller för alla inkommande och utgående meddelanden som visas nedan. Eller så kan du använda den på vissa meddelanden, till exempel dem som innehåller specifika ord eller textmönster.

 Titta på en kort video om hur du skapar en företagsomfattande e-postsignatur. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](../../business-video/index.yml).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Skapa en signatur som gäller för alla meddelanden

> [!TIP]
> Signaturer för hela organisationen kallas för ansvarsfriskrivningar, oavsett vad de innehåller. De kan till exempel bara vara en signatur eller innehålla din adress, ansvarsfriskrivning eller annan information.
    
::: moniker range="o365-worldwide"

Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Välj startprogrammet ![ Appstartikonen ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) och välj sedan **Admin**.
   
    Hittar du inte appen du söker? Från appstartaren väljer du Alla **appar för** att se en alfabetisk lista över tillgängliga appar. Därifrån kan du söka efter en specifik app. 
    
2. Välj **Administrationscenter** och välj sedan **Exchange**.
    
3. Välj Regler under **E-postflöde.**
    
4. Välj **+** ikonen (Lägg till) och välj Använd **ansvarsfriskrivningar**.
    
5. Ge regeln ett namn.
    
6. Under **Använd den här regeln** väljer du **[Använd för alla meddelanden]**.
    
    > [!TIP]
    > [Läs mer](/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) om att använda villkor om du inte vill ha med ansvarsfriskrivningen i alla meddelanden. (Den här artikeln används för Exchange Server, men den gäller även Microsoft 365.) 
  
7. Under Gör följande lämnar du **Lägg till ansvarsfriskrivningen** markerat. 
    
8.  Välj **Ange text och** skriv ansvarsfriskrivningen. 
    
    > [!TIP]
    > [Läs mer](/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) om att formatera ansvarsfriskrivningar. (Den här formateringsartikeln är Exchange Server, men den gäller även Microsoft 365.) 

9. Välj **Välj en** och välj **Radbyte** som reservalternativ. Välj sedan **OK**. Det innebär att om ansvarsfriskrivningen inte kan läggas till på grund av kryptering eller en annan e-postinställning kommer den att inneslutas i ett meddelandekuvert.
    
10. Lämna **Granska den här regeln med allvarlighetsnivå** markerat. Välj sedan **Låg**, **Medium** eller **Hög** för användning i meddelandeloggen. 
    
11. Välj **Tillämpa** för att aktivera ansvarsfriskrivningen direkt, såvida du inte vill testa den först. 
    
12. Välj **Fler alternativ** om du vill inkludera ytterligare villkor eller undantag. 
    
13. När du är klar väljer du **Spara**. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Begränsningar för hela organisationens signaturer

Du kan inte göra följande när du hanterar e-postsignaturer i Microsoft 365:
  
- Infoga signaturen direkt under det senaste e-postmeddelandet eller vidarebefordra
    
- Visa e-postsignaturer på serversidan i användarnas Skickat-mappar
    
- Bädda in bilder i e-postsignaturer
    
- Hoppa över rader som innehåller variabler som inte kunde uppdateras (t.ex. eftersom värdet inte angavs för en användare)
    
Använd ett tredjepartsverktyg för att få dessa och andra funktioner för att hantera e-postsignaturer. Gör en internetsökning efter programvara för **e-postsignaturer.** Några av dessa leverantörer är Microsoft Gold Partners och deras programvara tillhandahåller dessa funktioner. 
  
## <a name="more-resources"></a>Fler resurser

Information om hur du använder PowerShell finns i Ansvarsfriskrivningar för meddelanden i hela [organisationen, signaturer, sidfötter och sidhuvuden i Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

## <a name="related-content"></a>Relaterat innehåll

[Migrera e-post och kontakter Microsoft 365](migrate-email-and-contacts-admin.md) (video)

[E-postinställningar för användare](../email/office-365-user-email-settings.md) (artikel)

[Översikt över administrationscenter för Microsoft 365](../../business-video/admin-center-overview.md) (video)

