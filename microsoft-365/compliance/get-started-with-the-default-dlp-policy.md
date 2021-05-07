---
title: Kom igång med DLP-standardprincipen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du använder rapporten för att förfina organisationens standardprincip för skydd mot dataförlust (DLP).
ms.openlocfilehash: 4530e570f0ce593a7d2cb62acc28dfa4e1658df0
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162989"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Kom igång med DLP-standardprincipen

Innan du ens har skapat din första DLP-princip (Data Loss Prevention) hjälper DLP till att skydda känslig information med en standardprincip. Den här standardprincipen och dess rekommendation (visas nedan) hjälper dig att skydda känsligt innehåll genom att meddela dig när e-post eller dokument som innehåller ett kreditkortsnummer har delats med någon utanför organisationen. Du ser den här rekommendationen på **startsidan** för &amp; Säkerhetsefterlevnadscenter. 
  
Du kan använda den här widgeten för att snabbt visa när och hur mycket känslig information som har delats, och sedan förfina standard-DLP-principen med bara ett eller två klick. Du kan också redigera standard-DLP-principen när som helst eftersom den är helt anpassningsbar. Observera att om du inte ser rekommendationen från början kan du prova att klicka på **+Mer** längst ned i **avsnittet Rekommenderas för** dig. 
  
![Widget med namnet Ytterligare skydda delat innehåll](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Visa rapporten och förfina DLP-standardprincipen

När widgeten visar att användarna har delat känslig information med personer utanför organisationen väljer du **Förfina DLP-principen** längst ned. 
  
I den detaljerade rapporten visas när och hur mycket innehåll som innehåller kreditkortsnummer som delats de senaste 30 dagarna. Observera att regelmatchning kan ta upp till 48 timmar innan de visas i widgeten.
  
Standardprincipen för DLP gör följande för att skydda den känsliga informationen:
  
- Upptäcker när innehåll i Exchange, SharePoint och OneDrive som innehåller minst ett kreditkortsnummer delas med personer utanför organisationen.
    
- Visar ett principtips och skickar ett e-postmeddelande till användare när de försöker dela den här känsliga informationen med personer utanför organisationen. Mer information om de här alternativen finns i Skicka [e-postmeddelanden och visa principtips för DLP-principer.](use-notifications-and-policy-tips.md)
    
- Genererar detaljerade aktivitetsrapporter så att du kan spåra sådant som vem som har delat innehållet med personer utanför organisationen och när de gjorde det. Du kan använda [DLP-rapporter och](view-the-dlp-reports.md) [granskningsloggdata](search-the-audit-log-in-security-and-compliance.md) (där **aktivitet**  =  **DLP**) för att visa den här informationen.
    
Om du snabbt vill förfina standard-DLP-principen kan du välja att följande ska användas:
  
- Skicka ett e-postmeddelande med en incidentrapport när användare delar den här känsliga informationen med personer utanför organisationen.
    
- Lägg till andra användare i e-posthändelserapporten.
    
- Blockera åtkomst till innehåll som innehåller känslig information, men tillåt användaren att åsidosätta och dela eller skicka vid behov.
    
Mer information om incidentrapporter eller om att begränsa åtkomst finns i Referens [för dataförlustskydd.](data-loss-prevention-policies.md)
  
Om du vill ändra de här alternativen senare kan du redigera standard-DLP-principen när som helst – se nästa avsnitt.
  
![Inställningar för widget med namnet Ytterligare skydda delat innehåll](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Redigera standard-DLP-principen

Den här principen heter **Standard-DLP-princip** och visas under **Skydd mot dataförlust** **på** sidan Princip i &amp; Säkerhetsefterlevnadscenter. 
  
Den här principen är helt anpassningsbar, samma som alla DLP-princip du skapar själv från grunden. Du kan också inaktivera eller ta bort principen så att användarna inte längre får principtips eller e-postaviseringar.
  
![DLP-princip med namnet Standard-DLP-princip](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>När widgeten visas och inte visas

Widgeten **Med namnet Ytterligare skydd av** delat innehåll visas i **avsnittet** Rekommenderas för dig **på sidan** Start i &amp; Säkerhetsefterlevnadscenter. 
  
Den här widgeten visas bara om:
  
- Det finns inga principer för dataförlustskydd i &amp; Säkerhetsefterlevnad eller Exchange administrationscenter. Den här widgeten är avsedd att hjälpa dig att komma igång med DLP, så den visas inte om du redan har DLP-principer.
    
- Innehåll som innehåller minst ett kreditkort har delats med någon utanför organisationen under de senaste 30 dagarna.
    
Observera att regelmatchning kan ta upp till 48 timmar innan widgeten är tillgänglig, så när känslig information som delas externt har upptäckts kan det ta upp till två dagar innan rekommendationen visas.
  
Slutligen försvinner widgeten från startsidan när du använder widgeten för  att förfina standard-DLP-principen. 
  

