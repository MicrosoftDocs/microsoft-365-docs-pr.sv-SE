---
title: Dokumentmetadatafält i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: I den här artikeln definieras metadatafälten för dokument i en granskning, i ett fall Advanced eDiscovery i Microsoft 365.
ms.openlocfilehash: 77df40f4922718a7ed30431b0c1bd91f5c075425
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244606"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Dokumentmetadatafält i Advanced eDiscovery

I följande tabell visas metadatafälten för dokument i en granskning, som i ett fall Advanced eDiscovery. Tabellen innehåller följande information:

- **Fältnamn** **och visningsfältnamn:** Namnet på metadatafältet och namnet på det fält som visas när du visar filmetadata för ett markerat dokument i en granskningsuppsättning. Vissa metadatafält tas inte med när du visar filens metadata i ett dokument. De här fälten är markerade med en asterisk (*).

- **Sökbart fältnamn:** Namnet på egenskapen som du kan söka efter när du kör en [granskningsuppsättningsfråga](review-set-search.md). En tom cell innebär att du inte kan söka efter fältet i en frågeuppsättning.

- **Namn på exporterat fält:** Namnet på det metadatafält som inkluderades när dokument exporteras.  En tom cell innebär att fältet inte ingår i de exporterade metadata.

- **Beskrivning:** En beskrivning av metadatafältet.

> [!NOTE]
> Fältet **Nyckelord** i en [granskningsuppsättningssökning](./review-set-search.md) använder Keyword Query Language (KQL). Fälten som visas i **kolumnen sökbara** fältnamn  kan användas i fältet Nyckelord i en granskningsuppsättningssökning för att skapa komplexa frågor utan att du behöver använda frågeverktyget. Mer information om KQL finns i [Syntaxreferens för nyckelordsfrågaspråk.](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

|**Fältnamn** och **visningsfältnamn**|**Sökbart fältnamn**|**Exporterat fältnamn**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|Innehålls-ID för bifogad fil|AttachmentContentId||Objektets innehålls-ID för bifogade filer.|
|Behörighetspoäng för juristklient|AttorneyClientPrivilegeScore||Innehållspoäng för behörighetsmodell för juristklienter.|
|Författare|Författare|Doc_authors|Författare från dokumentets metadata.|
|Hemlig kopia|Hemlig kopia|Email_bcc|Fältet Hemlig kopia för meddelandetyper. Formatet är **DisplayName \<SMTPAddress>**.|
|Kopia|Kopia|Email_cc|Fältet Kopia för meddelandetyper. Formatet är **DisplayName \<SMTPAddress>**.|
|Efterlevnadsetiketter|ComplianceLabels|Compliance_labels|[Bevarandeetiketter](retention.md) tillämpas på innehåll i Office 365.|
|Sammansatt sökväg|CompoundPath|Compound_path|Läsbar väg för en person som beskriver objektets källa.|
|Innehåll*|Content||Extraherad text för objektet.|
|Konversationstext|Konversationstext||Konversationstexten för objektet.|
|Konversationsämne|Konversationsämne||Konversationsämne för objektet.|
|Konversations-ID|ConversationId|Email_conversation_ID|Konversations-ID från meddelandet.|
|Konversationsindex||Conversation_index|Konversationsindex från meddelandet.|
|Pdf-tid för konversation|ConversationPdfTime||Datumet när PDF-versionen av konversationen skapades.|
|Samtal Redaction Burn Time|ConversationRedactionBurnTime||Datum då PDF-versionen av konversationen skapades för chatt.|
|||Converted_file_path|Sökvägen till den konverterade exportfilen. Endast för intern Microsoft-användning.|
|Dokumentdatum skapat|CreatedTime|Doc_date_created|Skapa datum från dokumentmetadata.|
|Insikare|Insikare|Insikare|Namnet på den insikare som objektet var associerat med.|
|Datum|Datum|Datum|Datum är ett beräknat fält som beror på filtypen.<br /><br />E-post: Skickat<br />E-postbilagor: Datum för senaste ändring av dokumentet;, om det inte är tillgängligt, förälderns skickat-datum<br />Inbäddade dokument: Datum för senaste ändring av dokumentet om den inte är tillgänglig: förälderns senaste ändring<br />SPO-dokument (innehåller moderna bifogade filer): SharePoint senaste ändring; dokument som senast ändrades, om de inte var tillgängliga<br />Icke-Office 365 dokument: Datum för senaste ändring<br />Möten: Startdatum för mötet<br />Röstbrevlåda: Skickat<br />Snabbmeddelande: Skickat|
|Andra sökvägar|Dedupedcompoundpath|Deduped_compound_path|Lista över sammansatta sökvägar för dokument som är exakta dubbletter (e-post: baserat på innehåll, dokument: baserat på hash-kod).|
|Andra snianer|DedupedCustodians|Deduped_custodians|Lista över dokument dokument som är exakta dubbletter (för e-post, baserat på innehåll, för dokument, baserat på hash-kod).|
|Andra fil-ID|DedupedFileIds|Deduped_file_IDs|Lista med fil-Ds med dokument som är exakta dubbletter (för e-post, baserat på innehåll, för dokument, baserat på hash- eller hash-kod).|
|Dokumentkommentarer|DocComments|Doc_comments|Kommentarer från dokumentets metadata.|
|Dokumentföretag||Doc_company|Företag från dokumentmetadata.|
|DocIndex*|||Indexet i familjen. **-1** eller **0** innebär att det är roten.|
|Dokumentnyckelord||Doc_keywords|Nyckelord från dokumentets metadata.|
|Dokument ändrat av||Doc_modified_by|Senast ändrad av från dokumentmetadata.|
|Dokumentändring|Doc_Version|Doc_Version|Revision från dokumentmetadata.|
|Dokumentets ämne||Doc_subject|Ämne från dokumentets metadata.|
|Dokumentmall||Doc_template|Mall från dokumentets metadata.|
|DocLastSavedBy||Doc_last_saved_by|Namnet på den användare som senast sparade dokumentet.|
|Dominant tema|DominantTheme|Dominant_theme|Dominant tema som beräknats för analys.|
|Duplicera delmängd||Duplicate_subset|Grupp-ID för exakta dubbletter.|
|EmailAction*||Email_action|Värdena är **Ingen,** **Svara** eller **Vidarebefordra**; baserat på ämnesraden i ett meddelande.|
|Begärt leveranskvitto för e-post||Email_delivery_receipt_requested|E-postadress som anges i Internethuvuden för leveranskvitto.|
|Prioritet|EmailImportance|Email_importance|Prioritet i meddelandet: **0** – Låg; **1** – Normal; **2** – Hög|
|EmailInternetHeaders|EmailInternetHeaders|Email_internet_headers|Alla e-posthuvuden från e-postmeddelandet|
|EmailLevel*||Email_level|Anger nivån för ett meddelande i e-posttråden som det tillhör. bifogade filer ärver det överordnade meddelandets värde.|
|Id för e-postmeddelande||Email_message_ID|Internetmeddelande-ID från meddelandet.|
|EmailReadReceiptRequested||Email_read_receipt_requested|E-postadress som anges i Internethuvuden för läskvitto.|
|E-postsäkerhet|EmailSecurity|Email_security|Säkerhetsinställning för meddelandet: **0** – Ingen; **1** – Signerat; **2** – Krypterad; **3** – Krypterad och signerad.|
|Känslighet för e-post|E-postkänslighet|email_sensitivity|Inställningen Känslighet för meddelandet: **0** – Ingen; **1** Personligt; **2** - Privat; **3** – CompanyConfidential.|
|E-postuppsättning|EmailSet|Email_set|Grupp-ID för alla meddelanden i samma e-postuppsättning.|
|EmailThread*||Email_thread|Placeringen av meddelandet i e-postuppsättningen; består av nod-ID från roten till det aktuella meddelandet och avgränsas med punkter (.).|
|||Export_native_path|Sökvägen till den exporterade filen.|
|Extraherad innehållstyp||Native_type|Extraherad innehållstyp, i form av mimetyp. till exempel **bild/jpeg**|
|||Extracted_text_path|Sökväg till den extraherade textfilen i exporten.|
|ExtractedTextLength*||Extracted_text_length|Antal tecken i den extraherade texten.|
|FamilyDuplicateSet*||Family_duplicate_set|Numerisk identifierare för familjer som är exakta dubbletter av varandra (samma innehåll och samma bifogade filer).|
|Familje-ID|FamilyId|Family_ID|Familje-ID grupperar alla objekt; för e-post, detta inkluderar meddelandet och alla bifogade filer; för dokument, till exempel dokumentet och eventuella inbäddade objekt.|
|Familjestorlek||Family_size|Antalet dokument i familjen.|
|Filklass|FileClass|File_class|För innehåll från SharePoint och OneDrive: **Dokument**; för innehåll från Exchange: **E-post** eller **Bifogad fil**.|
|Fil-ID|FileId|File_ID|Dokumentidentifierare som är unik i det aktuella ärendet.|
|Filsystemdatum skapat||File_system_date_created|Skapat datum från filsystem (gäller endast Office 365 data).|
|Systemdatum för fil som ändrats||File_system_date_modified|Ändrad datum från filsystem (gäller endast icke-Office 365 data).|
|Filtyp|FileType||Filtypen för objektet baserat på filnamnstillägget.|
|Grupp-ID|GroupID||Grupp-ID för grupperat innehåll.|
|Har bifogad fil|HasAttachment|Email_has_attachment|Anger om meddelandet har bifogade filer.|
|Har jurist|HasAttorney||**Sant** om minst en av deltagarna finns med i juristlistan. annars är värdet **Falskt.**|
|HasText*||Has_text|Anger om objektet innehåller text; möjliga värden är **Sant** och **Falskt.**|
|Oföränderligt ID||Immutable_ID|Det här ID:t används för att unikt identifiera ett dokument i en granskningsuppsättning. Det här fältet kan inte användas i en granskningsuppsättningssökning och ID:t kan inte användas för att komma åt ett dokument på dess ursprungliga plats.|
|Inkluderande typ|InclusiveType|Inclusive_type|Inkluderande typ som beräknas för **analys: 0** – inte inkluderande; **1** – inklusive; **2** – inklusive minus; **3 inklusive** kopia.|
|I Svara på ID||In_reply_to_ID|När du svarar på ID i meddelandet.|
|InputFileExtension||Original_file_extension|Det ursprungliga filtillägget för filen.|
|InputFileID||Input_file_ID|Fil-ID för objektet på översta nivån i granskningsuppsättningen. För bifogade filer är id:t ID:t för den överordnade filen. Det här kan användas för att gruppera familjer tillsammans.|
|Är modern bifogad fil| IsModernAttachment|  |Den här filen är en modern bifogad fil eller länkad fil.|
|Kommer från dokumentversion | IsFromDocumentVersion |  |Aktuellt dokument kommer från en annan version av ett annat dokument.|
|Bifogad fil i e-post | IsEmailAttachment|  |Det här objektet kommer från en e-postbilaga som visas som ett bifogat objekt i meddelandet.|
|Är bifogad fil i bifogad fil| IsInlineAttachment|  |Det här bifogades och visas i brödtexten i meddelandet.|
|Är representativ|IsRepresentative|Is_representative|Ett dokument i varje uppsättning med exakta dubbletter markeras som representativt.|
|Objektklass|ItemClass|Item_class|Objektklass som tillhandahålls av Exchange Server. till exempel **IPM. Obs!**|
|Datum för senaste ändring|LastModifiedDate|Doc_date_modified|Senast ändrad från dokumentmetadata.|
|Läs in ID|LoadId|Load_ID|ID för inläsningsuppsättningen där objektet lades till i en granskningsuppsättning.|
|Plats|Plats|Plats|Sträng som anger vilken typ av plats som dokumenten kommer från.<br /><br />**Importerade data** – icke-Office 365 data<br />**Teams** – Microsoft Teams<br />**Exchange** – Exchange postlådor<br />**SharePoint** – SharePoint webbplatser<br />**OneDrive** – OneDrive konton|
|Platsnamn|LocationName|Location_name|Sträng som identifierar objektets källa. För Exchange är det här postlådans SMTP-adress. för SharePoint webbplatssamlingens OneDrive, URL:en för webbplatssamlingen.|
|||Marked_as_pivot|Den här filen är pivot i en uppsättning med nästan dubbletter.|
|Markerat som representativt|MarkAsRepresentative||Ett dokument från varje uppsättning med exakta dubbletter markeras som representanter.|
|Slutdatum för möte|MeetingEndDate|Meeting_end_date|Mötets slutdatum för möten.|
|Startdatum för möte|MeetingStartDate|Meeting_start_date|Mötets startdatum för möten.|
|Meddelande sort|MessageKind|Message_kind|Den typ av meddelande du vill söka efter. Möjliga värden: kontakter dokument skicka e-post **<br /> <br /> <br /> <br /> externadata fax im journaler möten <br /> <br /> <br /> <br /> <br /> <br /> microsoftteams** (returnerar objekt från chattar, möten och samtal i Microsoft Teams) anteckningar inlägg **<br /> <br /> <br /> rssfeeds uppgifter <br /> <br /> röstbrevlåda**| 
|ModernAttachment_ParentId||ModernAttachment_ParentId||
|Ursprungligt filnamnstillägg|NativeExtension|Native_extension|Ursprungligt tillägg för objektet.|
|Eget filnamn|NativeFileName|Native_file_name|Det ursprungliga filnamnet för objektet.|
|NativeMD5||Native_MD5|MD5-hash (128-bitars hashvärde) för filströmmen.|
|NativeSHA256||Native_SHA_256|SHA256-hash (256-bitars hashvärde) för filströmmen.|
|ND/ET-sortering: Exklusive bifogade filer|NdEtSortExclAttach|ND_ET_sort_excl_attach|Sammanfogning av e-posttråduppsättningen (ET) och ND-uppsättningen (Near-duplicate). Det här fältet används för effektiv sortering vid granskning. En **D** föregås av ND-uppsättningar och **E** föregås av ET-uppsättningar.|
|ND/ET-sortering: Inklusive bifogade filer|NdEtSortInclAttach|ND_ET_sort_incl_attach|Sammanfogning av en e-posttråduppsättning (ET) och en nästan dubblettuppsättning (ND). Det här fältet används för effektiv sortering vid granskning. En **D** föregås av ND-uppsättningar och **E** föregås av ET-uppsättningar. Varje e-postobjekt i en ET-uppsättning följs av lämpliga bifogade filer.|
|O365-författare||O365_authors|Författare från SharePoint.|
|O365 som skapats av||O365_created_by|Skapad av SharePoint.|
|O365-datum skapat||O365_date_created|Skapat datum från SharePoint.|
|O365 ändrat datum||O365_date_modified|Senaste ändring från SharePoint.|
|O365 ändrat av||O365_modified_by|Ändrad av SharePoint.|
|Överordnat ID|ParentId|Container_ID|Id för objektets överordnade objekt.|
|ParentNode||Parent_node|Det e-postmeddelande som ligger närmast föregående i e-posttråden.|
|Deltagardomäner|ParticipantDomains|Email_participant_domains|Lista över alla domäner av ett meddelande.|
|Deltagare|Deltagare|Email_participants|Lista över alla deltagare i ett meddelande. till exempel Avsändare, Till, Kopia, Hemlig kopia.|
|Pivot-ID|Pivot-ID|Pivot_ID|ID för en pivot.|
|Potentiellt privilegierad|PotentielltPrivilegerat|Potentially_privileged|Sant om modellen för identifiering av juristklienter behandlar dokumentet som potentiellt privilegierat|
|Bearbetningsstatus|ProcessingStatus|Error_code|Bearbetningsstatus efter att objektet lades till i en granskningsuppsättning.|
|Läs percentiler|ReadPercentile||Läs percentilen för dokumentet baserat på relevans.|
|Mottaget|Mottaget|Email_date_received|Datum och tid då e-postmeddelandet togs emot i UTC.|
|Antal mottagare||Recipient_count|Antalet mottagare i meddelandet.|
|Mottagardomäner|RecipientDomains|Email_recipient_domains|Lista över alla mottagares domäner för ett meddelande.|
|Mottagare|Mottagare|Email_recipients|Lista över alla mottagare av ett meddelande (Till, Kopia, Hemlig kopia).|
|||Redacted_file_path|Sökvägen till den omdrekända ersättningsfilen i exporten.|
|||Redacted_text_path|Sökvägen till den omformaterade textfilen som ersätts i exporten. Endast för intern Microsoft-användning.|
|Problem med relevanstagg – ärende 1||Relevance_tag_case_issue_1|Problem med relevanstaggen Ärende 1 från Relevans.|
|Relevansresultat|RelevanceScore||Relevansresultat för ett dokument baserat på relevans.|
|Relevanstagg|Relevanstagg||Relevansresultat för ett dokument baserat på relevans.|
|Representativt ID|RepresentativeId||Numerisk identifierare för varje uppsättning med exakta dubbletter.|
|||Row_number|Radnumret för objektet i inläsningsfilen.|
|Avsändare|Avsändare|Email_sender|Fältet Sender (From) för meddelandetyper. Formatet är **DisplayName \<SmtpAddress>**.|
|Avsändare/författare|SenderAuthor||Beräknat fält som består av avsändaren eller författaren av objektet.|
|Avsändningsdomän|SenderDomain|Email_sender_domain|Domän för avsändaren.|
|Skickat|Skickat|Email_date_sent|Skickat-datum för meddelandet.|
|Ange ordning: Inklusive första|SetOrderInclusivesFirst|Set_order_inclusives_first|Fältet Sortering – e-post och bifogade filer: kronologiskt; dokument: pivotera först sedan i fallande likhetspoäng.|
|SimilarityPercent||Similarity_percent|Anger hur liknande ett dokument är med pivot för den nästan duplicerade uppsättningen.|
|Ursprunglig filstorlek|Storlek|Native_size|Antal byte av det ursprungliga objektet.|
|Ämne|Ämne|Email_subject|Meddelandets ämne.|
|Ämne/rubrik|SubjectTitle||Beräknat fält som består av objektets ämne eller rubrik.|
|Taggar|Taggar|Taggar|Taggar som används i en granskningsuppsättning.|
|Listan Teman|ThemesList|Themes_list|Lista över teman som beräknas för analys.|
|Title|Title|Doc_title|Rubrik från dokumentets metadata.|
|Till|Till|Email_to|Fältet Till för meddelandetyper. Format är **DisplayName \<SmtpAddress>**|
|Unik i e-postuppsättning|UniqueInEmailSet||**False** om det finns en dubblett av den bifogade filen i dess e-postuppsättning.|
|Åtgärdades|WasRemediated|Was_Remediated|**Sant** om objektet har åtgärdats, annars **falskt.**|
|Räkna ord|WordCount|Word_count|Antalet ord i objektet.|
|||||

> [!NOTE]
> Mer information om sökbara egenskaper vid sökning Office 365 på innehållsplatser när du samlar in data för ett Advanced eDiscovery-fall finns i Nyckelordsfrågor och sökvillkor för [innehållssökning](keyword-queries-and-search-conditions.md).