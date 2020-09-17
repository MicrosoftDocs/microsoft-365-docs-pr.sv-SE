---
title: Integrera ServiceNow biljetter i säkerhets Center och Compliance Center för Microsoft 365
description: Lär dig hur du skapar och spårar biljetter i ServiceNow från säkerhets Center och Center för Microsoft 365.
keywords: säkerhet, Microsoft 365, M365, efterlevnad, Compliance Center, säkerhets Center, ServiceNow, biljetter, uppgifter, snö, anslutning
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: b9e900baf02e9fc866fe6fe520ad1e40ccd565de
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950706"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>Integrera ServiceNow biljetter i säkerhets Center och Compliance Center för Microsoft 365

[!include[Prerelease information](../includes/prerelease.md)]

ServiceNow är en populär plattform för moln datorer som hjälper företag att hantera digitala arbets flöden för företag. Deras plattform har arbets flöden, arbets flöden och kund arbets flöden. [Lär dig mer om ServiceNow](https://www.servicenow.com/)

Microsoft samarbetar med ServiceNow för att göra det lättare för IT-administratörer att hantera sina biljetter och uppgifter på båda plattformarna. [Microsoft 365 säkerhets Center](overview-security-center.md) och [Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) förbättras med möjligheten att skapa och spåra biljetter i ServiceNow.

- [**Hantera ServiceNow biljetter i säkerhets Center**](tickets-security-center.md)
- **Hantera ServiceNow biljetter i överensstämmelse Center** (kommer snart)

## <a name="prerequisites"></a>Förutsättningar

Åtkomst till Microsoft 365 säkerhets Center eller Compliance Center och en ServiceNow-instans med:  

* Kingston eller senare version
* Ha administratörs behörighet
* Ha administratörs behörighet för din mål leverantörs instans

ServiceNow rekommenderar att användarna behåller standardinställningarna i din ServiceNow-förekomst. Det kan orsaka fel när du har anpassat installations check lista och integrering med Microsoft 365 Security Center.

## <a name="data-exchange"></a>Data Exchange

När du ansluter Microsoft 365 säkerhets Center eller Compliance Center till ServiceNow, får Microsoft följande ytterligare data:

* ServiceNow instans namn
* ServiceNow klient-ID
* ServiceNow klient hemlighet
* ServiceNow åtkomst & uppdaterings-token

När du skapar en ServiceNow-biljett från Microsoft 365 Security Center eller Compliance Center skickas följande data till ServiceNow:

* Användar-ID som initierar biljett skapandet
* Aktivitets namn
* Beskrivning av uppgift
* Priority
* Förfallo datum
* Rekommendations källa (användar rekommendation eller Microsoft-rekommendation)
* Rekommendations kategori (enheter, data, appar, identitet, infrastruktur)

## <a name="connect-to-servicenow"></a>Anslut till ServiceNow

Gå till [skapa och spåra ServiceNow biljetter i Microsoft 365 säkerhets Center](tickets-security-center.md) för att lära dig hur du ansluter till ServiceNow. Att ansluta från Microsoft 365 Compliance Center kommer snart.

## <a name="troubleshooting"></a>Felsökning

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>Du får ett fel meddelande i det första steget i installations check listan (OAuth-skapande)

**Fel meddelande**: Läs åtgärd mot ' oauth_entity ' från omfattning ' x_mioms_m365ticket ' har nekats på grund av tabellens åtkomst policy för kors omfånget

Programmet förutsätter att en administratör på ServiceNow-instansen kan skapa och läsa OAuth-enheter. Det här felet kan orsakas av en anpassning i din instans av ServiceNow som begränsar vem som kan skapa eller läsa OAuth-enheter.

**ServiceNow rekommenderar att användarna behåller standardinställningarna.**

Ange konfigureringen av tabellen "program register" till standard:

* Label = program register
* Namn = oauth_entity
* Tillgänglig från = alla program omfattningar
* Kryss rutan kan läsa = markerad

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Verifiera den OAuth-enhet som har skapats för Microsoft 365 Security & Compliance Connector

Gå till tabellen program register (**meny > systemet OAuth > program register**) i ServiceNow. Hitta den OAuth-enhet som skapades av dig, med det namn som du har tilldelat den.

### <a name="signing-in-as-the-integration-user"></a>Logga in som integrations användare

Innan du godkänner anslutningen mellan Microsoft 365 säkerhets Center och ServiceNow bör du kontrol lera att du använder användar inloggning och lösen ord som du skapade i installations stegen. Använd inte dina personliga autentiseringsuppgifter.

1. Gå till sidan verifiering i ServiceNow.
2. Om du är inloggad med dina personliga autentiseringsuppgifter väljer **du länken inte** i det övre högra hörnet.
3. Logga in på ServiceNow som integrations användaren som du skapade tidigare från check lista för installation.  
4. Välj **Tillåt** på ServiceNow-sidan som frågar om säkerhet + kompatibilitetskontrollen kan ansluta till ditt ServiceNow-konto.
5. Fortsätt med konfigurations stegen.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Så här verifierar du integrations användaren som har skapats med check lista för installation för Microsoft 365 Security & Compliance Connector

Gå till tabellen användare **(meny > användar Administration > användare**) i ServiceNow och leta reda på den integrations användare som du har skapat, med det namn som du har tilldelat.

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>Ditt företag har en enkel inloggning som hindrar dig från att ansluta till ServiceNow via Microsoft 365 säkerhets Center

Om ditt företag har aktiverat enkel inloggning och du får ett fel meddelande eller att inloggningen Miss lyckas följer du en av de två lösningarna.

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a>Logga in på ServiceNow som integrations användare

1. Gå tillbaka till sidan för auktorisering i ServiceNow.
2. Markera länken **inte** i det övre högra hörnet.
3. Logga in på ServiceNow som integrations användaren som du skapade tidigare från check lista för installation.  
4. Välj **Tillåt** på ServiceNow-sidan som frågar om säkerhet + kompatibilitetskontrollen kan ansluta till ditt ServiceNow-konto.
5. Fortsätt med konfigurations stegen.

#### <a name="create-a-security-admin-user"></a>Skapa en säkerhets administratörs användare

1. Skapa en användare med administratörs privilegier i Azure Active Directory. Användaren måste ha samma namn och e-postadress som integrations användaren som du skapade från check lista för installation. Du kan ta bort rollen som säkerhets administratör när inloggningen är klar.
2. Logga in på Microsoft 365 säkerhets Center som användare och följ anvisningarna nedan.

### <a name="ip-filtering"></a>IP-filtrering

Om du har aktiverat IP-filtrering kan du behöva uttryckligen tillåta IP-adresser. Se [åtkomst kontroll för IP-adresser](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) för information om hur du tillåter IP-intervall i ServiceNow. Se [Azure IP-adressintervall och service märken-offentliga moln](https://www.microsoft.com/en-us/download/details.aspx?id=56519) för en lista med IP-adresser att tillåta.

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>Installationen är klar men inte biljetter och kan inte dela

Om installations-och konfigurations stegen har genomförts men du inte ser ServiceNow-korten på Start sidan och inte kan dela till ServiceNow från Microsofts säkra Poäng kan du kontrol lera status för etablerings sidan på https://security.microsoft.com/ticketProvisioning . Välj **Godkänn** och gå tillbaka till start sidan. Korten ska visas.

## <a name="resources"></a>Resurser

- [Hantera ServiceNow biljetter i säkerhets Center](tickets-security-center.md)