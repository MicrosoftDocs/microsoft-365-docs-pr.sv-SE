---
title: Hitta och undersöka skadlig e-post som levererades i Office 365, åtgärda, åtgärda, åtgärda, hotskydd, hotutforskare, skydd
keywords: TIMailData-Inline, Security Incident, incident, ATP PowerShell, e malware, komprometterade användare, e-post phish, e-malware, läsa e-postrubriker, läshuvuden, öppna e-postrubriker
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Läs om hur du använder hotundersöknings- och svarsfunktioner för att hitta och undersöka skadlig e-post.
ms.openlocfilehash: 1b7cef7f079023dd88fe3f04eb1b7d159c4157ef
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955621"
---
# <a name="investigate-and-remediate-malicious-email-that-was-delivered-in-office-365"></a>Undersöka och åtgärda skadlig e-post som levererades i Office 365

[Med Office 365 Advanced Threat Protection](office-365-atp.md) kan du undersöka aktiviteter som utsätter personer i organisationen för risker och vidtar åtgärder för att skydda din organisation. Om du till exempel ingår i organisationens säkerhetsteam kan du hitta och undersöka misstänkta e-postmeddelanden som levererades. Du kan göra detta genom att använda [Threat Explorer (eller realtidsidentifieringar)](threat-explorer.md).
  
## <a name="before-you-begin"></a>Innan du börjar...

Kontrollera att följande krav är uppfyllda:
  
- Din organisation har [Office 365 Advanced Threat Protection](office-365-atp.md) och licenser tilldelas [användare](../../admin/manage/assign-licenses-to-users.md).
    
- [Granskningsloggning av Office 365](../../compliance/turn-audit-log-search-on-or-off.md) är aktiverat för din organisation. 
    
- Din organisation har principer som definierats för anti-spam, anti-malware, anti-phishing, och så vidare. Se [Skydda mot hot i Office 365](protect-against-threats.md).
    
- Du är en global Office 365-administratör eller har rollen Säkerhetsadministratör eller sök- och rensning tilldelat i Säkerhetsefterlevnadscenter. &amp; Se [Behörigheter i &amp; Säkerhetsefterlevnadscenter för Office 365](permissions-in-the-security-and-compliance-center.md). För vissa åtgärder måste du också ha tilldelat en ny förhandsversionsroll. 

#### <a name="preview-role-permissions"></a>Förhandsgranska rollbehörigheter

Om du vill utföra vissa åtgärder, till exempel visa meddelanderubriker eller hämta e-postmeddelandeinnehåll, måste du ha en ny roll som kallas *Förhandsgranska tillagd* i en annan lämplig Office 365-rollgrupp. I följande tabell klargörs nödvändiga roller och behörigheter.

|Aktivitet  |Rollgrupp |Förhandsversionsroll behövs?  |
|---------|---------|---------|
|Använda Threat Explorer (och realtidsidentifieringar) för att analysera hot     |Global administratör för Office 365 <br> Säkerhetsadministratör <br> Säkerhetsläsare     | Nej   |
|Använda Threat Explorer (och realtidsidentifieringar) för att visa rubriker för e-postmeddelanden samt förhandsgranska och hämta e-postmeddelanden i karantän    |Global administratör för Office 365 <br> Säkerhetsadministratör <br>Säkerhetsläsare   |       Nej  |
|Använda Threat Explorer för att visa rubriker och hämta e-postmeddelanden som levereras till postlådor     |Global administratör för Office 365 <br>Säkerhetsadministratör <br> Säkerhetsläsare <br> Förhandsgranska   |   Ja      |

> [!NOTE]
> *Förhandsversion* är en roll och inte en rollgrupp. Förhandsrollen måste läggas till i en befintlig rollgrupp för Office 365. Rollen För office 365-administratör tilldelas microsoft 365-administrationscentret ([https://admin.microsoft.com](https://admin.microsoft.com)) och rollerna Säkerhetsadministratör och säkerhetsläsare tilldelas i[https://protection.office.com](https://protection.office.com)Office 365 Security & Compliance Center ( ). Mer information om roller och behörigheter finns [i Behörigheter i Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Hitta och ta bort misstänkt e-post som levererades

Threat Explorer är en kraftfull rapport som kan tjäna flera syften, till exempel att hitta och ta bort meddelanden, identifiera IP-adressen för en skadlig e-postavsändare eller starta en incident för vidare undersökning. Följande procedur fokuserar på att använda Explorer för att hitta och ta bort skadlig e-post från mottagarens postlådor.

> [!NOTE]
> Standardsökningar i Explorer innehåller för närvarande inte Zapped-objekt.  Detta gäller alla vyer, till exempel skadlig kod eller phish-vyer. Om du vill inkludera Zapped-objekt måste du lägga till en leveransåtgärd som ska inkluderas med "Borttaget av ZAP". Om du inkluderar alla alternativ visas alla resultat för leveransåtgärder, inklusive Zapped-objekt.

1. **Navigera till Threat Explorer:** Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt arbets- eller skolkonto för Office 365. Detta tar dig &amp; till Security Compliance Center.

2. I snabbstarten för vänster navigering väljer du **Explorer för hothantering** \> **.**

    ![Explorer med fälten Leveransåtgärd och Leveransplats.](../../media/ThreatExFields.PNG)

    <!-- You may notice the new **Special actions** column. This feature is aimed at telling admins the outcome of processing an email. The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**. Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.-->

3. **Vyer i Threat Explorer:** Välj **Alla e-postmeddelanden**på **Visa-menyn.**

    ![Hot explorer Visa menyn och E-post - Malware, Phish, Inlagor och alla e-postalternativ, även Innehåll - Malware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    Vyn *Skadlig kod* är för närvarande standard och fångar e-postmeddelanden där ett hot mot skadlig kod upptäcks. *Phish-vyn* fungerar på samma sätt, för Phish.

    I *alla e-postmeddelanden* visas dock alla e-postmeddelanden som tas emot av organisationen, oavsett om hot har upptäckts eller inte. Som ni kan föreställa er är detta en hel del data, vilket är anledningen till att den här vyn visar en platshållare som ber om ett filter tillämpas. (Den här vyn är endast tillgänglig för ATP P2-kunder.)

    *Vyn Inlämningar* visar alla e-postmeddelanden som skickats av administratör eller användare och som har rapporterats till Microsoft.

4. **Sök och filtrera i Threat Explorer**: Filter visas högst upp på sidan i sökfältet för att hjälpa administratörer i sina undersökningar. Observera att flera filter kan användas samtidigt och flera kommaavgränsade värden läggs till i ett filter för att begränsa sökningen. Kom ihåg:
    - Filter gör exakt matchning på de flesta filterförhållanden.
    - Ämnesfiltret använder en CONTAINS-fråga.
    - URL-filter fungerar med eller utan protokoll (t.ex. https).
    - URL-domän-, URL-sökvägs- och URL-domän- och sökvägsfilter kräver inget protokoll för att filtrera.
    - Du måste klicka på ikonen Uppdatera varje gång du ändrar filtervärdena för att få relevanta resultat.

5. **Avancerade filter:** Med dessa filter kan du skapa komplexa frågor och filtrera datauppsättningen. Om du klickar på *Avancerade filter* öppnas ett utfällbart alternativ.

   Avancerad filtrering är ett bra komplement till sökfunktionerna. Ett booleskt **NOT-filter** har introducerats på *domänen Mottagare,* *Avsändare* och *Avsändare* för att administratörer ska kunna undersöka genom att utesluta värden. Det här alternativet visas under *markeringsparametern Innehåller ingen av*. **INTE** kommer att låta administratörer utesluta varningspostlådor, standardsvarllådor svar från sina undersökningar, och är användbart för fall där administratörer söka efter ett visst ämne (subject ="Attention") där mottagaren kan ställas in på *ingen av defaultMail@contoso.com*. Detta är en exakt värdesökning.

   ![Mottagarna - "Innehåller inget av" Avancerat filter.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *Filtrering efter timmar* hjälper organisationens säkerhetsteam att snabbt öka detaljnivån. Den kortaste tillåtna tidstiden är 30 minuter. Om du kan begränsa den misstänkta åtgärden efter tidsram (t.ex. det hände för tre timmar sedan), begränsar detta sammanhanget och hjälper till att identifiera problemet.

  ![Alternativet filtrering efter timmar för att begränsa mängden datasäkerhetsteam måste bearbeta och vars kortaste varaktighet är 30 minuter.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Fält i hot explorer:** Threat Explorer exponerar mycket mer säkerhetsrelaterad e-postinformation, till exempel *Leveransåtgärd,* *Leveransplats,* *Specialåtgärd,* *Riktning,* *Åsidosättningar*och *URL-hot*. Det gör det också möjligt för organisationens säkerhetsteam att undersöka med högre säkerhet. 

    *Leveransåtgärd* är de åtgärder som vidtas på ett e-postmeddelande på grund av befintliga principer eller identifieringar. Här är de möjliga åtgärder ett e-postmeddelande kan vidta:
    - **Levererad** – e-post levererades till en användares inkorg eller mapp och användaren kan komma åt den direkt.
    - **Junked (Levererad** till skräppost)– e-post skickades till antingen användarens skräppostmapp eller borttagen mapp, och användaren har tillgång till e-postmeddelanden i sin skräppostmapp eller borttagna mapp.
    - **Blockerad** – alla e-postmeddelanden som är i karantän, som misslyckades eller togs bort. (Detta är helt otillgängligt av användaren.)
    - **Ersatt** – alla e-postmeddelanden där skadliga bilagor ersätts av .txt-filer som anger att den bifogade filen var skadlig

    **Leveransplats**: Filtret Leveransplats är tillgängligt för att hjälpa administratörer att förstå var misstänkt skadlig e-post hamnade och vilka åtgärder som vidtogs på den. De resulterande data kan exporteras till kalkylblad. Möjliga leveransplatser är:
    - **Inkorgen eller mappen** – E-postmeddelandet finns i Inkorgen eller en viss mapp, enligt dina e-postregler.
    - **On-prem eller extern** – Postlådan finns inte i molnet men är lokalt.
    - **Skräppostmapp** – E-postmeddelandet finns i en användares skräppostmapp.
    - **Mappen Borttaget objekt** – E-postmeddelandet finns i mappen Borttaget.
    - **Karantän** – E-postmeddelandet i karantän och inte i en användares postlåda.
    - **Misslyckades** – Det gick inte att nå postlådan via e-post.
    - **Tappade** - E-post förlorades någonstans i e-postflödet.

    **Riktning:** Med det här alternativet kan säkerhetsoperationsteamet filtrera efter den "riktning" som ett e-postmeddelande kommer från eller kommer. Riktningsvärden är *Inkommande,* *Utgående*och Intra-org (motsvarande *e-post* som kommer in i din organisation utifrån, skickas ut från din organisation eller skickas internt till din organisation, respektive). Den här informationen kan hjälpa säkerhetsoperationer team plats förfalskning och personifiering, eftersom en obalans mellan directionality värde (t.ex. *Inkommande*), och domänen för avsändaren (som *verkar* vara en intern domän) kommer att vara uppenbart! Riktningsvärdet är separat och kan skilja sig från meddelandespårningen. Resultaten kan exporteras till kalkylblad.

    **Åsidosättningar**: Det här filtret tar information som visas på fliken information om e-post och använder den för att exponera var organisations- eller användarprinciper, för att tillåta och blockera e-post har *åsidosatts*. Det viktigaste med det här filtret är att det hjälper organisationens säkerhetsteam att se hur många misstänkta e-postmeddelanden som levererades på grund av konfigurationen. Detta ger dem en möjlighet att ändra tillåter och block som behövs. Den här resultatuppsättningen för det här filtret kan exporteras till kalkylblad.

|Åsidosättningar av hotutforskaren  | Vad de betyder  |
|---------|---------|
|Tillåts av org policy     |   E-post tilläts komma in i postlådan enligt organisationens princip.       |
|Blockerad av org-principen      |  E-post blockerades från leverans till postlådan enligt organisationens princip.    |
|Filtillägg blockeras av Org Policy     | Filen blockerades från leverans till postlådan enligt organisationens princip.        |
|Tillåts av användarprincip     | E-post tilläts komma in i postlådan enligt anvisningarna i användarprincipen.        |
|Blockerad av användarprincip     | E-post blockerades från leverans till postlådan enligt anvisningarna i användarprincipen.        |

**URL-hot**: Url-hotfältet har inkluderats på *informationsfliken* i ett e-postmeddelande för att ange det hot som en webbadress utgör. Hot som presenteras av en webbadress kan vara *skadlig kod,* *Phish*eller *Spam*, och en webbadress *utan hot* kommer att säga *Ingen* i hot avsnitt.

7. **Tidslinjevy för e-post:** Ditt säkerhetsoperationsteam kan behöva fördjupa sig i e-postinformation för att undersöka saken ytterligare. Med e-posttidslinjen kan administratörer visa åtgärder som vidtas på ett e-postmeddelande från leverans till efterleverans. Om du vill visa en tidslinje för e-post klickar du på ämnet för ett e-postmeddelande och klickar sedan på E-posttidslinje. (Det visas bland andra rubriker på panelen som Sammanfattning eller Detaljer.) Dessa resultat kan exporteras till kalkylblad.

    E-posttidslinje öppnas för en tabell som visar alla leverans- och efterleveranshändelser för e-postmeddelandet. Om det inte finns några ytterligare åtgärder på e-postmeddelandet, bör du se en enda händelse för den ursprungliga leveransen som anger ett resultat, till exempel *Blockerad*, med en dom som *Phish*. Administratörer kan exportera hela e-posttidslinjen, inklusive all information på fliken och e-postmeddelandet (till exempel Ämne, Avsändare, Mottagare, Nätverk och Meddelande-ID). E-posttidslinjen skär ned på randomisering eftersom det finns mindre tid att kontrollera olika platser för att försöka förstå händelser som hänt sedan e-postmeddelandet kom. När flera händelser inträffar vid eller i närheten av samma tid i ett e-postmeddelande visas dessa händelser i en tidslinjevy.

8. **Preview / ladda ner:** Threat Explorer ger din säkerhetsoperation team de uppgifter de behöver för att undersöka misstänkta e-post. Säkerhetsoperationsteamet kan antingen:

    - [Kontrollera leveransåtgärden och platsen](#check-the-delivery-action-and-location).

    - [Visa tidslinjen för din e-post](#view-the-timeline-of-your-email).

    ##### <a name="check-the-delivery-action-and-location"></a>Kontrollera leveransåtgärden och platsen

    I [Threat Explorer (och realtidsidentifieringar)](threat-explorer.md)har du nu kolumner för **leveransåtgärd** och **leveransplats** i stället för den tidigare kolumnen **Leveransstatus.** Detta resulterar i en mer fullständig bild av var dina e-postmeddelanden landar. En del av målet med denna förändring är att göra utredningar lättare för säkerhetsoperationer team, men nettoresultatet är att veta platsen för problem e-postmeddelanden på ett ögonblick.

    Leveransstatus är nu uppdelad i två kolumner:

    - **Leveransåtgärd** - Vad är status för det här e-postmeddelandet?

    - **Leveransplats** - Var dirigerades det här e-postmeddelandet som ett resultat?

    Leveransåtgärd är de åtgärder som vidtas på ett e-postmeddelande på grund av befintliga principer eller identifieringar. Här är de möjliga åtgärder ett e-postmeddelande kan vidta:

    - **Levererad** – e-post levererades till en användares inkorg eller mapp och användaren kan komma åt den direkt.

    - **Skräppost** – e-post skickades till antingen användarens skräppostmapp eller borttagna mapp, och användaren har tillgång till e-postmeddelanden i mappen Skräppost eller Borttaget.

    - **Blockerad** – alla e-postmeddelanden som är i karantän, som misslyckades eller togs bort. (Detta är helt otillgängligt av användaren.)

    - **Ersatt** – alla e-postmeddelanden där skadliga bilagor ersätts av .txt-filer som anger att den bifogade filen var skadlig.
 
    Leveransplatsen visar resultatet av principer och identifieringar som körs efter leverans. Det är kopplat till en leveransåtgärd. Det här fältet har lagts till för att ge insikt i de åtgärder som vidtogs när ett problemmeddelande hittas. Här är möjliga värden för leveransplats:

    - **Inkorgen eller mappen** – E-postmeddelandet finns i inkorgen eller i en mapp (enligt dina e-postregler).

    - **On-prem eller extern** – Postlådan finns inte i molnet utan är lokal.

    - **Skräppostmapp** – E-postmeddelandet finns i en användares skräppostmapp.

    - **Mappen Borttaget objekt** – E-postmeddelandet finns i mappen Borttaget.

    - **Karantän** – E-postmeddelandet i karantän och inte i en användares postlåda.

    - **Misslyckades** – Det gick inte att nå postlådan via e-post.

    - **Tappade** - E-post försvinner någonstans i e-postflödet.

     ##### <a name="view-the-timeline-of-your-email"></a>Visa tidslinjen för din e-post
  
     **E-posttidslinje** är ett fält i Threat Explorer som gör det enklare för säkerhetsoperationsteamet att jaga. När flera händelser inträffar samtidigt eller i närheten av samma tid i ett e-postmeddelande visas dessa händelser i en tidslinjevy. Vissa händelser som inträffar efter leverans till e-post fångas in i kolumnen **Särskilda åtgärder.** Genom att kombinera information från tidslinjen för ett e-postmeddelande med eventuella särskilda åtgärder som vidtogs efter leveransen får administratörerna insikt i principer och hothantering (till exempel var posten dirigerades och, i vissa fall, vad den slutliga bedömningen var).

<!-- Reference material

1. **Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 

2. In the left navigation quick-launch, choose **Threat management** \> **Explorer**.

3. Click on the subject of an email message, and then click **Email timeline**. (It appears among other headings on the panel like **Summary** or **Details**.)

    Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail. In the case of no further events for the email, you should see a single event for the original delivery that states a result like **Blocked** with a verdict like **Phish**. The tab also has the option to export the entire email timeline, and this exports all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).

    The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived. When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view. 
    
    Some events that happen post-delivery to your mail are captured in the **Special actions** column. Combining the information from the email timeline along with special actions taken on email post-delivery gives admins insight into how their policies work, where the email was finally routed, and, in some cases, what the final assessment was. 

4. In the **View** menu, choose **All email**.

    ![Use the View menu to choose between Email and Content reports](../../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.

    ![Threat Explorer showing data for all email](../../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    (Depending on the actions that were taken on email messages for your organization, you might see other labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only email messages that ended up in users' inboxes.

    ![Clicking "Delivered to junk" removes that data from view](../../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.

    ![Below the chart, view a list of email messages that were detected](../../media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.

    ![You can view additional information about an item](../../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This deletes the selected messages from the recipients' mailboxes.

    ![When you select one or more email messages, you can choose from several available actions](../../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## Dealing with suspicious email messages

Malicious attackers might be sending mail to people in your organization in an attempt to phish their credentials and gain access to your corporate secrets. To help prevent this, you use the threat protection services in Office 365, including [Exchange Online Protection](exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md). However, it occasionally happens that an attacker sends email that contains a link (URL) that only later points to malicious content (such as malware). Or, you might realize too late that someone in your organization has been compromised, and while they were compromised, an attacker used their account to send email to other people in your organization. As part of dealing with either of these scenarios, you can remove suspicious email messages from user inboxes. To do that, you can use [Threat Explorer](threat-explorer.md).

## Finding re-routed email messages after actions are taken

Threat Explorer provides your security operations team with the details they need to investigate suspicious email. Your security operations team can:

- [View the email headers and download the email body](#view-the-email-headers-and-download-the-email-body) 

- [Check the delivery action and location](#check-the-delivery-action-and-location)

- [View the timeline of your email](#view-the-timeline-of-your-email)

### View the email headers and download the email body

The ability to preview email headers and download the body of an email body are powerful capabilities in Threat Explorer. Appropriate [permissions](permissions-in-the-security-and-compliance-center.md) must be assigned. See [Preview role permissions](#preview-role-permissions).

To access your message header and email download options, follow these steps: 

1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 
    
2. In the left navigation, choose **Threat management** \> **Explorer**.

3. Click on a subject in the Threat Explorer table. 

    This opens the flyout, where both header preview and email download links are positioned.

    ![Threat Explorer flyout with download and preview links on the page.](../../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> This capability doesn't show up for email messages that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed. In cases where email messages were deleted from users' mailboxes, admins see a "Mail not found" error message.
-->

## <a name="related-topics"></a>Relaterade ämnen

[Avancerat hotskydd i Office 365](office-365-ti.md)
  
[Skydda mot hot i Office 365](protect-against-threats.md)
  
[Visa rapporter för avancerat hotskydd för Office 365](view-reports-for-atp.md)
