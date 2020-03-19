---
title: Skicka meddelanden om skräppost, icke-skräppost och nätfiskebedrägerier till Microsoft för analys
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Du och dina användare kan skicka falska negativa och falska positiva skräppostmeddelanden till Microsoft för analys. '
ms.openlocfilehash: 7b53f74be78bc1203189815c6a7adf3337decd21
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856875"
---
# <a name="submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis"></a>Skicka meddelanden om skräppost, icke-skräppost och nätfiskebedrägerier till Microsoft för analys

Det kan vara frustrerande när användare i organisationen får skräpmeddelanden (skräppost) eller phishing-bluffmeddelanden i inkorgen, eller om de inte får ett legitimt e-postmeddelande eftersom det är markerat som skräppost. Vi finjusterar ständigt våra skräppostfilter för att vara mer exakta. Du och dina användare kan hjälpa den här processen genom att skicka falska negativa och falska positiva skräpmeddelanden till Microsoft för analys. En "falsk negativ" är ett spam-meddelande som borde ha varit men identifierades inte som skräppost. Ett "falskt positivt" är ett legitimt e-postmeddelande som felaktigt identifierades som skräppost.

> [!NOTE]
> På grund av den stora mängden inlagor som vi får kanske vi inte kan svara på alla förfrågningar om analys.

Administratörer kan skicka e-post, url och bilagor till Microsoft för granskning. Se [Administratörsinlämningar i Office 365 ATP](admin-submission.md).

## <a name="submit-junk-or-phishing-messages-that-passed-through-the-spam-filters"></a>Skicka skräp- eller nätfiskemeddelanden som passerade skräppostfiltren

Om du får ett meddelande som passerade via skräppostfiltren som och bör klassificeras som skräppost eller nätfiskebedrägeri kan du skicka det "falska negativa" meddelandet till Microsoft Spam Analysis och Microsoft Phishing Analysis-team, beroende på vad som är lämpligt. Analytikerna kommer att granska meddelandet och lägga till det i serviceomfattande filter om det uppfyller klassificeringskriterierna.

Mer skräppostinställningar som gäller för hela organisationen finns i [Blockera skräppost via e-post med skräppostfiltret för Office 365 för att förhindra falska negativa problem](reduce-spam-email.md). Den här artikeln innehåller tips för att förhindra falska negativ.

Du kan skicka skräppost på följande sätt:

- För Outlook och Outlook på webbanvändarna använder du tillägget Rapportmeddelande för Microsoft Outlook. Information om hur du installerar och använder det här verktyget finns [i Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md).

- Du kan också använda e-post för att skicka meddelanden till Microsoft som ska klassificeras som skräppost eller nätfiskebedrägerier, enligt beskrivningen i följande procedur.

### <a name="use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft"></a>Använda e-post för att skicka skräp (skräppost) eller phishing-bluffmeddelanden till Microsoft

Så här skickar du ett skräp- eller nätfiskebedrägerimeddelande till Microsoft:

1. Skapa ett tomt e-postmeddelande.

2. Adressera meddelandet till Microsoft-teamet som granskar meddelanden enligt följande:

   - För skräpmeddelanden: junk@office365.microsoft.com

   - För nätfiskebluffmeddelanden: phish@office365.microsoft.com

3. Kopiera och klistra in skräp- eller nätfiskebluffmeddelandet i det nya meddelandet som en bifogad fil.

   > [!NOTE]
   > • Du kan bifoga flera meddelanden i det nya meddelandet. Se till att alla meddelanden är samma typ: antingen phishing-bluffmeddelanden eller skräppostmeddelanden. <br/><br/>• Lämna det nya meddelandets brödtext tom. <br/><br/>• Använd antingen MSG-format (standardformat i Outlook) eller .eml (standardOutlook i webbformat) för bifogade meddelanden.

4. Klicka på **Skicka**.

## <a name="submit-messages-that-were-tagged-as-junk-but-should-have-been-allowed-through"></a>Skicka meddelanden som har taggats som skräppost men som borde ha tillåtits genom

Om ett meddelande har identifierats felaktigt som skräppost kan du skicka meddelandet "falskt positivt" till Microsoft Spam Analysis Team. Analytikerna kommer att utvärdera och analysera meddelandet. Beroende på resultaten av analysen kan reglerna för filterfilter för hela tjänsten justeras så att meddelandet kan gå igenom.
  
Administratörer kan granska mer information om skräppostinställning som gäller för en hel organisation. Se [Så här ser du till att ett meddelande inte markeras som skräppost](prevent-email-from-being-marked-as-spam.md). Den här informationen är användbar om du har kontroll på administratörsnivå och vill förhindra falska positiva.
  
Du kan skicka meddelanden som inte är skräppost på följande sätt:

- Om du använder åtgärden **Flytta meddelande till skräppostmapp** när du konfigurerar innehållsfiltren (det här är standardåtgärden) kan användarna släppa falska positiva meddelanden i mappen Outlook eller Outlook på webben (tidigare känt som Outlook Web App) Skräppostmapp.

  - Outlook-användare kan släppa falska positiva meddelanden med hjälp av menyalternativet **Inte skräppost.** De måste dock skicka meddelandet till Microsoft via e-post, som visas i proceduren i den här artikeln.

  - Outlook på webben användare kan släppa falska positiva meddelanden och skicka dem till Microsoft för analys med hjälp av **Märket som inte skräp** åtgärd. Mer information om hur du gör detta finns i [Rapportera skräppost och nätfiskebedrägerier i Outlook på webben ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).

- Om du använder åtgärden **Karantänmeddelande** i stället för **åtgärden Flytta meddelande till skräppost mapp** när du konfigurerar innehållsfilter:

  - Administratörer kan släppa meddelanden i skräppost karantän och rapportera dem som falska positiva från administrationscentret för Exchange. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).

  - Användare kan släppa sina egna meddelanden om skräppost i karantän och rapportera dem som falska positiva genom följande kanaler:

  - Användargränssnittet i Exchange Admin Center (EAC). Mer information finns i [Sök och släpp meddelanden i karantän (slutanvändare).](find-and-release-quarantined-messages-as-a-user.md)

  - Meddelanden om skräppost meddelanden från slutanvändare (om de är aktiverade av administratören).

- Du kan också använda e-post för att skicka meddelanden till Microsoft som inte ska klassificeras som skräppost. När du gör detta kontrollerar du att du använder stegen i följande procedur.

### <a name="use-email-to-submit-false-positive-messages"></a>Använda e-post för att skicka falska positiva meddelanden

Använd samma procedur som beskrivs i [länken Använd e-post för att skicka skräp (skräppost) eller phishing-bluffmeddelanden till Microsoft,](#use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft) men skicka meddelandet till not_junk@office365.microsoft.com.

## <a name="spam-evaluation-and-rules-deployment"></a>Distribution av skräppost och regler

Spamanalysteamet undersöker meddelanden som du skickar in och justerar skräppostfiltren för att förhindra framtida skräppost. Därför förfinas skräppostfilter från Office 365 ständigt. Alla skickade objekt utvärderas på nätverksnivå. Falska positiva inlagor undersöks och bedöms för eventuell regeljustering för att möjliggöra framtida meddelanden via skräppostfiltren. Därför är det fördelaktigt för dig och alla kunder som använder det globala nätverket att meddela tjänsten om falska positiva och även falska negativ (ofiltrerat skräppost). Spam-teamet undersöker indikatorer i varje skickat meddelande, till exempel följande:

- Från adress

- Skicka IP-adress

- Sökord

- Fraser

- Överföringsfrekvens

- Andra trender och mönster

När de har granskat den här informationen kan spam-teamet göra ändringar i tjänstens skräppostfiltreringslager. Mer information om spam-teamet kan du titta på följande video endast på engelska:

[Video i Microsoft Exchange Spam-teamet](https://youtu.be/-TpX_-GMC7o?hd=1)

Spam utvärdering är en pågående process som gäller oavsett ursprungsspråk eller teckenuppsättning. Eftersom ett spam-meddelande kan vara vagt eller till och med saknar text i ämnet eller meddelandetexten, förlitar sig spam-teamet på andra meddelandeegenskaper för att utföra filtrering. Detta innebär att efter spam laget flaggor ett visst meddelande som spam och gör nödvändiga ändringar i sin regelbas, kommer detta meddelande blockeras i framtiden tills dess egenskaper har ändrats tillräckligt för att undvika våra filter. Nya skräppostregler distribueras kontinuerligt. Tidsramar för regler för enskilda inlämningar varierar beroende på antalet och kvaliteten på bidragen. Eftersom nya skräppostregler ställs in globalt för alla kunder, kommer inte alla enskilda spam-inlämningar att resultera i en ny skräppostregel.

## <a name="for-more-information"></a>Mer information

[Skydd mot skräppost och skadlig programvara](anti-spam-and-anti-malware-protection.md)
  
[Så här säkerställer du att ett meddelande inte markeras som skräppost](prevent-email-from-being-marked-as-spam.md)
  
[Block email spam with the Office 365 spam filter to prevent false negative issues](reduce-spam-email.md)
  

[Block email spam with the Office 365 spam filter to prevent false negative issues](reduce-spam-email.md)
