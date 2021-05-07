---
title: Kom igång med kommunikationsefterlevnad
description: Konfigurera principer för kommunikationsefterlevnad för att konfigurera användarkommunikation för granskning.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 3e84c3266dd802fb6cab12db0c20773838b4e2a9
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52162829"
---
# <a name="get-started-with-communication-compliance"></a>Kom igång med kommunikationsefterlevnad

Använd principer för kommunikationsefterlevnad för att identifiera användarkommunikation för granskning av interna eller externa granskare. Mer information om hur principer för kommunikationsefterlevnad kan hjälpa dig att övervaka kommunikationen i organisationen finns i principer för [kommunikationsefterlevnad i Microsoft 365.](communication-compliance.md) Om du vill granska hur Contoso snabbt konfigurerade en policy för kommunikationsefterlevnad för att övervaka anstötliga språk i Microsoft Teams, Exchange Online och Yammer kommunikation kan du ta en titta på denna [fallstudie.](communication-compliance-case-study.md)

## <a name="subscriptions-and-licensing"></a>Prenumerationer och licensiering

Innan du börjar med kommunikationsefterlevnad bör du bekräfta [Microsoft 365 prenumerationen](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) och eventuella tillägg. För att komma åt och använda kommunikationsefterlevnad måste din organisation ha någon av följande prenumerationer eller tillägg:

- Microsoft 365 E5 prenumeration (betald version eller utvärderingsversion)
- Microsoft 365 E3-prenumeration + Microsoft 365 E5 Compliance-tillägget
- Microsoft 365 E3 -prenumerationen + Microsoft 365 E5-tillägget Insider Risk Management
- Microsoft 365 A5-prenumeration (betald eller utvärderingsversion)
- Microsoft 365 A3-prenumeration + Microsoft 365 A5-tillägget efterlevnad
- Microsoft 365 En 3-prenumeration + Microsoft 365 A5 Insider Risk Management-tillägget
- Microsoft 365 G5-prenumeration (betald eller utvärderingsversion)
- Microsoft 365 G5-prenumeration + Microsoft 365 G5-tillägget för efterlevnad
- Microsoft 365 G5-prenumeration + Microsoft 365 G5 Insider Risk Management-tillägget
- Office 365 Enterprise E5-prenumeration (betald eller utvärderingsversion)
- Office 365 A5 prenumeration (betald version eller utvärderingsversion)
- Office 365 Enterprise E3-prenumeration + Office 365 Advanced Compliance-tillägget (inte längre tillgängligt för nya prenumerationer, se anteckningen)

Användare som ingår i principer för kommunikationsefterlevnad måste tilldelas en av licenserna ovan.

>[!IMPORTANT]
>Office 365 Advanced Compliance säljs inte längre som en fristående prenumeration. När aktuella prenumerationer går ut bör kunderna gå över till en av prenumerationerna ovan, som innehåller samma eller ytterligare efterlevnadsfunktioner.

Om du inte har ett befintligt Office 365 Enterprise E5-abonnemang och vill prova kommunikationsefterlevnad kan du [](https://www.microsoft.com/microsoft-365/enterprise) lägga till [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) i din befintliga prenumeration eller registrera dig för en utvärderingsversion av Office 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Steg 1 (obligatoriskt): Aktivera behörigheter för kommunikationsefterlevnad

>[!Important]
>Som standard har globala administratörer inte tillgång till funktioner för kommunikationsefterlevnad. Rollerna som tilldelats i det här steget krävs för att alla funktioner för kommunikationsefterlevnad ska vara tillgängliga. När du har konfigurerat rollgrupperna kan det ta upp till 30 minuter för rollgruppsbehörigheterna att gälla för tilldelade användare i organisationen.

Det finns fem rollgrupper som används för att konfigurera behörigheter för att hantera funktioner för kommunikationsefterlevnad. För att göra **kommunikationsefterlevnad** tillgängligt som ett menyalternativ i Microsoft 365 efterlevnadscenter och för  att fortsätta med de här konfigurationsstegen måste du tilldelas rollgrupperna Administratör för kommunikationsefterlevnad *eller* kommunikationsefterlevnad. För att komma åt och hantera funktioner för kommunikationsefterlevnad efter den första konfigurationen måste användare vara medlemmar i minst en rollgrupp för kommunikationsefterlevnad.

Beroende på hur du vill hantera kommunikationsprinciper och aviseringar måste du tilldela användare till specifika rollgrupper. Du kan tilldela användare med olika efterlevnadsansvar till specifika rollgrupper för att hantera olika områden av funktioner för kommunikationsefterlevnad. Eller så kanske du bestämmer dig för att tilldela alla användarkonton till administratörer, analytiker, slutanvändare och läsare till rollgruppen *för* kommunikationsefterlevnad. Använd en rollgrupp eller flera rollgrupper som bäst passar kraven på efterlevnadshantering.

Välj bland de här rollgruppsalternativen när du konfigurerar kommunikationsefterlevnad:

| Roll | Rollbehörigheter |
|:-----|:-----|
| **Kommunikationsefterlevnad** | Använd den här rollgruppen för att hantera kommunikationsefterlevnad för organisationen i en enda grupp. Genom att lägga till alla användarkonton för angivna administratörer, analytiker, slutanvändare och läsare kan du konfigurera behörigheter för kommunikationsefterlevnad i en enda grupp. Den här rollgruppen innehåller alla behörighetsroller för kommunikationsefterlevnad. Den här konfigurationen är det enklaste sättet att snabbt komma igång med kommunikationsefterlevnad och är en god passform för organisationer som inte behöver separata behörigheter som definierats för olika användargrupper. |
| **Admin för kommunikationsefterlevnad** | Använd den här rollgruppen till att först konfigurera kommunikationsefterlevnad och senare för att avgränsa administratörer för kommunikationsefterlevnad i en definierad grupp. Användare som tilldelats den här rollgruppen kan skapa, läsa, uppdatera och ta bort principer för kommunikationsefterlevnad, globala inställningar och tilldelningar av rollgrupper. Användare som tilldelats den här rollgruppen kan inte visa meddelandeaviseringar. |
| **Analytiker för kommunikationsefterlevnad** | Använd den här gruppen för att tilldela behörigheter till användare som fungerar som kommunikationsefterlevnadsanalytiker. Användare som har tilldelats den här rollgruppen kan visa principer där de har tilldelats som granskare, visa metadata för meddelanden (inte meddelandeinnehåll), eskalera till ytterligare granskare eller skicka meddelanden till användare. Analytiker kan inte lösa väntande aviseringar. |
| **Communication Compliance Investigator** | Använd den här gruppen för att tilldela behörigheter till användare som ska agera som kommunikationsefterlevnad. Användare som har tilldelats den här rollgruppen kan visa metadata och innehåll för meddelanden, eskalera till ytterligare granskare, eskalera till ett Advanced eDiscovery-ärende, skicka meddelanden till användare och lösa aviseringen. |
| **Visningsprogram för kommunikationsefterlevnad** | Använd den här gruppen för att tilldela behörigheter till användare som hanterar kommunikationsrapporter. Användare som har tilldelats den här rollgruppen har åtkomst till alla rapportwidgetar på kommunikationsefterlevnadens startsida och kan visa alla rapporter om kommunikationsefterlevnad. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Alternativ 1: Tilldela alla efterlevnadsanvändare till rollgruppen för kommunikationsefterlevnad

1. Logga in [https://protection.office.com/permissions](https://protection.office.com/permissions) med autentiseringsuppgifter för ett administratörskonto i Microsoft 365 organisation.

2. I &amp; Säkerhetsefterlevnadscenter går du till **Behörigheter.** Välj länken för att visa och hantera roller i Office 365.

3. Markera *rollgruppen Kommunikationsefterlevnad* och välj sedan **Redigera rollgrupp**.

4. Välj **Välj medlemmar** i det vänstra navigeringsfönstret och välj sedan **Redigera**.

5. Välj **Lägg** till och markera sedan kryssrutan för alla användare som du vill lägga till i *rollgruppen för* kommunikationsefterlevnad.

6. Välj **Lägg** till och välj sedan **Klar**.

7. Välj **Spara** för att lägga till användare i rollgruppen. Välj **Stäng** för att slutföra stegen

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Alternativ 2: Tilldela användare specifika rollgrupper för kommunikationsefterlevnad

Använd det här alternativet om du vill tilldela användare specifika rollgrupper för segmenterad åtkomst och ansvar för kommunikationsefterlevnad mellan olika användare i organisationen.

1. Logga in [https://protection.office.com/permissions](https://protection.office.com/permissions) med autentiseringsuppgifter för ett administratörskonto i Microsoft 365 organisation.

2. I &amp; Säkerhetsefterlevnadscenter går du till **Behörigheter.** Välj länken för att visa och hantera roller i Office 365.

3. Välj en av rollgrupperna för kommunikationsefterlevnad och välj **sedan Redigera rollgrupp**.

4. Välj **Välj medlemmar** i det vänstra navigeringsfönstret och välj sedan **Redigera**.

5. Välj **Lägg** till och markera sedan kryssrutan för alla användare som du vill lägga till i rollgruppen.

6. Välj **Lägg** till och välj sedan **Klar**.

7. Välj **Spara** för att lägga till användare i rollgruppen.

8. Välj nästa rollgrupp för kommunikationsefterlevnad och upprepa steg 4–7 för varje obligatorisk rollgrupp.

9. Välj **Stäng** för att slutföra stegen.

Mer information om rollgrupper och behörigheter finns i [Behörigheter i Efterlevnadscenter.](../security/office-365-security/protect-against-threats.md)

## <a name="step-2-required-enable-the-audit-log"></a>Steg 2 (obligatoriskt): Aktivera granskningsloggen

För kommunikationsefterlevnad krävs granskningsloggar för att visa aviseringar och spåra åtgärder som granskarna har vidtagit. Granskningsloggarna är en sammanfattning av alla aktiviteter som är associerade med en definierad organisationspolicy eller när en princip för kommunikation är efterlevnadspolicyn ändras.

Stegvisa instruktioner för hur du aktiverar granskning finns i [Aktivera eller inaktivera granskningsloggsökning.](turn-audit-log-search-on-or-off.md) När du aktiverar granskningen visas ett meddelande om att granskningsloggen förbereds och att du kan köra en sökning om några timmar efter att förberedelserna har slutförts. Du behöver bara göra den här åtgärden en gång. Mer information om hur du använder granskningsloggen finns i [Söka i granskningsloggen](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Steg 3 (valfritt): Konfigurera grupper för kommunikationsefterlevnad

 När du skapar en princip för kommunikationsefterlevnad definierar du vilka som får sin kommunikation granskad och vem som utför granskningar. I principen använder du e-postadresser för att identifiera personer eller grupper av personer. För att förenkla konfigurationen kan du skapa grupper för personer som får sin kommunikation granskad och grupper för personer som granskar dessa meddelanden. Om du använder grupper kan du behöva flera. Till exempel om du vill övervaka kommunikationen mellan två distinkta grupper av personer eller om du vill ange en grupp som inte kommer att övervakas.

Använd följande diagram för att hjälpa dig att konfigurera grupper i organisationen för principer för kommunikationsefterlevnad:

| **Principmedlem** | **Grupper som stöds** | **Grupper som inte stöds** |
|:-----|:-----|:-----|
|Övervakade användare <br> Ej övervakade användare | Distributionsgrupper <br> Microsoft 365-grupper | Dynamiska distributionsgrupper <br> Kapslade distributionsgrupper <br> E-postaktiverad säkerhetsgrupp <br> Microsoft 365 grupper med dynamiskt medlemskap |
| Granskare | Ingen | Distributionsgrupper <br> Dynamiska distributionsgrupper <br> Kapslade distributionsgrupper <br> E-postaktiverad säkerhetsgrupp |
  
När du tilldelar en distributionsgrupp i principen övervakar principen alla e-postmeddelanden Teams och chattar från varje användare i distributionsgruppen. När du tilldelar en Microsoft 365-grupp i principen övervakar principen alla e-postmeddelanden och Teams-chattar som skickas till den gruppen, inte de enskilda e-postmeddelanden och chattar som tas emot av varje gruppmedlem.

Om du är en organisation med en lokal distribution av Exchange eller en extern e-postleverantör och du vill övervaka Microsoft Teams-chattar för användarna måste du skapa en distributionsgrupp som ska övervakas av användare med lokala eller externa postlådor. Senare i de här stegen tilldelar du den här distributionsgruppen som val **av övervakade användare** och grupper i principguiden.

Om du vill hantera övervakade användare i stora företag kan du behöva övervaka alla användare i stora grupper. Du kan använda PowerShell till att konfigurera en distributionsgrupp för en global princip för kommunikationsefterlevnad för den tilldelade gruppen. På så sätt kan du övervaka tusentals användare med en enda princip och hålla principen för kommunikationsefterlevnad uppdaterad när nya anställda ansluter till organisationen.

1. Skapa en dedikerad distributionsgrupp för din globala kommunikationsefterlevnadsprincip med följande egenskaper: Kontrollera att den här [distributionsgruppen](/powershell/module/exchange/new-distributiongroup) inte används för andra ändamål eller andra Office 365 tjänster.

    - **MemberDepartRestriction = Closed**. Säkerställer att användarna inte kan ta bort sig själva från distributionsgruppen.
    - **MemberJoinRestriction = Closed**. Säkerställer att användarna inte kan lägga till sig själva i distributionsgruppen.
    - **ModerationEnabled = True**. Säkerställer att alla meddelanden som skickas till den här gruppen måste godkännas och att gruppen inte används för att kommunicera utanför konfigurationen av policyn för kommunikationsefterlevnad.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Välj ett anpassat [Exchange som inte används för](/Exchange/recipients/mailbox-custom-attributes) att spåra användare som lagts till i organisationens princip för kommunikationsefterlevnad.

3. Kör följande PowerShell-skript på ett återkommande schema för att lägga till användare i principen för kommunikationsefterlevnad:

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

Mer information om hur du inställningar grupper finns i:

- [Skapa och hantera distributionsgrupper](/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Översikt över Microsoft 365 grupper](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Steg 4 (valfritt): Kontrollera Yammer klientorganisationen är i inbyggt läge

I ursprungligt läge Yammer alla användare i Azure Active Directory (Azure AD), alla grupper Office 365 grupper och alla filer lagras i SharePoint Online. Din Yammer måste vara i inbyggt läge för principer för kommunikationsefterlevnad för att söka igenom och identifiera riskfyllda konversationer i privata meddelanden och community-konversationer i Yammer.

Mer information om hur du konfigurerar Yammer i inbyggt läge finns i:

- [Översikt över Yammer inbyggt läge i Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Konfigurera ditt Yammer för inbyggt läge för Microsoft 365](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Steg 5 (obligatoriskt): Skapa en princip för kommunikationsefterlevnad
  
>[!Important]
>Det går inte att använda PowerShell för att skapa och hantera principer för kommunikationsefterlevnad. Om du vill skapa och hantera de här principerna måste du använda principhanteringskontrollerna [i Microsoft 365 för kommunikationsefterlevnad.](https://compliance.microsoft.com/supervisoryreview)

1. Logga in [https://compliance.microsoft.com](https://compliance.microsoft.com) med autentiseringsuppgifter för ett administratörskonto i Microsoft 365 organisation.

2. I Microsoft 365 väljer du **Kommunikationsefterlevnad.**
  
3. Välj **fliken** Principer.

4. Välj **Skapa princip om** du vill skapa och konfigurera en ny princip från en mall eller skapa och konfigurera en anpassad princip.

    Om du väljer en principmall för att skapa en princip gör du följande:

    - Bekräfta eller uppdatera principnamnet. Principnamn kan inte ändras när principen har skapats.

    - Välj vilka användare eller grupper som ska övervakas, t.ex. välja användare eller grupper som du vill utesluta. När du använder intressekonfliktmallen väljer du två grupper eller två användare som ska övervakas för intern kommunikation.

    - Välj granskare för principen. Granskare är enskilda användare och alla granskare måste ha postlådor Exchange Online. Granskare som lagts till här är de granskare som du kan välja mellan när du eskalerar en avisering i arbetsflödet för undersökning och åtgärd. När granskare läggs till i en princip får de automatiskt ett e-postmeddelande som meddelar dem om tilldelningen till principen och länkar till information om granskningsprocessen.

    - Välj ett begränsat villkorsfält, vanligtvis en typ av känslig information eller nyckelordsordlista som ska användas för principen.

    >[!NOTE]
    >Om du vill aktivera optisk teckenläsning [(OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview) för att skanna inbäddade eller bifogade bilder i meddelanden för tryckt eller handskriven text som matchar principvillkor väljer du Anpassa principvillkor och procentandel och aktiverar Extrahera tryckt eller  >   **handskriven text** från bilder för utvärdering.

    Om du väljer att använda principguiden för att skapa en anpassad princip gör du följande:

    - Ge principen ett namn och en beskrivning. Principnamn kan inte ändras när principen har skapats.

    - Välj vilka användare eller grupper som ska övervakas, inklusive alla användare i organisationen, specifika användare och grupper eller andra användare och grupper som du vill utesluta.

    - Välj granskare för principen. Granskare är enskilda användare och alla granskare måste ha postlådor Exchange Online. Granskare som lagts till här är de granskare som du kan välja mellan när du eskalerar en avisering i arbetsflödet för undersökning och åtgärd. När granskare läggs till i en princip får de automatiskt ett e-postmeddelande som meddelar dem om tilldelningen till principen och länkar till information om granskningsprocessen.

    - Välj de kommunikationskanaler du vill söka igenom, Exchange, Microsoft Teams, Yammer eller Skype för företag. Du väljer också att söka igenom tredjepartskällor om du har konfigurerat en koppling i Microsoft 365.

    - Välj den kommunikationsriktning du vill övervaka, inklusive inkommande, utgående eller intern kommunikation.

    - Definiera kommunikationspolicyvillkor [.](communication-compliance-feature-reference.md#ConditionalSettings) Du kan välja mellan meddelandeadress, nyckelord, filtyper och storlek som matchar villkoren.

    - Välj om du vill ta med typer av känslig information. I det här steget kan du välja standard- och anpassade typer av känslig information. Välj från befintliga anpassade typer av känslig information eller egna ordlistor för nyckelord i guiden för kommunikationsefterlevnadsprincip. Du kan skapa de här objekten innan du kör guiden om det behövs. Du kan också skapa nya typer av känslig information från guiden för kommunikationsefterlevnadsprincipen.

    - Välj om du vill aktivera klassificerare. Klassificerare kan identifiera olämpligt språk och bilder som skickas eller tas emot i brödtexten i e-postmeddelanden eller andra typer av text. Du kan välja följande inbyggda *klassificerare:* Hot , *svordomar*, *riktade* *trakasserier,* vuxna bilder, *racybilder* och *gorybilder*.

    - Gör [det möjligt för optisk teckenigenkänning (OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview) att skanna inbäddade eller bifogade bilder i meddelanden för tryckt eller handskriven text som matchar policyvillkor. För anpassade principer måste en eller flera villkorsstyrda inställningar som associeras med text, nyckelord, klassificerare eller typer av känslig information konfigureras i principen för att möjliggöra val av optisk teckenläsningssökning.

    - Definiera hur många procent av kommunikationen som ska granskas.

    - Granska dina principval och skapa principen.

5. Välj **Skapa princip** när du använder mallarna eller **Skicka** när du använder den anpassade principguiden.

6. Sidan **Din princip har** skapats visas med riktlinjer för när principen ska aktiveras och vilken kommunikation som ska fångas.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Steg 6 (valfritt): Skapa meddelandemallar och konfigurera anonymisering för användare

Om du vill kunna välja att svara på en principavisering genom att skicka ett påminnelsemeddelande till den associerade användaren måste du skapa minst en meddelandemall i organisationen. Meddelandemallsfälten är redigerbara innan de skickas som en del av aviseringsprocessen, och vi rekommenderar att du skapar en anpassad meddelandemall för varje princip för kommunikationsefterlevnad.

Du kan också välja att aktivera anonymisering för visade användarnamn när du undersöker principmatchningar och vidtar åtgärder för meddelanden.

1. Logga in [https://compliance.microsoft.com](https://compliance.microsoft.com) med autentiseringsuppgifter för ett administratörskonto i Microsoft 365 organisation.

2. Gå till Microsoft 365 i **kompatibilitetscentret för kommunikation.**

3. Om du vill konfigurera anonymisering för användarnamn väljer du **fliken** Sekretess.

4. Om du vill aktivera anonymisering väljer **du Visa anonymiserade versioner av användarnamn.**

5. Välj **Spara**.

6. Gå till fliken **Meddelandemallar** och välj sedan **Skapa meddelandemall**.

7. Fyll i **följande fält på** sidan Ändra en meddelandemall:

    - Mallnamn (obligatoriskt)
    - Skicka från (obligatoriskt)
    - Kopia och Hemlig kopia (valfritt)
    - Ämne (obligatoriskt)
    - Meddelandetext (obligatoriskt)

8. Välj **Spara** för att skapa och spara meddelandemallen.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Steg 7 (valfritt): Testa kommunikationsefterlevnadsprincipen

När du har skapat en princip för kommunikationsefterlevnad är det en bra idé att testa den för att kontrollera att de villkor du definierar tillämpas korrekt av principen. Du kanske också vill testa [dina principer för dataförlustskydd (DLP)](create-test-tune-dlp-policy.md) om dina principer för kommunikationsefterlevnad innehåller typer av känslig information. Se till att ge dina principer tid att aktivera så att de meddelanden som du vill testa fångas upp.

Följ de här stegen för att testa din policy för kommunikationsefterlevnad:

1. Öppna en e-postklient, Microsoft Teams eller Yammer när du är inloggad som en övervakad användare som definierats i principen du vill testa.

2. Skicka ett e-Microsoft Teams eller ett Yammer meddelande som uppfyller de villkor som du har definierat i policyn för kommunikationsefterlevnad. Det här testet kan vara ett nyckelord, en storlek på en bifogad fil, en domän, osv. Kontrollera att du bestämmer om de konfigurerade villkorsinställningarna i principen är för restriktiva eller för eftersägna.

    > [!NOTE]
    > Det kan ta upp till 24 timmar innan e-postmeddelanden bearbetas helt i en princip. Kommunikation i Microsoft Teams, Yammer och tredjepartsplattformar kan ta upp till 48 timmar för att fullständigt bearbeta i en princip.

3. Logga in Microsoft 365 granskare som anges i policyn för kommunikationsefterlevnad. Navigera till **aviseringar om**  >  **kommunikationsefterlevnad** för att visa aviseringar för dina principer.

4. Åtgärda aviseringen med hjälp av åtgärdskontrollerna och kontrollera att aviseringen är korrekt matchad.

## <a name="next-steps"></a>Nästa steg

När du har slutfört de här stegen för att skapa din första princip för kommunikationsefterlevnad får du aviseringar från aktivitetsindikatorer efter 24–48 timmar. Konfigurera ytterligare principer efter behov med hjälp av vägledning i steg 5 i den här artikeln.

Mer information om hur du undersöker aviseringar om kommunikationsefterlevnad finns i Undersöka [och åtgärda aviseringar om kommunikationsefterlevnad.](communication-compliance-investigate-remediate.md)
