---
title: Utvärdera Microsoft Defender för Office 365
description: Defender för Office 365 i utvärderingsläge skapar Defender för Office 365-e-postprinciper som loggar ut, till exempel skadlig programvara, men inte agerar på meddelanden.
keywords: utvärdera Office 365, Microsoft Defender för Office 365, office 365 utvärdering, prova Office 365, Microsoft Defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d16c0afc675ba759e392c9fe9a44c42b89dbad0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287659"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Utvärdera Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Utvärdering av Microsoft Defender för Office 365 är en offentlig förhandsversion. Den här förhandsversionen tillhandahålls utan ett servicenivåavtal. Vissa funktioner kanske inte stöds eller kan ha begränsade funktioner.

Genom att genomföra en omfattande utvärdering av säkerhetsprodukter kan du få välgrundade beslut om uppgraderingar och köp. It helps to try out the security product's capabilities to assess how it can help your security operations team in their daily tasks.

Utvärderingsupplevelsen i Microsoft Defender för [Office 365](office-365-atp.md) har utformats för att eliminera komplexiteten i konfigurationen av enheter och miljöer så att du kan fokusera på att utvärdera funktionerna i säkerhetslösningen. Den gäller endast e-postskydd och inte SharePoint, Office-klienter eller Teams.

Om du inte redan har en licens som stöder Microsoft Defender för Office 365 kan du påbörja en kostnadsfri [30-dagarsutvärdering](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) och testa funktionerna i Säkerhets- och & Office 365 ( https://protection.office.com/homepage) . Du kommer att njuta av den snabba uppsättningen och du kan enkelt stänga av den om det behövs.

## <a name="how-the-evaluation-works"></a>Så här fungerar utvärderingen

Defender för Office 365 i utvärderingsläge skapar Defender för Office 365-e-postprinciper som loggar ut, till exempel skadlig programvara, men inte agerar på meddelanden. Du behöver inte ändra konfigurationen av MX-posten.

Med utvärderingsläge [konfigureras principer för](atp-safe-attachments.md) [säkra](atp-safe-links.md)bifogade filer, säkra länkar och skydd [mot](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) nätfiske för din räkning. Alla Defender för Office 365-principer skapas i läget för icke-tvingande tillämpning i bakgrunden och visas inte för dig.

Som en del av konfigurationen konfigurerar utvärderingsläget även [utökad filtrering för kopplingar.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Det förbättrar filtreringsprecisionen genom att bevara IP-adress och avsändarinformation, som annars går förlorad när e-post passerar genom en e-postsäkerhetsgateway (ESG) framför Defender för Office 365. Förbättrad filtrering förbättrar också filtreringsprecisionen för skydd mot skräppost och nätfiske i Exchange Online Protection (EOP).

För att minimera potentiell produktionsrisk för vissa scenarier som inte stöds kan du kringgå all EOP-filtrering genom att skapa en transportregel som anger SCL (Spam Confidence Level) till -1. Mer information finns i Använda EAC för att skapa en e-postflödesregel som [anger SCL för ett meddelande.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)  

När utvärderingsläget har ställts in uppdateras en rapport dagligen med upp till 90 dagars datauppspelning av meddelanden som skulle ha blockerats om principerna implementerats (till exempel ta bort, skicka till skräppost, karantän). Rapporter skapas för alla Defender för Office 365- och EOP-identifieringar. De aggregeras per identifieringsteknik (till exempel personifiering) och kan filtreras efter tidsperiod. Dessutom kan du skapa meddelanderapporter på begäran för att skapa anpassade pivoter eller för att djupdykar meddelanden med hjälp av Threat Explorer.

Med den förenklade uppsättningen kan du fokusera på:

- Köra utvärderingen
- Få en detaljerad rapport
- Analysera rapporten för åtgärd
- Presentera utvärderingsresultatet

## <a name="before-you-begin"></a>Innan du börjar

### <a name="licensing"></a>Licensiering

För att få åtkomst till utvärderingen måste du uppfylla licenskraven. Någon av följande licenser fungerar:

- Microsoft Defender för Office 365 Abonnemang 1
- Microsoft Defender för Office 365 abonnemang 2
- Microsoft 365 E5, Microsoft 365 E5 Security
- Office 365 E5

Om du inte har någon av dessa licenser måste du skaffa en utvärderingsversionslicens.

#### <a name="trial"></a>Utvärderingsversion

Om du vill ha en utvärderingslicens för Microsoft Defender för Office 365 måste du ha rollen **Faktureringsadministratör** eller **Global administratör.** Begär behörighet från någon som har rollen Global administratör. [Läs mer om prenumerationer och licenser](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

När du har rätt roll är det rekommenderade att skaffa en utvärderingslicens för Microsoft Defender för Office 365 (abonnemang 2) i administrationscentret för Microsoft 365 genom att gå till Billing > Purchase services. Utvärderingsversionen omfattar en kostnadsfri provperiod på 30 dagar för 25 licenser. [Skaffa en utvärderingsversion av Microsoft Defender för Office 365 (abonnemang 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Det finns ett 30-dagarsfönster med en utvärdering som du kan använda för att övervaka och rapportera avancerade hot. Du kan också köpa en betald prenumeration om du vill ha hela Defender för Office 365-funktionerna.

### <a name="roles"></a>Roller

Exchange Online-roller krävs för att konfigurera Defender för Office 365 i utvärderingsläge.

- [Läs mer om behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [Läs mer om hur du tilldelar administratörsroller](../../admin/add-users/assign-admin-roles.md)

Följande roller krävs:

|Uppgift|Roll|
|---|---|
|Skaffa en kostnadsfri utvärderingsversion eller köp Microsoft Defender för Office 365 (abonnemang 2)|Rollen Faktureringsadministratör ELLER Global administratör|
|Skapa utvärderingsprincip|Roll för fjärrdomäner och godkända domäner. Rollen Säkerhetsadministratör|
|Redigera utvärderingsprincip|Roll för fjärrdomäner och godkända domäner. Rollen Säkerhetsadministratör|
|Ta bort utvärderingsprincip|Roll för fjärrdomäner och godkända domäner. Rollen Säkerhetsadministratör |
|Visa utvärderingsrapport|Rollen Säkerhetsadministratör ELLER Säkerhetsläsare|
|


### <a name="enhanced-filtering"></a>Förbättrad filtrering

Dina Exchange Online Protection-principer, till exempel skydd för massutskick och skräppost, förblir oförändrade. Leverans av meddelanden förblir också oförändrad. Men utvärderingen aktiverar förbättrad filtrering för kopplingar, vilket påverkar e-postflödet och Exchange Online Protection-principerna om de inte kringgås.

Förbättrad filtrering för kopplingar gör att klientorganisationen kan använda skydd mot förfalskning. Förfalskning stöds inte om du använder en e-postsäkerhetsgateway (ESG) utan att ha aktiverat utökad filtrering för kopplingar.

### <a name="urls"></a>URL:er

URL:er detoneras under e-postflödet. Om du inte vill att specifika URL:er ska detoneras hanterar du listan med tillåtna URL-adresser på rätt sätt. Mer [information finns i Hantera klientorganisationens lista över tillåtna/blockerade](tenant-allow-block-list.md) användare.

URL-länkar i e-postmeddelandet kommer inte att radbrytas, för att minska kundens påverkan.

### <a name="email-routing"></a>E-postdirigering

Förbered motsvarande information om hur din e-post dirigeras, inklusive namnet på den inkommande koppling som dirigerar din e-post. Om du bara använder Exchange Online Protection har du inte någon koppling.  [Lär dig mer om e-postflöde och e-postdirigering](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Exempel på e-postdirigeringsscenarier som stöds:

- **Tredjepartspartner och/eller** lokal tjänstprovider: Den inkommande koppling som du vill utvärdera använder en tredjepartsleverantör och/eller så använder du en lösning för e-postsäkerhet lokalt.
- **Endast Microsoft Exchange Online Protection:** Den klientorganisation som du vill utvärdera använder Office 365 för e-postsäkerhet och MX-posten (Mail Exchange) pekar på Microsoft.

### <a name="email-security-gateway"></a>E-postsäkerhetsgateway

Om du använder en e-postsäkerhetsgateway från tredje part (ESG) behöver du känna till leverantörens namn. Om du använder en lokal eller icke-stödd ESG-leverantör måste du känna till de offentliga IP-adresserna för enheterna.

Tredjepartspartner som stöds är:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Soforer
- Symantec
- Trend Micro

### <a name="scoping"></a>Scoping

Du kommer att kunna begränsa utvärderingen till en inkommande koppling. Om det inte finns någon konfigurerad anslutning kan administratörer i utvärderingsomfånget samla in data från alla användare i klientorganisationen för att utvärdera Defender för Office 365.

## <a name="get-started-with-the-evaluation"></a>Komma igång med utvärderingen

Leta reda på kortet för utvärderingsuppsättningen i Microsoft Defender för Office 365 i Säkerhets- och & Office 365 (från https://protection.office.com/homepage) tre åtkomstpunkter:

- Threat management > Dashboard
- Policy för > hantering av hot
- Reports > Dashboard

## <a name="setting-up-the-evaluation"></a>Konfigurera utvärderingen

När du startar set-up-flödet för utvärderingen får du två routningsalternativ. Beroende på organisationens behov av e-postdirigering och utvärdering kan du välja om du använder en tredjeparts- och/eller lokal tjänstprovider eller endast Microsoft Exchange Online.

- Om du använder en partner från tredje part och/eller en lokal tjänstprovider måste du välja namnet på leverantören i listrutan. Ange annan kopplingsrelaterad information.

- Välj Microsoft Exchange Online om MX-posten pekar på Microsoft och du har en Exchange Online-postlåda.

Granska inställningarna och redigera dem om det behövs. Välj sedan **Skapa utvärdering.** Du bör få ett bekräftelsemeddelande som anger att din kondation är klar.

Utvärderingsrapporten för Microsoft Defender för Office 365 genereras en gång per dag. Det kan ta upp till 24 timmar innan data fylls i.

### <a name="exchange-rules-optional"></a>Exchange-regler (valfritt)

Om du har en befintlig gateway aktiverar utvärderingsläget utökad filtrering för kopplingar. Detta förbättrar filtreringens precision genom att ändra IP-adressen för inkommande avsändare. Detta kan ändra filtrets bedömning och om du inte kringgår Exchange Online Protection kan detta förändra slutbarheten för vissa meddelanden. I det här fallet kanske du tillfälligt vill kringgå filtrering för att analysera påverkan. Om du vill kringgå detta navigerar du till administrationscentret för Exchange och skapar en princip för SCL -1 (om du inte redan har ett). Mer information om regelkomponenter och hur de fungerar finns i E-postflödesregler (transportregler) i Exchange Online.

## <a name="evaluate-capabilities"></a>Utvärdera funktioner

När utvärderingsrapporten har skapats kan du se hur många avancerade hotlänkar, avancerade hotbilagor och potentiella impersonationer som identifierats i arbetsytorna för e-post och samarbete i organisationen.

När utvärderingsversionen har upphört att gälla kan du fortsätta att komma åt rapporten i 90 dagar. Men det samlar inte in mer information. Om du vill fortsätta använda Microsoft Defender för Office 365 när utvärderingsversionen har gått ut kontrollerar du att du köper en betald prenumeration för Microsoft Defender för [Office 365 (abonnemang 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Du kan när som **helst** gå till Inställningar och uppdatera din routning eller inaktivera utvärderingen. Du måste dock gå igenom samma process igen om du bestämmer dig för att fortsätta utvärderingen när du har inaktiverat den.

## <a name="provide-feedback"></a>Ge feedback

Din feedback hjälper oss att bli bättre på att skydda miljön mot avancerade attacker. Dela med dig av din upplevelse och dina intryck av produktfunktioner och utvärderingsresultat.

Välj **Ge feedback om** du vill berätta för oss vad du tycker.
