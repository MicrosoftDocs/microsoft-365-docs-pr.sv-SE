---
title: Skicka meddelanden om skräppost, icke-skräppost och nätfiske till Microsoft för analys
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
ms.openlocfilehash: 27e0698d1ad7d05adfa69e18e9b5b21edb74b1eb
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893652"
---
# <a name="submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis"></a>Skicka meddelanden om skräppost, icke-skräppost och nätfiske till Microsoft för analys

Det kan vara frustrerande när användare i organisationen får meddelanden om skräppost eller nätfiskebedrägeri i inkorgen, eller om de inte får ett legitimt e-postmeddelande eftersom det är markerat som skräppost. Vi finjusterar ständigt våra skräppostfilter för att vara mer exakta. Du och dina användare kan hjälpa den här processen genom att skicka falska negativa och falska positiva skräppostmeddelanden till Microsoft för analys. En "falsk negativ" är ett spam-meddelande som borde ha varit men identifierades inte som spam. Ett "falskt positivt" är ett legitimt e-postmeddelande som felaktigt identifierades som skräppost.

> [!NOTE]
> På grund av den stora mängden inlagor som vi får kanske vi inte kan svara på alla förfrågningar om analys.

Administratörer kan skicka e-post, url och bilagor till Microsoft för granskning. Se [Administratörsinlämningar i Office 365 ATP](admin-submission.md).

## <a name="submit-junk-or-phishing-messages-that-passed-through-the-spam-filters"></a>Skicka skräp- eller nätfiskemeddelanden som skickas genom skräppostfiltren

Om du får ett meddelande som skickades genom skräppostfiltren som och ska klassificeras som skräppost eller ett nätfiskebedrägeri kan du skicka meddelandet "falskt negativt" till teamen för Analys av skräppost och Microsofts nätfiskeanalys, beroende på vad som är lämpligt. Analytikerna granskar meddelandet och lägger till det i de serviceomfattande filtren om det uppfyller klassificeringskriterierna.

Fler skräppostinställningar som gäller för hela organisationen finns i [Skydd mot skräppost i Office 365](anti-spam-protection.md). Den här artikeln innehåller tips för att förhindra falska negativ.

Du kan skicka skräppostmeddelanden på följande sätt:

- För Outlook och Outlook på webbanvändarna använder du tillägget Rapportmeddelande för Microsoft Outlook. Information om hur du installerar och använder det här verktyget finns [i Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md).

- Du kan också använda e-post för att skicka meddelanden till Microsoft som ska klassificeras som skräppost eller nätfiskebedrägerier, enligt beskrivningen i följande procedur.

### <a name="use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft"></a>Använd e-post för att skicka skräppost eller meddelanden om nätfiske till Microsoft

Så här skickar du ett meddelande om skräppost eller nätfiske till Microsoft:

1. Skapa ett tomt e-postmeddelande.

2. Adressera meddelandet till Microsoft-teamet som granskar meddelanden enligt följande:

   - För skräppost: junk@office365.microsoft.com

   - För meddelanden om nätfiske: phish@office365.microsoft.com

3. Kopiera och klistra in meddelandet om skräppost eller nätfiske i det nya meddelandet som en bifogad fil.

   > [!NOTE]
   > * Du kan bifoga flera meddelanden i det nya meddelandet. Kontrollera att alla meddelanden är av samma typ: antingen meddelanden om nätfiske eller skräppost. <br/><br/>* Lämna brödtexten i det nya meddelandet tom. <br/><br/>* Använd antingen MSG-format (standardformatet Outlook) eller .eml (standardformatet Outlook på webben) för de bifogade meddelandena.

4. Klicka på **Skicka**.

## <a name="submit-messages-that-were-tagged-as-junk-but-should-have-been-allowed-through"></a>Skicka meddelanden som har taggats som skräppost men som borde ha tillåtits genom

Om ett meddelande har identifierats felaktigt som skräppost kan du skicka meddelandet "falskt positivt" till Microsoft Spam Analysis Team. Analytikerna kommer att utvärdera och analysera meddelandet. Beroende på resultatet av analysen kan reglerna för skräppostinnehållsfilter justeras så att meddelandet kan skickas igenom.

Administratörer kan granska mer information om skräppostinställning som gäller för en hel organisation. Se [Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365.md). Den här informationen är användbar om du har kontroll på administratörsnivå och vill förhindra falska positiva identifieringar.

Du kan skicka meddelanden som inte är skräppost på följande sätt:

- Om du använder åtgärden **Flytta meddelande till skräppost när** du konfigurerar innehållsfiltren (det här är standardåtgärden) kan användare släppa falska positiva meddelanden i mappen Outlook eller Outlook på webben (tidigare kallat Outlook Web App) skräppostmapp.

  - Outlook-användare kan släppa falska positiva meddelanden med hjälp av alternativet **Inte skräppost** högerklicka på menyn. De måste dock skicka meddelandet till Microsoft via e-post, vilket visas i proceduren i den här artikeln.

  - Outlook på webben användare kan släppa falska positiva meddelanden och skicka dem till Microsoft för analys med hjälp av **Mark som inte skräp** åtgärd. Mer information om hur du gör detta finns [i Rapportera skräppost och nätfiskebedrägerier i Outlook på webben ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).

- Om du använder åtgärden **Karantänmeddelande** i stället för åtgärden **Flytta meddelande till skräppost när** du konfigurerar innehållsfiltren:

  - Administratörer kan släppa skräppostmeddelanden i karantän och rapportera dem som falska positiva resultat från administrationscentret för Exchange. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).

  - Användare kan släppa sina egna skräppostmeddelanden i karantän och rapportera dem som falska positiva genom följande kanaler:

  - Användargränssnittet för Exchange admin center (EAC). Mer information finns i [Hitta och släppa meddelanden i karantän (slutanvändare)](find-and-release-quarantined-messages-as-a-user.md).

  - Meddelanden om skräppost för slutanvändare (om de är aktiverade av administratören).

- Du kan också använda e-post för att skicka meddelanden till Microsoft som inte bör klassificeras som skräppost. När du gör detta kontrollerar du att du använder stegen i följande procedur.

### <a name="use-email-to-submit-false-positive-messages"></a>Använd e-post för att skicka falska positiva meddelanden

Använd samma procedur som beskrivs i [e-postmeddelandet Använd för att skicka meddelanden om skräppost eller nätfiske till Microsoft,](#use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft) men skicka meddelandet till not_junk@office365.microsoft.com.

## <a name="spam-evaluation-and-rules-deployment"></a>Spam utvärdering och regler distribution

Skräppostanalysteamet undersöker meddelanden som du skickar in och justerar skräppostfiltren för att förhindra framtida skräppost. Därför förfinas skräppostfilter för Office 365 noggrant. Alla inskickade objekt utvärderas på nätverksomfattande nivå. Falska positiva inlagor undersöks och bedöms för eventuell regeljustering för att tillåta framtida meddelanden via skräppostfiltren. Därför är det fördelaktigt för dig och alla kunder som använder det globala nätverket att meddela tjänsten för falska positiva identifieringar och även falska negativ (ofiltrerad skräppost). Skräppostteamet undersöker indikatorer i varje skickat meddelande, till exempel följande:

- Från adress

- Skicka IP-adress

- Sökord

- Fraser

- Sändningsfrekvens

- Andra trender och mönster

När de har granskat den här informationen kan skräppostteamet göra ändringar i tjänstens skräppostfiltreringslager. Om du vill ha mer information om skräppostteamet kan du titta på följande engelska video:

[Video för Microsoft Exchange Spam-teamet](https://youtu.be/-TpX_-GMC7o?hd=1)

Spam utvärdering är en pågående process som gäller oavsett ursprungsspråk eller teckenuppsättning. Eftersom ett skräppostmeddelande kan vara vagt eller till och med sakna text i ämnes- eller meddelandetexten, förlitar sig skräppostteamet på andra meddelandeegenskaper för att utföra filtrering. Detta innebär att efter spam team flaggor ett visst meddelande som spam och gör nödvändiga ändringar i sin regelbas, kommer att meddelandet blockeras i framtiden tills dess egenskaper har ändrats tillräckligt för att undvika våra filter. Nya skräppostregler distribueras kontinuerligt. Tidsramarna för regler för enskilda inlämningar varierar beroende på antalet och kvaliteten på inlämningarna. Eftersom nya skräppostregler ställs in globalt för alla kunder resulterar inte alla enskilda skräppostinlägg i en ny skräppostregel.
