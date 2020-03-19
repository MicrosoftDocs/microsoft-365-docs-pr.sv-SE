---
title: Bekämpa skräppost som skickas till Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
ms.collection:
- M365-security-compliance
description: Microsofts färdplan för e-postsäkerhet innebär en oöverträffad produktövergripande metod. Exchange Online Protection (EOP) anti-spam och anti-phishing filtrering teknik tillämpas över Microsofts e-postplattformar för att ge användarna de senaste anti-spam och anti-phishing verktyg och innovationer i hela nätverket. Målet för EOP är att erbjuda en omfattande och användbar e-posttjänst som hjälper till att upptäcka och skydda användare från skräppost, bedrägliga e-posthot (nätfiske) och skadlig kod.
ms.openlocfilehash: 888df6224007471db46b669ac4ffe33983057115
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805447"
---
# <a name="fighting-junk-email-sent-to-office-365"></a>Bekämpa skräppost som skickas till Office 365

Microsofts färdplan för e-postsäkerhet innebär en oöverträffad produktövergripande metod. Exchange Online Protection (EOP) anti-spam och anti-phishing filtrering teknik tillämpas över Microsofts e-postplattformar för att ge användarna de senaste anti-spam och anti-phishing verktyg och innovationer i hela nätverket. Målet för EOP är att erbjuda en omfattande och användbar e-posttjänst som hjälper till att upptäcka och skydda användare från skräppost, bedrägliga e-posthot (nätfiske) och skadlig kod.
  
## <a name="the-challenge"></a>Utmaningen

E-post har blivit ett viktigt kommunikationsverktyg inte bara för konsumenterna utan även för marknadsförare, supportpersonal, säljorganisationer och företag av alla storlekar. Som e-postanvändning har ökat, så har e missbruk. Oövervakad skräppost kan täppa till inkorgar och nätverk, påverka användarnas tillfredsställelse och hindra effektiviteten i legitim e-postkommunikation. Det är därför Microsoft fortsätter att investera i anti-spam-teknik. Enkelt uttryckt, det börjar med att innehålla och filtrera skräppost. 
  
## <a name="our-efforts"></a>Våra ansträngningar

EOP erbjuder ett antal steg för att minimera den negativa inverkan skräppost har på våra användares e-postupplevelse.
  
### <a name="exchange-online-protection-technology"></a>Exchange Online Protection-teknik

För att minska skräpposten innehåller EOP skräppostskydd med hjälp av egenutvecklade EOP-filtreringstekniker som skärm e-post för att identifiera och separera skräppost från legitim e-post. EOP-innehållsfiltret lär sig av kända skräppost- och nätfiskehot och användarfeedback från vår konsumentplattform, Outlook.com. Dessa typer av data hjälper till att utbilda EOP-teknik för att känna igen legitim e-post och skräppost och är viktiga ingångar till avsändarens rykte. Pågående feedback från EOP-användare i skräppostklassificeringsprogrammet hjälper till att säkerställa att EOP-teknikerna tränas och förbättras kontinuerligt.
  
#### <a name="how-does-eop-work"></a>Hur fungerar EOP?

När en extern användare skickar ett e-postmeddelande till en EOP-användare utvärderar EOP-filtreringstekniker meddelandets innehåll och tilldelar meddelandet en klassificering baserat på sannolikheten för att meddelandet är skräppost. Den här klassificeringen lagras som en meddelandeegenskap som kallas en SCL (Spam Confidence Level) i själva meddelandet. SCL-klassificeringen stannar med meddelandet när det skickas till andra anti-spam-skyddslager inom EOP. 
  
Regler i EOP är inställda på att hantera e-postmeddelanden med olika SCL-klassificeringar. Om ett meddelande har en SCL-klassificering som är högre än ett visst tröskelvärde betraktas det som skräppost. Meddelandet kommer att sättas i karantän eller levereras till användarens skräppostmapp beroende på hur systemadministratören konfigurerar alternativet för skräppostleverans.
  
#### <a name="eop-filters"></a>EOP-filter

Förutom anti-spam filtrering teknik, EOP ger också systemadministratören möjlighet att ställa in filternivåer för att ytterligare anpassa leveransen av e-post till sina användarkonton. Administratörer kan enkelt lägga till en avsändare eller domännamn i listan Betrodda avsändare och domäner så att e-postmeddelandet från avsändaren eller domänen aldrig behandlas som skräppost oavsett meddelandets innehåll. Information finns [i Säkra avsändare och blockerade avsändarelistor i Exchange Online](safe-sender-and-blocked-sender-lists-faq.md).
  
### <a name="phishing-protection"></a>Skydd mot nätfiske

Nätfiske (uttalas "fiske") är en form av identitetsstöld och en av de snabbast växande hoten på Internet. Du kan ofta identifiera ett nätfiskemeddelande när det begär personlig eller ekonomisk information eller innehåller en länk till en webbplats som begär sådan information. EOP erbjuder nätfiskeskydd som en del av den egenutvecklade EOP-filtreringstekniken. EOP-filtreringstekniker analyserar e-post för att upptäcka bedrägliga länkar eller falska domäner för att skydda användare från dessa typer av onlinebedrägerier.
  
#### <a name="how-does-phishing-protection-work"></a>Hur fungerar nätfiskeskydd?

Ofta skickas ett nätfiskemeddelande som innehåller en länk, när du har klickat på länken omdirigerar användarna till en bedräglig webbplats som verkar giltig (som din finansiella institution eller onlinetjänst). Den här nätfiskewebbplatsen uppmanar vanligtvis användarna att ange personlig information som användarnamn, lösenord och personnummer. All information du anger på nätfiskewebbplatsen hjälper phisher att stjäla din identitet. Genom att använda välkända betrodda varumärken och logotyper, phishers kan verka legitima. Nätfiskefilterteknik som erbjuds i EOP-kontroller för potentiella nätfiskeegenskaper i e-post. Om det hittas flyttas e-postmeddelandet till mappen Skräppost.
  
Microsoft fokuserar sina insatser mot nätfiske på två fronter: för det första genom att hjälpa till att förhindra att nätfiskemeddelanden når våra användare och för det andra genom att hjälpa till att eliminera möjligheten för användare att bli lurade av falska e-postmeddelanden och webbplatser. 
  
> [!TIP]
> Internet Explorer version 7 och senare blockerar eller varnar användare när de besöker kända eller potentiella nätfiskewebbplatser så att de inte luras att tillhandahålla personlig information. [Kontrollera att du har den senaste versionen av Internet Explorer](https://www.microsoft.com/windows/ie/default.mspx). 
  
#### <a name="authentication"></a>Autentisering

Domän spoofing är ett sätt att imitera en legitim e-postadress för att göra bedrägliga e-post ser legitima. Spoofing används av illvilliga personer eller organisationer i nätfiskebedrägerier för att locka människor att avslöja känslig personlig information. Utlämnande av sådan information kan leda till att stölder och andra typer av bedrägerier identifieras.
  
EOP använder Sender Protection Framework (SPF), DomainKeys Identified Mail (DKIM) och Domänbaserad meddelandeautentisering, rapportering och konformitet (DMARC) och andra implicita autentiseringar för att verifiera att meddelanden kom från den domän de påstår sig komma från . Vi rekommenderar att alla avsändare använder SPF och DKIM för att skydda sina mottagare från skräppost och nätfiske. Vi rekommenderar avsändare att överväga att publicera en DMARC för att avvisa eller sätta e-post som skickas från obehöriga avsändare.
  
- Mer information om SPF finns i [RFC 7208](https://tools.ietf.org/html/rfc7208) [och Policy Framework för avsändare](https://www.openspf.org/).
    
- Mer information om DKIM finns i [RFC 6376](https://tools.ietf.org/html/rfc6376) och [DKIM.org](https://dkim.org/).
    
- Mer information om DMARC finns [i DMARC.org](https://dmarc.org/).
    
### <a name="legislation"></a>Lagstiftning

På Microsoft anser vi att utvecklingen av ny teknik och självreglering kräver stöd från effektiv statlig politik och rättsliga ramar. Den världsomspännande spam spridning har sporrat många lagstiftande organ att reglera kommersiella e-post. Många länder/regioner har nu lagar om förebyggande av skräppost. USA har både federala och statliga lagar som styr spam, och denna kompletterande strategi hjälper till att begränsa spam samtidigt som legitima e-handel att blomstra. CAN-SPAM Act utökar de verktyg som finns tillgängliga för att stävja bedrägliga och bedrägliga e-postmeddelanden.
  

