---
title: Klienthantering för Microsoft 365 för företag
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: En översikt över planering, distribution och kontinuerlig drift av Microsoft 365 klientorganisationen.
ms.openlocfilehash: 42bde00fbd4ddc1cf92236f099a22b2260dbb980
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405684"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Klienthantering för Microsoft 365 för företag

Att skapa en väg för din organisations digitala omvandling med molntjänster kräver en stabil grund som medarbetarna kan förlita sig på för produktivitet, samarbete, prestanda, sekretess, efterlevnad och säkerhet.

Rätt konfiguration av Microsoft 365-klientorganisationen ger grunden, så att medarbetarna kan fokusera på att få jobbet gjort och IT-avdelningen att fokusera på end-to-end-lösningar som ger ytterligare affärsvärde. 

Den här lösningen tar dig genom konfigurationen av den grunden i följande steg:

1. Fastställ dina klientorganisationar
2. Optimera dina nätverk
3. Synkronisera dina identiteter och tillämpa säkra inloggningar
4. Migrera dina Windows, Office och lokala nätverk från Office och data
5. Distribuera hantering av enheter och program

Men först ska vi se hur en klientorganisation är och hur en klientorganisation som ger en fast grund ser ut.

## <a name="a-microsoft-365-tenant-defined"></a>En Microsoft 365 definierad klientorganisation

En Microsoft 365 är en dedikerad instans av tjänsterna för Microsoft 365 och dina organisationsdata som lagras på en viss standardplats, till exempel Europa eller Nordamerika. Den här platsen anges när du skapar klientorganisationen för din organisation. Varje Microsoft 365 är distinkt, unik och skiljer sig från alla Microsoft 365 klientorganisationen. Du skapar en Microsoft 365 när du köper en eller flera produkter från Microsoft, till exempel Microsoft 365 E3 eller E5, och en uppsättning licenser för var och en.

Din Microsoft 365-klientorganisation inkluderar också en Azure Active Directory -klientorganisation (Azure AD), som är en dedikerad instans av Azure AD för användarkonton, grupper och andra objekt. Varje Azure AD-klient är distinkt, unik och skiljer sig från alla andra Azure AD-klientorganisationen. Även om din organisation kan ha flera Azure AD-klientorganisationar som du kan konfigurera med Azure-prenumerationer, kan Microsoft 365-klientorganisationen bara använda en enda Azure AD-klientorganisation, den som skapades när du skapade klientorganisationen. 

Här är ett exempel:

![Ett exempel Microsoft 365 klientorganisation med Azure AD-klientorganisationen](../media/tenant-management-overview/tenant-management-example-tenant.png)

*Klientorganisationshantering* är planering, distribution och kontinuerlig drift av Microsoft 365 klientorganisationen. 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>Attribut för en väl utformad och fungerande klientorganisation

Förutom rätt namn och plats för din klientorganisation finns det ytterligare element som du kan använda för att planera, distribuera och hantera för att säkerställa att din användarupplevelse av appar för molnproduktivitet, till exempel Microsoft Teams och Exchange Online, är effektiv, säker och &mdash; &mdash; effektiv.

Här är de olika elementen:

- Du har rätt uppsättning produkter (prenumerationer) och licenser.
  - Uppsättningen produkter matchar dina affärs-, IT- och säkerhetsbehov.
  - Det finns ett lämpligt antal licenser för dina medarbetare och förväntade förändringar av personal.
- För nätverk:
  - Du har konfigurerat rätt DNS-domännamn.
  - För företagsnätverk har du optimerad nätverkstrafik till Microsoft-nätverket för anställda på plats.
  - Du har optimerad nätverkstrafik för fjärranslutna medarbetare som använder en VPN-klient.
- Du har synkroniserat dina AD DS-konton (Active Directory Domain Services), grupper och andra objekt.
  - Dina Azure AD-klientkonton mappas till Exchange Online postlådor med rätt DNS-domäner för e-postadresser.
  - Dina användarkonton har tilldelats rätt licenser från rätt köpta produkter (t.ex. Microsoft 365 E3 eller E5).
- Du har konfigurerat en stark identitets- och åtkomsthantering.
  - Du kräver säker användar inloggning utan lösenord eller multifaktorautentisering (MFA).
  - Du har villkorsstyrda åtkomstprinciper som tillämpar inloggningskrav och begränsningar för högre säkerhetsnivåer.
- Lokala servrar Office och deras data har migrerats till molnappar eller används i en hybridkonfiguration.
- Du utför enhetshantering med Intune eller Basic Mobility and Security inbyggt i Microsoft 365.
  - Dina organisationsägda enheter registreras och hanteras.
  - Programmen för personliga enheter hanteras.

Här är ett exempel på Microsoft 365 klientorganisation med alla dessa element på plats.

![Ett exempel Microsoft 365 klientorganisation](../media/tenant-management-overview/tenant-management-tenant-config.png)

I den här illustrationen Microsoft 365 klientorganisationen:

- Produkter och licenser för Microsoft 365 E3 och E5.
- Microsoft 365 produktivitetsprogram.
- Intune med registrerade enheter samt principer för enheter och program.
- En Azure AD-klient som har synkroniserat användarkonto (grupper och andra katalogobjekt visas inte), domäner och villkorsstyrda åtkomstprinciper.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Klientorganisationsfunktioner för Microsoft 365 för företag

I följande avsnitt och tabell finns nyckelfunktioner och licensiering för stegen i den här lösningen.

### <a name="tenant"></a>Klientorganisation

| Resurs eller funktion | Beskrivning | Licensiering |
|:-------|:-----|:-------|
| Flera klientorganisationer | Varje Microsoft 365 är distinkt, unik och skiljer sig från alla Microsoft 365 klientorganisationen. Med flera klientorganisationar finns det restriktioner och ytterligare överväganden när du hanterar dem och tillhandahåller tjänster till användarna. | Microsoft 365 E3 eller E5 | 
| Migrering av postlådor mellan klientorganisationer | Innehavaradministratörer kan flytta postlådor mellan klientorganisationar med minimalt beroende av infrastruktur i sina lokala system. Det här tar bort behovet av postlådor för off-board och onboard. | Microsoft 365 E3 eller E5 | 
| Multi-Geo | Klientorganisationen kan lagra data i vila på andra datacenters geoplatser som du har valt att uppfylla krav för datalagring. | Microsoft 365 E3 eller E5 | 
| Flytta basdata till ett nytt datacenter geo | När Microsoft lägger till nya datacenter geos för ytterligare kapacitet och beräknar resurser kan du begära en geoflyttning av ett datacenter för geodata som ska lagras för dina kärndata. | Microsoft 365 E3 eller E5 | 
||||

### <a name="networking"></a>Nätverk

| Resurs eller funktion | Beskrivning | Licensiering |
|:-------|:-----|:-------|
| Nätverksinsikter | Nätverksprestandamätvärden som samlas in från din Microsoft 365 för att hjälpa dig att utforma nätverks perimeter för kontorsplatserna. | Microsoft 365 E3 eller E5 | 
| Automatisera slutpunktsuppdateringar | Automatisera konfiguration och löpande uppdateringar för Microsoft 365 i dina klient-PAC-filer och nätverksenheter och -tjänster. | Microsoft 365 E3 eller E5 | 
||||

### <a name="identity"></a>Identitet

| Resurs eller funktion | Beskrivning | Licensiering |
|:-------|:-----|:-------|
| Synkronisera ad ds (Active Directory Domain Services) lokalt med Azure AD-klientorganisationen    | Utnyttja din lokala identitetsprovider för användarkonton, grupper och andra objekt. | Microsoft 365 E3 eller E5 |
| MFA som förstärks med säkerhetsstandarder   | Skydda er mot identitetsstölder och komprometterade enheter genom att kräva en andra form av autentisering vid inloggning. Säkerhetsstandarderna kräver MFA för alla användarkonton.   | Microsoft 365 E3 eller E5 |
| MFA som förstärks med villkorsstyrd åtkomst| Kräv MFA baserat på attributen för inloggningen med villkorsstyrda åtkomstprinciper.    | Microsoft 365 E3 eller E5 | 
| MFA som förstärks med riskbaserad villkorsstyrd åtkomst   | Använd Microsoft Defender for Identity för att kräva MFA baserat på risken som är kopplad till användarens inloggning. | Microsoft 365 E5 eller E3 med Azure AD Premium P2-licenser | 
| Självbetjäning för återställning av lösenord (SSPR)    | Låt användarna återställa eller låsa upp sina lösenord och konton.  | Microsoft 365 E3 eller E5 |
||||

### <a name="migration"></a>Migrering

| Resurs eller funktion | Beskrivning | Licensiering |
|:-------|:-----|:-------|
| Migrera till Windows 10 | Migrera dina enheter som kör Windows 7 eller Windows 8.1 till Windows 10 Enterprise. | Windows 10 Enterprise ingår i Microsoft 365 E3 eller E5 | 
| Migrera till Microsoft 365-appar för företag | Migrera dina Office klientprogram som Word och PowerPoint till versioner som är installerade från molnet och som är uppdaterade med nya funktioner. | Microsoft 365 E3 eller E5 | 
| Migrera lokala servrar och data till Microsoft 365 | Migrera dina Exchange, webbplatser SharePoint och Skype för företag Online till Microsoft 365 molntjänster. | Microsoft 365 E3 eller E5 | 
||||

### <a name="device-and-app-management"></a>Enhets- och apphantering

| Resurs eller funktion | Beskrivning | Licensiering |
|:-------|:-----|:-------|
| Microsoft Intune | En molnbaserad tjänst som tillhandahåller hantering av mobila enheter (MDM) och hantering av mobilprogram (MAM) för att styra hur organisationens program och enheterna används, inklusive mobiltelefoner, surfplattor och bärbara datorer. | Microsoft 365 E3 eller E5 | 
| Grundläggande Mobility and Security | Skydda och hantera användarnas mobila enheter som iPhone, iPad, Android och Windows med den här inbyggda tjänsten.  | Microsoft 365 E3 eller E5 | 
||||

## <a name="next-steps"></a>Nästa steg

Använd de här anvisningarna för att konfigurera och Microsoft 365 klientorganisationen.

1. [Fastställ dina klientorganisationar](tenant-management-tenants.md)
2. [Optimera dina nätverk](tenant-management-networking.md)
3. [Synkronisera dina identiteter och tillämpa säkra inloggningar](tenant-management-identity.md)
4. [Migrera dina lokala data Office och data](tenant-management-migration.md)
5. [Distribuera hantering av enheter och program](tenant-management-device-management.md)

[![Stegen för att distribuera och hantera en klientorganisation Microsoft 365 klientorganisation](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

Varje steg beskriver distributionsalternativ, sammanfattar resultaten och uppgifter för löpande underhåll.

I Contoso-fallstudien finns information om hur en fiktiv men representativt multinationell organisation distribuerade elementen i deras [Microsoft 365 klientorganisation.](../enterprise/contoso-case-study.md)
