---
title: Söka i granskningsloggen för att felsöka vanliga scenarier
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du använder verktyget Microsoft 365 granskningsloggsökning för att felsöka vanliga supportproblem för e-postkonton.
ms.openlocfilehash: 5f753163b5d4d6c04c121a7ce3fae970690a57b0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161924"
---
# <a name="search-the-audit-log-to-investigate-common-support-issues"></a>Söka i granskningsloggen för att undersöka vanliga supportproblem

I den här artikeln beskrivs hur du använder sökverktyget i granskningsloggen för att undersöka vanliga supportproblem. Det omfattar att använda granskningsloggen för att:

- Hitta IP-adressen för datorn som används för att komma åt ett komprometterat konto
- Avgöra vem som kan konfigurera vidarebefordran av e-post för en postlåda
- Avgöra om en användare har tagit bort e-postobjekt i postlådan
- Avgöra om en användare har skapat en inkorgsregel
- Undersöka varför en användare utanför organisationen har loggat in på ett bra sätt
- Söka efter postlådeaktiviteter som utförs av användare med andra licenser än E5
- Söka efter postlådeaktiviteter som utförts av ombudsanvändare

## <a name="using-the-audit-log-search-tool"></a>Använda granskningsloggens sökverktyg

Alla felsökningsscenarier som beskrivs i den här artikeln baseras på användning av verktyget för granskningsloggsökning i Säkerhets- & efterlevnadscenter. Det här avsnittet innehåller de behörigheter som krävs för att söka i granskningsloggen och beskriver stegen för att komma åt och köra granskningsloggsökningar. Varje scenarioavsnitt förklarar hur du konfigurerar en granskningsloggsökningsfråga och vad du letar efter i den detaljerade informationen i granskningsposterna som matchar sökvillkoren.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Behörigheter som krävs för att använda verktyget för granskningsloggsökning

Du måste ha tilldelats rollen View-Only granskningsloggar eller granskningsloggar i Exchange Online kunna söka i granskningsloggen. Som standard tilldelas de här rollerna till rollgrupperna  Efterlevnadshantering och Organisationshantering på sidan Behörigheter Exchange administrationscentret. Globala administratörer i Office 365 och Microsoft 365 läggs automatiskt till som medlemmar i rollgruppen Organisationshantering i Exchange Online. Mer information finns i [Hantera rollgrupper i Exchange Online](/Exchange/permissions-exo/role-groups).

### <a name="running-audit-log-searches"></a>Köra granskningsloggsökningar

I det här avsnittet beskrivs grunderna för att skapa och köra granskningsloggsökningar. Använd de här instruktionerna som utgångspunkt för varje felsökningsscenario i den här artikeln. Mer detaljerade anvisningar finns i Söka [i granskningsloggen](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).

1. Gå till [https://protection.office.com/unifiedauditlog](https://protection.office.com/unifiedauditlog) och logga in med ditt arbets- eller skolkonto.
    
    Sidan **Granskningsloggsökning** visas. 
    
    ![Konfigurera villkor och välj sedan Sök för att köra sökningen](../media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. Du kan konfigurera följande sökvillkor. Varje felsökningsscenario i den här artikeln rekommenderar särskild vägledning för hur du konfigurerar dessa fält.
    
    a. **Aktiviteter:** Välj listrutan för att visa de aktiviteter som du kan söka efter. När du har kört sökningen visas bara granskningsposterna för de markerade aktiviteterna. Om **du markerar Visa resultat för alla** aktiviteter visas resultat för alla aktiviteter som uppfyller de andra sökvillkoren. Du måste också lämna fältet tomt i vissa felsökningsscenarier.
    
    b. **Startdatum och** **Slutdatum: Välj ett** datum- och tidsintervall för att visa händelser som inträffat inom den perioden. De senaste sju dagarna är valda som standard. Datum och tid presenteras i UTC-format (Coordinated Universal Time). Det maximala datumintervall du kan ange är 90 dagar.

    c. **Användare:** Klicka i den här rutan och välj sedan en eller flera användare som du vill visa sökresultat för. Granskningsposter för den valda aktiviteten som utförts av de användare du väljer i den här rutan visas i resultatlistan. Lämna rutan tom för att returnera poster för alla användare (och tjänstkonton) i organisationen.
    
    d. **Fil, mapp eller webbplats:** Skriv en del av eller hela fil- eller mappnamnet för att söka efter aktivitet relaterad till filen i mappen som innehåller det angivna nyckelordet. Du kan också ange URL-adressen till en fil eller mapp. Om du använder en URL-adress måste du se till att skriva den fullständiga URL-sökvägen eller, om du bara skriver en del av URL-adressen, inte innehåller några specialtecken eller blanksteg. Lämna rutan tom för att returnera poster för alla filer och mappar i organisationen. Det här fältet är tomt i alla felsökningsscenarier i den här artikeln.
    
5. Välj **Sök** för att köra sökningen med dina sökvillkor. 
    
    Sökresultaten läses in och efter en liten stund visas de under **Resultat på sidan** **Granskningsloggsökning.** I vart och ett av avsnitten i den här artikeln finns anvisningar om vad du ska leta efter i samband med det specifika felsökningsscenariot.

    Mer information om att visa, filtrera eller exportera resultat från granskningsloggsökning finns i:

    - [Visa sökresultat](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [Filtrera sökresultat](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [Exportera sökresultat](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="find-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Hitta IP-adressen för datorn som används för att komma åt ett komprometterat konto

IP-adressen som motsvarar en aktivitet som utförts av en användare ingår i de flesta granskningsposter. Information om klienten som används ingår också i granskningsposten.

Så här konfigurerar du en granskningsloggsökningsfråga för det här scenariot:

**Aktiviteter:** Välj en specifik aktivitet att söka efter, om det är relevant för ditt ärende. För felsökning av komprometterade konton kan du välja den användare som **loggat in i** postlådeaktiviteten under **Exchange postlådeaktiviteter**. Detta returnerar granskningsposter som visar DEN IP-adress som används när du loggade in på postlådan. Annars lämnar du det här fältet tomt för att returnera granskningsposter för alla aktiviteter. 

> [!TIP]
> Om du lämnar det här fältet tomt returneras **UserLoggedIn-aktiviteter,** vilket är en Azure Active Directory som anger att någon har loggat in på ett användarkonto. Använd filtrering i sökresultaten för att visa **UserLoggedIn-granskningsposterna.**

**Startdatum och** **slutdatum: Välj** ett datumintervall som är relevant för din undersökning.

**Användare:** Om du undersöker ett komprometterat konto väljer du den användare vars konto har komprometterats. Det här returnerar granskningsposter för aktiviteter som utförs av användarkontot.

**Fil, mapp eller webbplats:** Lämna fältet tomt.

När du har kört sökningen visas IP-adressen för varje aktivitet i **kolumnen IP-adress** i sökresultatet. Markera posten i sökresultatet om du vill visa mer detaljerad information på den utfällade sidan.

## <a name="determine-who-set-up-email-forwarding-for-a-mailbox"></a>Avgöra vem som kan konfigurera vidarebefordran av e-post för en postlåda

När vidarebefordran av e-post har konfigurerats för en postlåda vidarebefordras e-postmeddelanden som skickas till postlådan till en annan postlåda. Meddelanden kan vidarebefordras till användare i eller utanför organisationen. När vidarebefordran av e-post konfigureras för en postlåda är den underliggande Exchange Online-cmdleten som används **Set-Mailbox**.

Så här konfigurerar du en granskningsloggsökningsfråga för det här scenariot:

**Aktiviteter:** Lämna fältet tomt så att sökningen returnerar granskningsposter för alla aktiviteter. Det här är nödvändigt för att returnera alla granskningsposter som är relaterade till **cmdleten Set-Mailbox.**

**Startdatum och** **slutdatum: Välj** ett datumintervall som är relevant för din undersökning.

**Användare:** Lämna fältet tomt om du inte undersöker ett problem med vidarebefordran av e-post för en viss användare. På så sätt kan du se om vidarebefordran av e-post har ställts in för en användare.

**Fil, mapp eller webbplats:** Lämna fältet tomt.

När du har kört sökningen väljer **du Filtrera** resultat på sidan med sökresultat. I rutan under **kolumnrubriken** Aktivitet skriver du **Set-Mailbox** så att endast granskningsposter som är relaterade till cmdleten **Set-Mailbox** visas.

![Filtrera resultatet av en granskningsloggsökning](../media/emailforwarding1.png)

I det här läget måste du titta på informationen för varje granskningspost för att avgöra om aktiviteten är relaterad till vidarebefordran av e-post. Välj granskningsposten för att **visa den utfällade** sidan Information och välj sedan Mer **information**. I följande skärmbild och beskrivningar markeras den information som anger att vidarebefordran av e-post ställts in för postlådan.

![Detaljerad information från granskningsposten](../media/emailforwarding2.png)

a. I fältet **Objekt-ID** visas alias för postlådan som vidarebefordran av e-post var inställd på. Den här postlådan visas också **i kolumnen** Objekt på sökresultatsidan.

b. I fältet **Parametrar** anger värdet *ForwardingSmtpAddress att* vidarebefordran av e-post har angetts för postlådan. I det här exemplet vidarebefordras e-post till e-postadressen mike@contoso.com, som finns utanför alpinehouse.onmicrosoft.com organisation.

c. Värdet *True* för parametern *DeliverToMailboxAndForward* anger att en kopia av  meddelandet levereras till sarad@alpinehouse.onmicrosoft.com och vidarebefordras till den e-postadress som anges av parametern *ForwardingSmtpAddress,* som i det här exemplet är mike@contoso.com. Om värdet för parametern *DeliverToMailboxAndForward* är inställt på *Falskt* vidarebefordras bara e-post till den adress som anges av parametern *ForwardingSmtpAddress.* Det levereras inte till postlådan som anges i **fältet ObjectId.**

d. Fältet **UserId** anger användaren som ställer in vidarebefordran av e-post för postlådan som anges i **fältet Objekt-ID.** Den här användaren visas också i **kolumnen** Användare på sidan med sökresultat. I det här fallet verkar ägaren av postlådan ställa in vidarebefordran av e-post för sin postlåda.

Om du anser att vidarebefordran av e-post inte ska ställas in på postlådan kan du ta bort den genom att köra följande kommando i Exchange Online PowerShell:

```powershell
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Mer information om parametrar för vidarebefordran av e-post finns i [artikeln Set-Mailbox.](/powershell/module/exchange/set-mailbox)

## <a name="determine-if-a-user-deleted-email-items"></a>Avgöra om en användare har tagit bort e-postobjekt

Från och med januari 2019 startar Microsoft granskningsloggning för postlådor som standard för alla Office 365 och Microsoft-organisationer. Det innebär att vissa åtgärder som utförs av postlådeägare loggas automatiskt och motsvarande granskningsposter för postlådor är tillgängliga när du söker efter dem i granskningsloggen för postlådan. Innan postlådegranskning var aktiverat som standard var du tvungen att manuellt aktivera den för alla användarpostlådor i organisationen. 

De postlådeåtgärder som loggas som standard omfattar åtgärderna MjukDelete och HardDelete-postlåda som utförs av postlådeägare. Det innebär att du kan använda följande steg för att söka i granskningsloggen efter händelser relaterade till borttagna e-postobjekt. Mer information om postlådegranskning som standard finns i [Hantera granskning av postlådor.](enable-mailbox-auditing.md)

Så här konfigurerar du en granskningsloggsökningsfråga för det här scenariot:

**Aktiviteter:** Under **Exchange postlådeaktiviteter** väljer du en eller båda av följande aktiviteter:

- **Meddelanden som tagits bort från mappen Borttaget:** Den här aktiviteten motsvarar **postlådegranskningsåtgärden SoftDelete.** Den här aktiviteten loggas också när en användare tar bort ett objekt permanent genom att markera det och trycka på **Skift+Delete.** När ett objekt har tagits bort permanent kan användaren återställa det tills bevarandetiden för borttagna objekt löper ut.

- **Meddelanden har rensats från postlådan:** Den här aktiviteten motsvarar **granskningsåtgärden HardDelete-postlåda.** Detta loggas när en användare rensar ett objekt från mappen Återställningsbara objekt. Administratörer kan använda verktyget Innehållssökning i säkerhets- och efterlevnadscentret för att söka efter och återställa borttagna objekt tills bevarandeperioden för borttagna objekt löper ut eller längre om användarens postlåda är undantaget.

**Startdatum och** **slutdatum: Välj** ett datumintervall som är relevant för din undersökning.

**Användare:** Om du väljer en användare i det här fältet returnerar verktyget för granskningsloggsökning granskningsposter för e-postobjekt som har tagits bort (SoftDeleted eller HardDeleted) av den användare du anger. Ibland är inte användaren som tar bort ett e-postmeddelande postlådans ägare.

**Fil, mapp eller webbplats:** Lämna fältet tomt.

När du har kört sökningen kan du filtrera sökresultatet och visa granskningsposterna för mjukt borttagna objekt eller för permanent borttagna objekt. Välj granskningsposten för att **visa den utfällade** sidan Information och välj sedan Mer **information**. Mer information om det borttagna objektet, till exempel ämnesraden och platsen för objektet när det togs bort, visas i **fältet AffectedItems.** Följande skärmbilder visar ett exempel på fältet **AffectedItems** från ett mjukt borttagna objekt och ett hård borttagna objekt.

**Exempel på fältet AffectedItems för mjukt borttagna objekt**

![Granskningspost för mjukt borttagna objekt](../media/softdeleteditem.png)

**Exempel på fältet AffectedItems för permanent borttagna objekt**

![Granskningspost för permanent borttagna e-postobjekt](../media/harddeleteditem.png)

### <a name="recover-deleted-email-items"></a>Återskapa borttagna e-postobjekt

Användare kan återställa mjukt borttagna objekt om bevarandeperioden för borttagna objekt inte har gått ut. I Exchange Online är standardlagringstiden för borttagna objekt 14 dagar, men administratörer kan öka den här inställningen till högst 30 dagar. Peka på artikeln [Återskapa borttagna objekt eller e-Outlook](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) i webbartikeln om du vill ha anvisningar för hur du återställer borttagna objekt.

Som tidigare förklarats kan administratörer eventuellt återställa permanent borttagna objekt om bevarandeperioden för borttagna objekt inte har gått ut eller om postlådan är undantaget. I sådana fall bevaras objekt tills bevarandetiden går ut. När du kör en innehållssökning returneras mjuka borttagna och permanent borttagna objekt i mappen Återställningsbara objekt i sökresultatet om de matchar sökfrågan. Mer information om hur du kör innehållssökningar finns i [Innehållssökning i Office 365](content-search.md).

> [!TIP]
> Om du vill söka efter borttagna e-postobjekt söker du efter hela eller en del av ämnesraden som visas i fältet **AffectedItems** i granskningsposten.

## <a name="determine-if-a-user-created-an-inbox-rule"></a>Avgöra om en användare har skapat en inkorgsregel

När användare skapar en inkorgsregel för Exchange Online postlåda sparas en motsvarande granskningspost i granskningsloggen. Mer information om inkorgsregler finns i:

- [Använda inkorgsregler i Outlook på webben](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Hantera e-postmeddelanden i Outlook med hjälp av regler](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

Så här konfigurerar du en granskningsloggsökningsfråga för det här scenariot:

**Aktiviteter:** Under **Exchange postlådeaktiviteter** väljer du **Ny inkorgRegel Skapa/ändra/aktivera/inaktivera inkorgsregel.**

**Startdatum och** **slutdatum: Välj** ett datumintervall som är relevant för din undersökning.

**Användare:** Lämna fältet tomt om du inte undersöker en specifik användare. På så sätt kan du identifiera nya inkorgsregler som har ställts in av alla användare.

**Fil, mapp eller webbplats:** Lämna fältet tomt.

När du har kört sökningen visas granskningsposter för den här aktiviteten i sökresultaten. Välj en granskningspost för att **visa den utfällna** sidan Information och välj sedan Mer **information**. Information om inställningarna för inkorgsregel visas i **fältet** Parametrar. I följande skärmbild och beskrivningar markeras informationen om inkorgsregler.

![Granskningspost för ny inkorgsregel](../media/NewInboxRuleRecord.png)

a. I **fältet Objekt-ID** visas det fullständiga namnet på inkorgsregeln. Det här namnet innehåller alias för användarens postlåda (till exempel SaraD) och namnet på inkorgsregeln (till exempel "Flytta meddelanden från administratör").

b. Villkoret **för** inkorgsregeln visas i fältet Parametrar. I det här exemplet anges villkoret av *parametern Från.* Värdet som har definierats för *parametern* Från anger att inkorgsregeln agerar på e-post som admin@alpinehouse.onmicrosoft.com. En fullständig lista över parametrar som kan användas för att definiera villkor för inkorgsregler finns i artikeln Regel [för Ny-Inkorg.](/powershell/module/exchange/new-inboxrule)

c. Parametern *MoveToFolder* anger åtgärden för inkorgsregeln. I det här exemplet flyttas meddelanden som admin@alpinehouse.onmicrosoft.com från mappen *AdminSearch.* I artikeln [Ny inkorg Finns även](/powershell/module/exchange/new-inboxrule) en fullständig lista över parametrar som kan användas för att definiera en inkorgsregels åtgärd.

d. Fältet **UserId** anger användaren som skapade inkorgsregeln som anges i **fältet Objekt-ID.** Den här användaren visas också i **kolumnen** Användare på sidan med sökresultat.

## <a name="investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization"></a>Undersöka varför en användare utanför organisationen har loggat in på ett bra sätt

När du granskar granskningsposter i granskningsloggen kan det hända att du ser poster som anger att en extern användare autentiserades av Azure Active Directory och har loggats in i organisationen. En administratör i contoso.onmicrosoft.com kan till exempel se en granskningspost som visar att en användare från en annan organisation (till exempel fabrikam.onmicrosoft.com) har loggat in på contoso.onmicrosoft.com. På samma sätt kan du se granskningsposter som anger att användare med ett Microsoft-konto (MSA), till exempel Outlook.com eller Live.com, har loggat in i organisationen. I dessa situationer är den granskade aktiviteten **Användare inloggad.** 

Detta är avsiktligt. Azure Active Directory (Azure AD), katalogtjänsten, tillåter något som kallas direktautentisering när en extern användare försöker komma åt en *SharePoint-webbplats* eller en OneDrive-plats i organisationen. När den externa användaren försöker göra detta uppmanas de att ange sina autentiseringsuppgifter. Azure AD använder autentiseringsuppgifterna för att autentisera användaren, vilket innebär att endast Azure AD verifierar att användaren är som han eller hon utger sig för att vara. Indikation på att inloggningen i granskningsposten är resultatet av azure AD-autentisering av användaren. En lyckad inloggning innebär inte att användaren har kunnat komma åt några resurser eller utföra andra åtgärder i organisationen. Den anger bara att användaren autentiserats av Azure AD. För att en direktanvändare ska få åtkomst till SharePoint- eller OneDrive-resurser måste en användare i organisationen uttryckligen dela en resurs med den externa användaren genom att skicka en delningsinbjudan eller en anonym delningslänk till dem. 

> [!NOTE]
> Azure AD tillåter direktautentisering endast *för program från första* part, till exempel SharePoint Online och OneDrive för företag. Det är inte tillåtet för andra program från tredje part.

Här är ett exempel och beskrivningar av relevanta egenskaper i en granskningspost för en användare som loggats **in** om det är ett resultat av direktautentisering. Välj granskningsposten för att **visa den utfällade** sidan Information och välj sedan Mer **information**.

![Exempel på granskningspost för lyckade pass-thru-autentisering](../media/PassThroughAuth1.png)

   a. Det här fältet anger att användaren som försökte komma åt en resurs i organisationen inte hittades i organisationens Azure AD.

   b. I det här fältet visas UPN för den externa användare som försökte komma åt en resurs i organisationen. Det här användar-ID:t identifieras också **i användar-** **och userid-egenskaperna** i granskningsposten.

   c. Egenskapen **ApplicationId** identifierar programmet som utlöste inloggningsbegäran. Värdet på 00000003-0000-0ff1-ce00-00000000000 som visas i ApplicationId-egenskapen i den här granskningsposten anger SharePoint Online. OneDrive för företag har samma ApplicationId.

   d. Det här indikerar att direktautentisering lyckades. Med andra ord kunde användaren autentiseras av Azure AD. 

   e. **RecordType-värdet** **för 15** anger att den granskade aktiviteten (UserLoggedIn) är en STS-inloggningshändelse (Secure Token Service) i Azure AD.

Mer information om andra egenskaper som visas i en UserLoggedIn-granskningspost finns i Azure AD-relaterad schemainformation i Office 365 API-schema för [hanteringsaktivitet.](/office/office-365-management-api/office-365-management-activity-api-schema#azure-active-directory-base-schema)

Här är två exempelscenarier som skulle resultera i en framgångsrik användare som **loggats i** granskningsaktivitet på grund av direktautentisering: 

  - En användare med ett Microsoft-konto (till exempel SaraD@outlook.com) har försökt komma åt ett dokument i ett OneDrive för företag-konto i fourthcoffee.onmicrosoft.com och det finns inte något motsvarande gästanvändarkonto för SaraD@outlook.com i fourthcoffee.onmicrosoft.com.

  - En användare med ett arbets- eller skolkonto i en organisation (till exempel pilarp@fabrikam.onmicrosoft.com) har försökt komma åt en SharePoint-webbplats i contoso.onmicrosoft.com och det finns inte något motsvarande gästanvändarkonto för pilarp@fabrikam.com i contoso.onmicrosoft.com.

### <a name="tips-for-investigating-successful-logins-resulting-from-pass-through-authentication"></a>Tips att undersöka lyckade inloggningar som härrör från direktautentisering

- Sök i granskningsloggen efter aktiviteter som utförts av den externa användaren som identifierats i **den användare som loggade in** granskningsposten. Skriv UPN för den externa användaren i rutan Användare **och** använd ett datumintervall om det är relevant för ditt scenario. Du kan till exempel skapa en sökning med hjälp av följande sökvillkor:

   ![Söka efter alla aktiviteter som utförts av den externa användaren](../media/PassThroughAuth2.png)

    Utöver de  användarloggade aktiviteterna kan andra granskningsposter returneras, sådana som anger att en användare i organisationen delade resurser med den externa användaren och om den externa användaren kom åt, ändrade eller hämtade ett dokument som delades med dem.

- Sök efter SharePoint delade aktiviteter som anger att en fil delades med den externa användare som identifieras av en användare **som loggade in i** granskningsposten. Mer information finns i Använda [delningsgranskning i granskningsloggen](use-sharing-auditing.md).

- Exportera granskningsloggens sökresultat som innehåller poster som är relevanta för din undersökning så att du kan Excel söka efter andra aktiviteter som är relaterade till den externa användaren. Mer information finns i [Exportera, konfigurera och visa granskningsloggposter.](export-view-audit-log-records.md)

## <a name="search-for-mailbox-activities-performed-by-users-with-non-e5-licenses"></a>Söka efter postlådeaktiviteter som utförs av användare med andra licenser än E5

Även [när](enable-mailbox-auditing.md) postlådegranskning är aktiverat som standard för organisationen kanske du märker att granskningshändelser för postlådor för vissa användare inte hittas i granskningsloggsökningar med hjälp av efterlevnadscentret, cmdleten **Search-UnifiedAuditLog eller API:t** för Office 365-hanteringsaktivitet. Anledningen är att granskningshändelser för postlådor bara returneras för användare med E5-licenser när du använder någon av de tidigare metoderna för att söka i den enhetliga granskningsloggen.

Om du vill hämta granskningsloggposter för postlådor för andra användare än E5 kan du utföra någon av följande lösningar:

- Aktivera postlådegranskning manuellt för enskilda postlådor (kör `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` kommandot i Exchange Online PowerShell). När du har gjort det kan du söka efter granskningsaktiviteter för postlådor med hjälp av efterlevnadscentret, **cmdlet:en Search-UnifiedAuditLog eller API:t** för Office 365 Management Activity.
  
  > [!NOTE]
  > Om postlådegranskning redan verkar vara aktiverad för postlådan, men sökningarna inte returnerar några resultat, så kan du ändra värdet för parametern _AuditEnabled_ till och `$false` sedan tillbaka till `$true` .
  
- Använd följande cmdlets i Exchange Online PowerShell:

  - [Search-MailboxAuditLog för](/powershell/module/exchange/search-mailboxauditlog) att söka i granskningsloggen för postlådor för specifika användare.

  - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) för att söka i granskningsloggen för postlådor för specifika användare och få resultatet skickat via e-post till vissa mottagare.

## <a name="search-for-mailbox-activities-performed-in-a-specific-mailbox-including-shared-mailboxes"></a>Sök efter postlådeaktiviteter som utförs i en viss postlåda (inklusive delade postlådor)

När du  använder listrutan Användare i verktyget för granskningsloggsökning i efterlevnadscentret eller kommandot **Search-UnifiedAuditLog -UserIds** i Exchange Online PowerShell kan du söka efter aktiviteter som utförs av en viss användare. För granskningsaktiviteter för postlådor söker den här typen av sökning efter aktiviteter som utförts av den angivna användaren. Det garanterar inte att alla aktiviteter som utförs i samma postlåda returneras i sökresultatet. En granskningsloggsökning returnerar till exempel inte granskningsposter för aktiviteter som utförts av en ombudsanvändare eftersom en sökning efter postlådeaktiviteter som utförts av en viss användare inte returnerar aktiviteter som utförts av en ombudsanvändare som har tilldelats behörighet till en annan användares postlåda. (En ombudsanvändare är någon som har tilldelats postlådebehörigheten SendAs, SendOnBehalf eller FullAccess till en annan användares postlåda.)

Om du  använder listrutan för användare i verktyget för granskningsloggsökning eller **Search-UnifiedAuditLog -UserIds returneras** inte heller resultat för aktiviteter som utförts i en delad postlåda.

Om du vill söka efter aktiviteter som utförs i en viss postlåda eller söka efter aktiviteter som utförs i en delad postlåda använder du följande syntax när du kör cmdleten **Search-UnifiedAuditLog:**

```powershell
Search-UnifiedAuditLog  -StartDate <date> -EndDate <date> -FreeText (Get-Mailbox <mailbox identity).ExchangeGuid
```

Följande kommando returnerar till exempel granskningsposter för aktiviteter som utförts i den delade postlådan i Contoso-efterlevnadsteamet mellan augusti 2020 och oktober 2020:

```powershell
Search-UnifiedAuditLog  -StartDate 08/01/2020 -EndDate 10/31/2020 -FreeText (Get-Mailbox complianceteam@contoso.onmicrosoft.com).ExchangeGuid
```

Alternativt kan du använda cmdleten **Search-MailboxAuditLog** för att söka efter granskningsposter för aktivitet som utförs i en viss postlåda. Det omfattar även sökning efter aktiviteter som utförs i en delad postlåda.

Följande exempel returnerar granskningsloggposter för postlådor för aktiviteter som utförts i den delade postlådan i Contoso-efterlevnadsteamet:

```powershell
Search-MailboxAuditLog -Identity complianceteam@contoso.onmicrosoft.com -StartDate 08/01/2020 -EndDate 10/31/2020 -ShowDetails
```

Följande exempel returnerar granskningsloggposter för postlådor för aktiviteter som utförts i den angivna postlådan av ombudsanvändare:

```powershell
Search-MailboxAuditLog -Identity <mailbox identity> -StartDate <date> -EndDate <date> -LogonTypes Delegate -ShowDetails
```

Du kan också använda cmdleten **New-MailboxAuditLogSearch** för att söka i granskningsloggen efter en viss postlåda och få resultatet skickat via e-post till angivna mottagare.