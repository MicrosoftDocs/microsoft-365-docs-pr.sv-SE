---
title: Hög tillgänglighet federerad autentisering Fas 5 Konfigurera federerad autentisering för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: Sammanfattning Konfigurera Azure AD Connect för hög tillgänglighet federerad autentisering för Microsoft 365 i Microsoft Azure.
ms.openlocfilehash: 2bca2b758486b85d185870e2e14b495b8f084cb7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929414"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a>Fas 5 med hög tillgänglighet för federerad autentisering: Konfigurera federerad autentisering för Microsoft 365

I den här sista fasen av distributionen av federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure-infrastrukturtjänster får du och installerar ett certifikat som utfärdats av en offentlig certifikatutfärdare, verifierar din konfiguration och installerar och kör sedan Azure AD Connect på katalogsynkroniseringsservern. Azure AD Connect konfigurerar Microsoft 365-prenumerationen och AD FS-servrar (Active Directory Federation Services) och webbprogramproxyservrar för federerad autentisering.
  
Se [Distribuera hög tillgänglighet federerad autentisering för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a>Skaffa ett offentligt certifikat och kopiera det till katalogsynkroniseringsservern

Få ett digitalt certifikat från en offentlig certifikatutfärdare med följande egenskaper:
  
- Ett X.509-certifikat som passar för att skapa SSL-anslutningar.
    
- Den utökade egenskapen Subject Alternative Name (SAN) är inställd på federationstjänstens FQDN (exempel: fs.contoso.com).
    
- Certifikatet måste ha den privata nyckeln och lagras i PFX-format.
    
Dessutom måste datorerna och enheterna i organisationen lita på den offentliga certifikatutfärdare som utfärdar det digitala certifikatet. Det här förtroende upprättas genom att ha ett rotcertifikat från den offentliga certifikatutfärdaren som är installerat i arkivet med betrodda rotcertifikatutfärdare på dina datorer och enheter. Datorer med Microsoft Windows har vanligtvis en uppsättning av dessa typer av certifikat installerade från vanliga certifikatutfärdare. Om rotcertifikatet från din offentliga certifikatutfärdare inte redan är installerat måste du distribuera det till datorerna och enheterna i organisationen.
  
Mer information om certifikatkrav för federerad autentisering finns i Förutsättningar för installation och [konfiguration av federerad autentisering.](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration)
  
När du får certifikatet kopierar du det till en mapp på C:-enheten på katalogsynkroniseringsservern. Du kan till exempel ge filen namnet SSL.pfx och lagra den i mappen C: \\ Certs på katalogsynkroniseringsservern.
  
## <a name="verify-your-configuration"></a>Verifiera konfigurationen

Nu bör du vara redo att konfigurera Azure AD Connect och federerad autentisering för Microsoft 365. För att säkerställa att du är det finns här en checklista:
  
- Organisationens offentliga domän läggs till i Microsoft 365-prenumerationen.
    
- Din organisations Microsoft 365-användarkonton är konfigurerade för organisationens offentliga domännamn och kan logga in.
    
- Du har fastställt en FQDN för en federationstjänst baserat på ditt offentliga domännamn.
    
- En offentlig DNS A-post för federationstjänstens FQDN pekar på den offentliga IP-adressen för den Internetbaserade Azure-belastningsutjämaren för webbprogramproxyservrarna.
    
- En privat DNS A-post för federationstjänstens FQDN pekar på den privata IP-adressen för den interna Azure-belastningsutjämaren för AD FS-servrarna.
    
- En offentlig certifikatutfärdare är ett digitalt certifikat som passar för SSL-anslutningar med SAN-uppsättningen till federationstjänstens FQDN är en PFX-fil som lagras på din katalogsynkroniseringsserver.
    
- Rotcertifikatet för den offentliga certifikatutfärdaren installeras i arkivet Betrodda rotcertifikatutfärdare på dina datorer och enheter.
    
Här är ett exempel för Contoso-organisationen:
  
**En exempelkonfiguration för en infrastruktur för federerad autentisering med hög tillgänglighet i Azure**

![Ett exempel på en konfiguration av microsoft 365-infrastrukturen för federerad autentisering med hög tillgänglighet i Azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a>Kör Azure AD Connect för att konfigurera federerad autentisering

Verktyget Azure AD Connect konfigurerar AD FS-servrarna, webbprogramproxyservrarna och Microsoft 365 för federerad autentisering med följande steg:
  
1. Skapa en anslutning till fjärrskrivbord till katalogsynkroniseringsservern med ett domänkonto som har lokal administratörsbehörighet.
    
2. Öppna Internet Explorer på skrivbordet på katalogsynkroniseringsservern och gå till [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
3. På sidan **Microsoft Azure Active Directory Connect** klickar du på **Ladda** ned och sedan på **Kör**.
    
4. På sidan **Välkommen till Azure AD Connect** klickar du på Jag **godkänner** och klickar sedan på **Fortsätt.**
    
5. På sidan **Expressinställningar klickar** du på **Anpassa**.
    
6. Klicka på **Installera på sidan** Installera nödvändiga **komponenter.**
    
7. På sidan **Användarinloggning** klickar du på **Federation med AD FS** och sedan på **Nästa**.
    
8. På sidan **Anslut till Azure AD** anger du namn och lösenord för ett globalt administratörskonto för Microsoft 365-prenumerationen och klickar sedan på **Nästa.**
    
9. På  sidan Anslut dina kataloger ser du till att din lokala AD DS-skog (Active Directory Domain Services) är vald i **Skog,** skriver namn och lösenord för ett domänadministratörskonto, klickar på Lägg till katalog och klickar sedan på **Nästa.**
    
10. På sidan **Konfiguration av Azure AD-inloggning** klickar du på **Nästa.**
    
11. På sidan **Domän- och OU-filtrering** klickar du på **Nästa.**
    
12. På sidan **Unikt identifiera dina användare** klickar du på **Nästa.**
    
13. På sidan **Filtrera användare och enheter** klickar du på **Nästa.**
    
14. På sidan **Valfria funktioner** klickar du på **Nästa.**
    
15. På sidan **AD FS-servergrupp** klickar du på **Konfigurera en ny AD FS-servergrupp**.
    
16. Klicka **på** Bläddra och ange plats och namn för SSL-certifikatet från den offentliga certifikatutfärdaren.
    
17. När du uppmanas till det anger du certifikatlösenordet och klickar sedan på **OK.**
    
18. Kontrollera att **Ämnesnamn** och **Federationstjänstnamn** är inställda på federationstjänstens FQDN och klicka sedan på **Nästa.**
    
19. På **sidan AD FS-servrar** skriver du den första AD FS-serverns namn (tabell M - objekt 4 – namnkolumn för virtuell dator) och klickar sedan på **Lägg till**.
    
20. Skriv namnet på den andra AD FS-servern (tabell M - objekt 5 – namnkolumn för virtuell dator), klicka på Lägg till och klicka sedan på **Nästa.**
    
21. På sidan **Proxyservrar** för webbprogram skriver du det första webbprogrammets proxyservernamn (tabell M - objekt 6 – namnkolumn för virtuell dator) och klickar sedan på **Lägg till**.
    
22. Skriv namnet på proxyservern för det andra webbprogrammet (tabell M - objekt 7 – namnkolumn för virtuell dator), klicka på Lägg till och klicka sedan på **Nästa.**
    
23. På sidan **Autentiseringsuppgifter för domänadministratör** anger du användarnamn och lösenord för ett domänadministratörskonto och klickar sedan på **Nästa.**
    
24. På sidan **AD FS-tjänstkonto** anger du användarnamn och lösenord för ett företagsadministratörskonto och klickar sedan på **Nästa.**
    
25. Välj din **organisations DNS-domännamn** i **Domän** på sidan Azure AD Domain och klicka sedan på **Nästa.**
    
26. På sidan **Klart att konfigurera** klickar du på **Installera**.
    
27. På sidan **Installationen är slutförd** klickar du på **Verifiera**. Du bör se två meddelanden som anger att både intranätet och Internetkonfigurationen har verifierats.
    
  - Intranätmeddelandet ska lista den privata IP-adressen för dina interna Azure-belastningsutjämnare för AD FS-servrarna.
    
  - Internetmeddelandet ska lista den offentliga IP-adressen för din Azure-belastningsutjämnare för dina proxyservrar för webbprogram.
    
28. På sidan **Installationen är slutförd** klickar du på **Avsluta**.
    
Här är den slutliga konfigurationen, med platshållarnamn för servrarna.
  
**Fas 5: Den slutliga konfigurationen av en infrastruktur för federerad autentisering med hög tillgänglighet i Azure**

![Den slutliga konfigurationen av microsoft 365-infrastrukturen för federerad autentisering med hög tillgänglighet i Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Din hög tillgänglighetsinfrastruktur för federerad autentisering för Microsoft 365 i Azure är klar.
  
## <a name="see-also"></a>Se även

[Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federerad identitet för din Utvecklings-/testmiljö för Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365-lösning och arkitekturcenter](../solutions/index.yml)

[Federerad identitet för Microsoft 365](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)