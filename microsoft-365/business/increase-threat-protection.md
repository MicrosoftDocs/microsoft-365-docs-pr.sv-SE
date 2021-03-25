---
title: Öka skyddet mot hot för Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Konfigurera Microsoft Defender för Office 365 och skydda känsliga data mot nätfiske, skadlig programvara och andra hot.
ms.openlocfilehash: 6526ed9a849e83f19f74656004978089ce367ea9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198400"
---
# <a name="increase-threat-protection"></a>Öka hotskyddet

Den här artikeln hjälper dig att öka skyddet för Microsoft 365-prenumerationen för att skydda mot nätfiske, skadlig programvara och andra hot. Dessa rekommendationer är lämpliga för organisationer med ett ökat behov av säkerhet, t.ex. juristkontor och sjukvårdskontoret.

Innan du börjar kontrollerar du ditt Office 365 Secure Score. Office 365 Secure Score analyserar organisationens säkerhet utifrån vanliga aktiviteter och säkerhetsinställningar och tilldelar en poäng. Börja med att anteckna det aktuella resultatet. Om du vill öka poäng slutför du åtgärderna som rekommenderas i den här artikeln. Målet är inte att uppnå det högsta resultatet, utan att vara medveten om möjligheter att skydda din miljö som inte negativt påverkar produktiviteten för användarna.

Mer information finns i [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Höja skyddsnivån för skadlig programvara i e-post

Din Office 365- eller Microsoft 365-miljö innehåller skydd mot skadlig programvara. Du kan öka skyddet genom att blockera bifogade filer med filtyper som ofta används för skadlig programvara. Öka skyddet mot skadlig programvara i e-post:

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med autentiseringsuppgifterna för ditt administratörskonto.

2. I det vänstra &amp; navigeringsfönstret, under Hothantering, i säkerhetsefterlevnadscentret väljer du **Policy** \> **Anti-Malware**.

3. Dubbelklicka på standardprincipen om du vill redigera den här företagsövergripande principen.

4. Välj **Inställningar.**

5. Under **Vanliga typer av bifogade filer väljer** du **På**. De filtyper som är blockerade visas i fönstret direkt nedanför den här kontrollen. Se till att du lägger till följande filtyper:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Om det behövs kan du lägga till eller ta bort filtyper senare.

6. Välj **Spara.**

Mer information finns i Skydd [mot skadlig programvara i EOP.](../security/office-365-security/anti-malware-protection.md)

## <a name="protect-against-ransomware"></a>Skydda mot utpressningstrojaner

Utpressningstrojaner begränsar åtkomsten till data genom att kryptera filer eller låsa datorskärmar. Sedan försöker den utträlja pengar från en leverantör genom att begära "utpressningstrojan", vanligtvis i form av cryptocurrencies som Bitcoin, i utbyte mot åtkomst till data.

För att skydda mot utpressningstrojaner skapar du en eller flera e-postflödesregler för att blockera filnamnstillägg som ofta används för utpressningstrojaner. (Du har lagt till dessa regler för att [höja skyddsnivån mot skadlig programvara i e-poststeg.)](#raise-the-level-of-protection-against-malware-in-mail) Du kan också varna användare som får dessa bifogade filer i e-postmeddelanden.

Utöver de filer som du blockerade i föregående steg är det bra att skapa en regel som varnar användare innan de öppnar bifogade Office-filer som innehåller makron. Utpressningstrojaner kan vara dolda i makron, så varna användarna att inte öppna dessa filer från personer de inte känner.

Så här skapar du en regel för e-posttransport:

1. Gå till administrationscentret på <https://admin.microsoft.com> och välj **Administrationscenter** \> **Exchange**.

2. Välj regler i kategorin E-postflöde.  

3. Välj **+** och välj sedan Skapa en ny **regel.**

4. Välj **Fler alternativ** längst ned i dialogrutan om du vill se alla alternativ.

5. Tillämpa inställningarna i följande tabell för regeln. Använd standardvärdena för resten av inställningarna, såvida du inte vill ändra dem.

6. Välj **Spara**.

|Inställning|Varna användare innan de öppnar bifogade filer i Office-filer||
|---|---|---|
|Namn|Regel för utpressningstrojaner: varna användare|
|Tillämpa den här regeln om . . .|En bifogad fil . . . filtillägg matchar . . .|
|Ange ord eller fraser|Lägg till följande filtyper:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Gör följande. . .|Meddela mottagaren med ett meddelande|
|Ange meddelandetext|Öppna inte den här typen av filer från personer som du inte känner eftersom de kan innehålla makron med skadlig kod.|

Mer information finns i:

- [Utpressningstrojaner: minska riskerna](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Återställa OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Stoppa automatisk vidarebefordran av e-post

Hackare som får åtkomst till en användares postlåda kan stjäla e-post genom att ställa in så att postlådan vidarebefordrar e-post automatiskt. Det här kan inträffa även utan användarens uppmärksamhet. Konfigurera en e-postflödesregel för att förhindra detta.

Om du vill skapa en e-posttransportregel kan du antingen [titta på den här](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) korta videon eller följa de här stegen:

1. I administrationscentret för Microsoft 365 väljer du **Administratörscentra** \> **Exchange**.

2. Välj regler i kategorin E-postflöde.  

3. Välj **+** och välj sedan Skapa en ny **regel.**

4. Om du vill se alla alternativ **väljer du Fler** alternativ längst ned i dialogrutan.

5. Använd inställningarna i följande tabell. Använd standardvärdena för resten av inställningarna, såvida du inte vill ändra dem.

6. Välj **Spara**.

|Inställning|Varna användare innan de öppnar bifogade filer i Office-filer|
|---|---|
|Namn|Förhindra automatisk vidarebefordran av e-post till externa domäner|
|Tillämpa den här regeln om ...|Avsändaren . . . är extern/intern . . . Inom organisationen|
|Lägg till villkor|Meddelandeegenskaperna . . . ange meddelandetypen . . . Vidarebefordra automatiskt|
|Gör följande ...|Blockera meddelandet . . . avvisa meddelandet och ge en förklaring.|
|Ange meddelandetext|Automatisk vidarebefordran av e-post utanför organisationen förhindras av säkerhetsskäl.|


## <a name="protect-your-email-from-phishing-attacks"></a>Skydda din e-post från nätfiskeattacker

Om du har konfigurerat en eller flera egna domäner för din Office 365- eller Microsoft 365-miljö kan du konfigurera riktad skydd mot nätfiske. Skydd mot nätfiske, en del av Microsoft Defender för Office 365, kan skydda organisationen från skadliga personifieringsbaserade nätfiskeattacker och andra nätfiskeattacker. Om du inte har konfigurerat en egen domän behöver du inte göra det.

Vi rekommenderar att du kommer igång med det här skyddet genom att skapa en princip för att skydda dina viktigaste användare och din anpassade domän.

Om du vill skapa en policy mot nätfiske i [](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)Microsoft Defender för Office 365 kan du titta på den här korta utbildningsvideon eller följa stegen nedan:

1. Gå till [https://protection.office.com](https://protection.office.com).

2. I det vänstra &amp; navigeringsfönstret i säkerhetsefterlevnadscentret, under **Hothantering,** väljer du **Princip**.

3. Välj **Nätfiskeskydd** **på sidan Princip.**

4. På sidan **mot nätfiske** väljer du **+ Skapa.** En guide startar stegen för att definiera din policy mot nätfiske.

5. Ange namn, beskrivning och inställningar för principen enligt rekommendationen i följande tabell. Mer information finns i Läs [mer om nätfiskeprincip i Microsoft Defender för Office 365-alternativ.](../security/office-365-security/set-up-anti-phishing-policies.md)

6. När du har granskat inställningarna väljer du Skapa **den här principen** eller **Spara** efter behov.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Domän och mest värdefull kampanjpersonal|
|Beskrivning|Se till att den viktigaste personalen och vår domän inte utger sig för att vara.|
|Lägga till användare att skydda|Välj **+ Lägg till ett villkor, mottagaren är**. Skriv användarnamn eller ange e-postadressen till kandidaten, kampanjhanteraren och andra viktiga personalmedlemmar. Du kan lägga till upp till 20 interna och externa adresser som du vill skydda från personifiering.|
|Lägga till domäner att skydda|Välj **+ Lägg till ett villkor, mottagarens domän är**. Ange den anpassade domän som är kopplad till din Microsoft 365-prenumeration, om du har definierat en sådan. Du kan ange mer än en domän.|
|Välja åtgärder|Om e-post skickas av en imiterad användare: Välj Omdirigera meddelande till en annan e-postadress och skriv sedan säkerhetsadministratörens e-postadress. Till exempel Så här ser det ut, Det kan vara *<span> <span> @ contoso.com.* Om e-post skickas av en imiterad domän: Välj **Sätt meddelande i karantän**.|
|Postlådeintelligens|Postlådeintelligens är valt som standard när du skapar en ny princip mot nätfiske. Lämna den här inställningen **På** för bästa resultat.|
|Lägga till betrodda avsändare och domäner|Här kan du lägga till din egen domän eller andra betrodda domäner.|
|Tillämpas på|Välj **Mottagarens domän är**. Under **Valfri av dessa** väljer du **Välj**. Välj **+ Lägg till.** Markera kryssrutan bredvid namnet på domänen, till exempel *contoso. <span> <span> com*, i listan och välj sedan Lägg **till**. Välj **Klar**.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Skydda mot skadliga bilagor och filer med säkra bifogade filer

Personer skickar, tar emot och delar regelbundet bifogade filer, till exempel dokument, presentationer, kalkylblad med mera. Det är inte alltid lätt att avgöra om en bifogad fil är säker eller skadlig bara genom att titta på ett e-postmeddelande. Microsoft Defender för Office 365 har skydd mot bifogade filer, men det här skyddet är inte aktiverat som standard. Vi rekommenderar att du skapar en ny regel för att börja använda det här skyddet. Skyddet omfattar filer i SharePoint, OneDrive och Microsoft Teams.

Om du vill skapa en princip för säkra bifogade filer [kan](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)du antingen titta på den här korta videon eller utföra följande steg:

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt administratörskonto.

2. I det vänstra &amp; navigeringsfönstret i säkerhetsefterlevnadscentret, under **Hothantering,** väljer du **Princip**.

3. På sidan Princip väljer du Säkra **bifogade filer.**

4. På sidan Säkra bifogade filer tillämpar du det här skyddet allmänt genom att markera kryssrutan Aktivera ATP för **SharePoint, OneDrive och Microsoft Teams.**

5. Välj **+** för att skapa en ny princip.

6. Använd inställningarna i följande tabell.

7. När du har granskat inställningarna väljer du **Skapa den här principen** eller **Spara** efter behov.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Blockera aktuella och framtida e-postmeddelanden med upptäckt skadlig programvara.|
|Beskrivning|Blockera aktuella och framtida e-postmeddelanden och bifogade filer med identifierade skadlig programvara.|
|Spara bifogade filer – okänd skadlig kod|Välj **Blockera – blockera aktuella och framtida e-postmeddelanden och bifogade filer med upptäckt skadlig kod.**|
|Omdirigera bifogad fil vid identifiering|Aktivera omdirigering (markera den här rutan) Ange administratörskontot eller en postlådekonfiguration för karantän.          Använd alternativet ovan om genomsökning efter bifogade filer på tider eller fel inträffar (markera den här rutan).|
|Tillämpas på|Mottagarens domän är . . . väljer du din domän.|

Mer information finns i Konfigurera [principer för skydd mot nätfiske i Microsoft Defender för Office 365.](../security/office-365-security/set-up-anti-phishing-policies.md)

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Skydda mot nätfiskeattacker med Säkra länkar

Hackare döljer ibland skadliga webbplatser i länkar i e-postmeddelanden och andra filer. Säkra länkar, en del av Microsoft Defender för Office 365, kan skydda organisationen genom att tillhandahålla snabb verifiering av webbadresser (URL:er) i e-postmeddelanden och Office-dokument. Skydd definieras genom principer för säkra länkar.

Vi rekommenderar att du gör följande:

- Ändra standardprincipen för att öka skyddet.

- Lägg till en ny princip som är riktad för alla mottagare i din domän.

Konfigurera säkra länkar genom att titta [på den här korta utbildningsvideon](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)eller utföra följande steg:

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt administratörskonto.

2. I det vänstra &amp; navigeringsfönstret i säkerhetsefterlevnadscentret, under **Hothantering,** väljer du **Princip**.

3. På sidan Princip väljer du **Säkra länkar.**

Så här ändrar du standardprincipen:

1. Välj Standardprincip under Principer **som gäller för** hela organisationen på sidan **Säkra** länkar.

2. Under **Inställningar som gäller för innehåll utom e-post** väljer du Microsoft **365-appar för företag, Office för iOS och Android.**

3. Välj **Spara**.

Så här skapar du en ny princip som är riktad till alla mottagare i din domän:

1. På sidan Säkra länkar, under **Principer som gäller för hela organisationen, väljer** du för att skapa en ny **+** princip.

2. Använd inställningarna i följande tabell.

3. Välj **Spara**.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Princip för säkra länkar för alla mottagare i domänen|
|Välj åtgärden för okända potentiellt skadliga URL-adresser i meddelanden|Välj **På – URL:er skrivs om och kontrolleras mot en lista med kända skadliga länkar när användaren klickar på länken.**|
|Använda säkra bifogade filer för att söka igenom nedladdningsbart innehåll|Markera den här rutan.|
|Tillämpas på|Mottagarens domän är . . . väljer du din domän.|

Mer information finns i [Säkra länkar.](../security/office-365-security/safe-links.md)

## <a name="go-to-intune-admin-center"></a>Gå till administrationscentret för Intune

1. Logga in på [Azure Portal](https://portal.azure.com/).

2. Välj **Alla tjänster** och skriv *Intune* i **sökrutan**.

3. När resultatet visas väljer du start bredvid **Microsoft Intune för att göra** den till en favorit och lätt att hitta senare.

Förutom administrationscentret kan du använda Intune för att registrera och hantera organisationens enheter. Mer information finns i Funktioner [efter registreringsmetod för Windows-enheter och](/intune/enrollment/enrollment-method-capab) [Registreringsalternativ för enheter som hanteras av Intune.](/intune/enrollment-options)
