---
title: Microsoft 365 identitetsmodeller och Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Lär dig hur du hanterar Azure AD-användaridentitetstjänsten i Microsoft 365 med endast moln- eller hybrididentitetsmodeller.
ms.openlocfilehash: 93a37f39a4d96d7c2e434ed6edf4df588e672a0f
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228501"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365 identitetsmodeller och Azure Active Directory

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft 365 använder Azure Active Directory (Azure AD), en molnbaserad användaridentitets- och autentiseringstjänst som ingår i din Microsoft 365-prenumeration, för att hantera identiteter och autentisering för Microsoft 365. Att konfigurera din identitetsinfrastruktur på rätt sätt är viktigt för Microsoft 365 att hantera användarnas åtkomst och behörigheter för din organisation.

Innan du börjar kan du titta på den här videon för att få en översikt över identitetsmodeller och autentisering för Microsoft 365.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Ditt första planeringsval är den Microsoft 365 identitetsmodellen.

## <a name="microsoft-365-identity-models"></a>Microsoft 365 identitetsmodeller

För att kunna planera för användarkonton måste du först förstå de två identitetsmodellerna i Microsoft 365. Du kan endast underhålla organisationens identiteter i molnet, eller så kan du underhålla dina lokala AD DS-identiteter (Active Directory Domain Services) och använda dem för autentisering när användare använder Microsoft 365 molntjänster.

Här är de två typerna av identitet och deras bästa form och fördelar.

| Attribut | Identitet endast för molnet | Hybrididentitet |
|:-------|:-----|:-----|
| **Definition** | Användarkontot finns bara i Azure AD-klientorganisationen för Microsoft 365 prenumeration. | Användarkontot finns i AD DS och en kopia finns också i Azure AD-klientorganisationen för Microsoft 365 prenumeration. Användarkontot i Azure AD kan också innehålla en hashtaggad version av det redan hashtaggade lösenordet för AD DS-användarkontot. |
| **Hur Microsoft 365 autentiseringsuppgifter för användare** | Azure AD-klientorganisationen för Microsoft 365-prenumerationen utför autentiseringen med molnidentitetskontot. | Azure AD-klientorganisationen för Microsoft 365-prenumerationen hanterar antingen autentiseringsprocessen eller omdirigerar användaren till en annan identitetsleverantör. |
| **Bäst för** | Organisationer som inte har eller behöver en lokal AD DS. | Organisationer som använder AD DS eller en annan identitetsleverantör. |
| **Största förmånen** | Enkel att använda. Inga extra katalogverktyg eller servrar krävs. | Användarna kan använda samma autentiseringsuppgifter när de använder lokala eller molnbaserade resurser. |
||||

## <a name="cloud-only-identity"></a>Identitet endast för molnet

En identitet som bara är molnbaserad använder användarkonton som bara finns i Azure AD. Identitet endast i molnet används vanligtvis av små organisationer som inte har lokala servrar eller inte använder AD DS för att hantera lokala identiteter.

Här är de grundläggande komponenterna i identiteter som bara är molnbaserade.

![Grundläggande komponenter i identiteter med endast molnet](../media/about-microsoft-365-identity/cloud-only-identity.png)

Både lokala användare och fjärranvändare (online) använder sina Azure AD-användarkonton och lösenord för åtkomst Microsoft 365 molntjänster. Azure AD autentiserar användarautentiseringsuppgifter baserat på dess lagrade användarkonton och lösenord.

### <a name="administration"></a>Administration
Eftersom användarkonton endast lagras i Azure AD hanterar du molnidentiteter med verktyg som Administrationscenter för Microsoft 365 [och](../admin/add-users/index.yml) [Windows PowerShell.](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

## <a name="hybrid-identity"></a>Hybrididentitet

Hybrididentitet använder konton som har sitt ursprung i en lokal AD DS och har en kopia i Azure AD-klientorganisationen för en Microsoft 365-prenumeration. Men de flesta ändringar flödar bara på ett sätt. Ändringar som du gör i AD DS-användarkonton synkroniseras till deras kopia i Azure AD. Men ändringar som görs i molnbaserade konton i Azure AD, till exempel nya användarkonton, synkroniseras inte med AD DS.

Med Azure AD Anslut kontinuerlig kontosynkronisering. Den körs på en lokal server, söker efter ändringar i AD DS och vidarebefordrar ändringarna till Azure AD. Med Azure AD Anslut kan du filtrera vilka konton som synkroniseras och om du vill synkronisera en hash-version av användarlösenord, så kallad synkronisering av lösenordshashar (PHS).

När du implementerar hybrididentitet är din lokala AD DS den auktoritativa källan för kontoinformation. Det innebär att du oftast utför administrativa uppgifter lokalt, som sedan synkroniseras till Azure AD.

Här är komponenterna i hybrididentitet.

![Komponenter i hybrididentitet](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD-klientorganisationen har en kopia av AD DS-kontona. I den här konfigurationen autentiseras både lokala användare och fjärranvändare som öppnar Microsoft 365-molntjänster mot Azure AD.

> [!NOTE]
> Du måste alltid använda Azure AD Anslut för att synkronisera användarkonton för hybrididentitet. Du behöver de synkroniserade användarkontona i Azure AD för att utföra licenstilldelning och grupphantering, konfigurera behörigheter och andra administrativa uppgifter som omfattar användarkonton.

### <a name="administration"></a>Administration

Eftersom de ursprungliga och auktoritativa användarkontona lagras i den lokala AD DS hanterar du dina identiteter med samma verktyg som du hanterar dina AD DS.

Du använder inte tjänsten Administrationscenter för Microsoft 365 eller PowerShell för Microsoft 365 att hantera synkroniserade användarkonton i Azure AD.

## <a name="next-step"></a>Nästa steg

Om du behöver den molnbaserade identitetsmodellen kan du [gå till Molnidentitet.](cloud-only-identities.md)

Om du behöver hybrididentitetsmodellen kan du gå till [Hybrididentitet](plan-for-directory-synchronization.md).

## <a name="see-also"></a>Se även

[Microsoft 365 Enterprise översikt](microsoft-365-overview.md)
