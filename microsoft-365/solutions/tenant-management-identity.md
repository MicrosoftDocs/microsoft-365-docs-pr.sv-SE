---
title: Steg 3. Identitet för Microsoft 365 för företag-klientorganisationen
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
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Distribuera rätt identitetsmodell för Microsoft 365-klientorganisationen och framtvinga starka användar inloggningar.
ms.openlocfilehash: 57e84b38715c4fbe29f9aa362e363663b0401f91
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052368"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>Steg 3. Identitet för Microsoft 365 för företag-klientorganisationen

Din Microsoft 365-klientorganisation inkluderar en Azure Active Directory-klientorganisation (Azure AD) för att hantera identiteter och autentisering för inloggningar. Att konfigurera identitetsinfrastrukturen på rätt sätt är viktigt för att hantera Microsoft 365-användares åtkomst och behörigheter för din organisation.

## <a name="cloud-only-vs-hybrid"></a>Endast molnet jämfört med hybrid

Här är de två typerna av identitetsmodeller och deras bästa form och fördelar.


| Modell | Beskrivning | Så här autentiserar Microsoft 365 användarautentiseringsuppgifter | Bäst för | Största förmånen |
|:-------|:-----|:-----|:-----|:-----|
| Endast molnet | Användarkontot finns bara i Azure AD-klientorganisationen för Microsoft 365-klienten. | Azure AD-klientorganisationen för Microsoft 365-klienten utför autentiseringen med molnidentitetskontot. | Organisationer som inte har eller behöver en lokal AD DS. | Enkel att använda. Inga extra katalogverktyg eller servrar krävs. |
| Hybrid |  Användarkontot finns i din lokala ACTIVE Directory Domain Services (AD DS) och en kopia finns också i Azure AD-klienten för Microsoft 365-klienten. Azure AD Connect körs på en lokal server för att synkronisera AD DS-ändringar i Din Azure AD-klient. Användarkontot i Azure AD kan också innehålla en hashtaggad version av det redan hashtaggade lösenordet för AD DS-användarkontot. | Azure AD-klientorganisationen för Microsoft 365-klienten hanterar antingen autentiseringsprocessen eller omdirigerar användaren till en annan identitetsleverantör. | Organisationer som använder AD DS eller en annan identitetsleverantör. | Användarna kan använda samma autentiseringsuppgifter när de använder lokala eller molnbaserade resurser. |
||||||

Här är de grundläggande komponenterna i identiteter som bara är molnbaserade.
 
![Grundläggande komponenter i identiteter med endast molnet](../media/about-microsoft-365-identity/cloud-only-identity.png)

I den här illustrationen loggar lokala användare och fjärranvändare in med konton i Azure AD-klientorganisationen för Sin Microsoft 365-klientorganisation.

Här är de grundläggande komponenterna i hybrididentitet.

![Grundläggande komponenter i hybrididentitet](../media/about-microsoft-365-identity/hybrid-identity.png)

I den här illustrationen loggar lokala användare och fjärranvändare in på sin Microsoft 365-klientorganisation med konton i Azure AD-klientorganisationen som har kopierats från deras lokala AD DS.

## <a name="synchronizing-your-on-premises-ad-ds"></a>Synkronisera din lokala AD DS

Beroende på dina affärsbehov och tekniska krav är hybrididentitetsmodellen och katalogsynkroniseringen det vanligaste valet för företagskunder som inför Microsoft 365. Med katalogsynkronisering kan du hantera identiteter i AD DS och alla uppdateringar av användarkonton, grupper och kontakter synkroniseras till Azure AD-klientorganisationen i Microsoft 365-klienten.

>[!Note]
>När AD DS-användarkonton synkroniseras för första gången tilldelas de inte automatiskt en Microsoft 365-licens och kan inte komma åt Microsoft 365-tjänster, till exempel e-post. Du måste först tilldela dem en användningsplats. Tilldela sedan en licens till dessa användarkonton, antingen individuellt eller dynamiskt genom gruppmedlemskap.
>

Här är de två typerna av autentisering när du använder hybrididentitetsmodellen.

| Autentiseringstyp | Beskrivning |
|:-------|:-----|
| Hanterad autentisering | Azure AD hanterar autentiseringsprocessen med hjälp av en lokalt lagrad hash-version av lösenordet eller skickar autentiseringsuppgifterna till en lokal programvaruagent som ska autentiseras av den lokala AD DS. <br> <br>  Det finns två typer av hanterad autentisering: synkronisering av lösenordshashar (PHS) och direktautentisering (PTA). Med PHS utför Azure AD själva autentiseringen. Med PTA har Azure AD AD DS för att utföra autentiseringen. |
| Federerad autentisering | Azure AD omdirigerar klientdatorn och begär autentisering till en annan identitetsleverantör. |
|  |  |

Mer [information finns i Välja rätt autentiseringsmetod.](/azure/active-directory/hybrid/choose-ad-authn)

## <a name="enforcing-strong-sign-ins"></a>Framtvinga starka inloggningar

För att öka säkerheten för användarens inloggningar använder du funktionerna i följande tabell.

| Funktion | Beskrivning | Mer information | Licenskrav |
|:-------|:-----|:-----|:-----|:-----|
| Windows Hello för företag | Ersätter lösenord med stark tvåfaktorautentisering när du loggar in på en Windows-enhet. De två faktorerna är en ny typ av användaruppgifter som är kopplade till en enhet och ett biometriskt attribut eller en PIN-kod. | [Översikt över Windows Hello för företag](/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 eller E5 |
| Azure AD-lösenordsskydd | Identifierar och blockerar kända svaga lösenord och deras varianter och kan även blockera ytterligare svaga termer som är specifika för din organisation. | [Konfigurera lösenordsskydd i Azure AD](/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 eller E5 |
| Använd multifaktorautentisering (MFA) | MFA kräver att användarens inloggningar måste verifieras mer än lösenordet för användarkontot, till exempel verifiering med en smartphone-app eller ett SMS som skickas till en smartphone. I [den här videon](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) finns instruktioner om hur användarna ställer in MFA. | [MFA för Microsoft 365 för företag](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 eller E5 |
| Konfigurationer av identiteter och enhetsåtkomst | Inställningar och principer som består av rekommenderade nödvändiga funktioner och deras inställningar i kombination med villkorsstyrd åtkomst, Intune och Azure AD Identity Protection-principer som bestämmer om en viss åtkomstbegäran ska beviljas och under vilka villkor.  | [Konfigurationer för identitets- och enhetsåtkomst](../security/defender-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 eller E5 |
| Azure AD Identity Protection | Skydda mot autentiseringsuppgifter, där en attack avgör en användares kontonamn och lösenord för att få åtkomst till en organisations molntjänster och data. | [Azure AD Identity Protection](/azure/active-directory/active-directory-identityprotection) | Microsoft 365 E5 eller Microsoft 365 E3 med tillägget & Identity & Threat Protection |
|  |  |  |



## <a name="results-of-step-3"></a>Resultat av steg 3

För identitet för Microsoft 365-klientorganisationen har du fastställt:

- Vilken identitetsmodell som ska användas.
- Hur du framtvingar stark användar- och enhetsåtkomst.

Här är ett exempel på en klientorganisation med de nya hybrididentitetselementen markerade.

![Exempel på hybrididentitet för en klientorganisation](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

I den här illustrationen har klientorganisationen:

- En AD DS-skog som synkroniseras med Azure AD-klientorganisationen med en DirSync-server och Azure AD Connect.
- En kopia av AD DS-användarkontona och andra objekt från AD DS-skogen.
- En uppsättning principer för villkorsstyrd åtkomst för att framtvinga säkra användar inloggningar och åtkomst baserat på användarkontot. 

## <a name="ongoing-maintenance-for-identity"></a>Löpande underhåll för identitet

Du kan behöva:

- Lägga till eller ändra användarkonton och grupper. När det gäller molnbaserad identitet behåller du dina molnbaserade användare och grupper med Azure AD-verktyg som administrationscentret för Microsoft 365 eller PowerShell. För hybrididentitet behåller du lokala användare och grupper med AD DS-verktyg.
- Lägg till eller ändra konfigurationen av identitets- och enhetsåtkomst för att tillämpa säkerhetskraven för inloggning.

## <a name="next-step"></a>Nästa steg

[![Steg 4. Migrera dina lokala Office-servrar och data](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

Fortsätt med [migrering](tenant-management-migration.md) för att migrera dina lokala Office-servrar och deras data till Microsoft 365.