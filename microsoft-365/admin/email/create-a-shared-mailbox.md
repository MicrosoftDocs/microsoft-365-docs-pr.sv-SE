---
title: Skapa en delad postlåda
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: När en delad postlåda har skapats kan flera personer i verksamheten dela på ansvaret att läsa och svara på e-postmeddelanden som skickas till en adress.
ms.openlocfilehash: 35f1de41094c6bf3f806b3e8e01c0a67949c491e
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683253"
---
# <a name="create-a-shared-mailbox"></a>Skapa en delad postlåda 

> [!NOTE]
> Om din organisation använder en Exchange-hybridmiljö, använder du det lokala administrationscentret för Exchange när du skapar och hanterar delade postlådor. Se [Så här skapar du en delad postlåda i administrationscentret för Exchange](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)<br><br>
> Om du inte är säker på ifall du ska skapa en delad postlåda eller en Microsoft 365-grupp för Outlook, kan du läsa mer i [Jämföra grupper](../create-groups/compare-groups.md).  Observera att det för närvarande inte är möjligt att migrera en delad postlåda till en Microsoft 365-grupp. Om det är något som du vill kunna göra, kan du låta oss veta detta genom att [rösta här](https://go.microsoft.com/fwlink/?linkid=871518).

Det är enkelt att skapa en delad postlåda så att en grupp användare kan övervaka och skicka e-post från en gemensam e-postadress, exempelvis info@contoso.com. När en person i gruppen svarar på ett meddelande till den delade postlådan ser svarsmeddelandet ut att komma från den delade postlådan, inte från den enskilda användaren.

I delade postlådor finns en delad kalender. Många små företag tycker att det är praktiskt att ha en delad kalender där alla lägger in sina avtalade tider. Om det till exempel finns 3 personer som utför kundbesök kan de alla skriva in sina avtalade tider i den delade kalendern. Det är ett bra sätt att hålla alla informerade om var alla befinner sig.

Innan du skapar en delad postlåda bör du läsa [Om delade postlådor](about-shared-mailboxes.md) för att få mer information.

## <a name="create-a-shared-mailbox-and-add-members"></a>Skapa en delad postlåda och lägg till medlemmar
  
1. Logga in med ett globalt administratörskonto eller Exchange-administratörskonto. Om du får meddelandet ”**Du har inte behörighet att komma åt den här sidan eller utföra den här åtgärden**”, är du inte någon administratör. 

::: moniker range="o365-worldwide"

2. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

2. I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041) går du till sidan **Grupper** \> **Delade postlådor**.

::: moniker-end

::: moniker range="o365-21vianet"

2. I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627) går du till sidan **Grupper** \> **Delade postlådor**.

::: moniker-end
    
3. På sidan **Delade postlådor** väljer du **+ Lägg till en postlåda**. Ange ett namn på den delade postlådan. Guiden väljer sedan e-postadress, men du kan redigera den.
    
    ![Namnge den delade postlådan.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. Välj **Lägg till**. Det kan ta några minuter innan du kan lägga till medlemmar.

5. Under **Nästa steg** väljer du **Lägg till medlemmar i den här postlådan**. Medlemmarna är de personer som kan se inkommande e-post till den delade postlådan och utgående svar.

   ![Välj Lägg till medlemmar](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. Välj knappen **+Lägg till medlemmar**. Markera de personer som ska använda den delade postlådan och välj **Spara**.

   ![Tilldela medlemmar till den delade postlådan](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. Välj **Stäng**.

Du har en delad postlåda och den innehåller en delad kalender. Gå vidare till nästa steg: Blockera inloggning för den delade postlådans konto.

## <a name="which-permissions-should-you-use"></a>Vilken behörighet ska du välja?

Du kan använda följande behörigheter med en delad postlåda:

- **Fullständig åtkomst**: Med behörigheten Fullständig åtkomst kan användaren logga in till den delade postlådan och agera som ägare av postlådan. Efter åtkomst till den delade postlådan kan en användare skapa kalenderobjekt, läsa, visa, radera och ändra e-postmeddelanden och skapa uppgifter och kalenderkontakter. Men användare med behörigheten Fullständig åtkomst kan inte skicka e-post från den delade postlådan om de inte också har behörigheten Skicka som eller Skicka för.

- **Skicka som** Med behörigheten Skicka som kan användaren skicka e-post för den delade postlådans räkning. Till exempel, om Katerina loggar in på den delade postlådans marknadsavdelning och skickar ett e-postmeddelande, ser det ut som att marknadsavdelningen skickade e-postmeddelandet.

- **Skicka för**: Med behörigheten Skicka för kan användaren skicka e-post för den delade postlådans räkning. Till exempel, om John loggar in till den delade postlådan Reception byggnad 32 och skickar ett e-postmeddelande, kommer det att se ut som att e-postmeddelandet skickades av "John för Reception byggnad 32". Du kan inte använda EAC för att bevilja behörigheter för skicka på väg, du måste använda cmdlet **Set-Mailbox** med parametern _GrantSendonBehalf_.

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a>Använda EAC för att redigera delegering för delad postlåda

1. Öppna EAC och gå till **Mottagare** \> **Grupper**. Välj den delade postlådan och välj sedan **Redigera** ![redigeringsikon](../../media/ITPro-EAC-EditIcon.png).

2. Välj **delegering av postlåda**.

3. Om du vill bevilja eller ta bort full åtkomst och skicka som behörighet, välj **Lägg till** ![lägg till ikonen](../../media/ITPro-EAC-AddIcon.png) eller **ta bort** ![ta bort ikonen](../../media/ITPro-EAC-RemoveIcon.gif) och välj sedan de användare du vill ge behörighet till.

   > [!NOTE]
   > Med behörigheten Fullständig åtkomst kan användaren öppna postlådan samt skapa och ändra objekt i den. Med behörigheten Skicka som kan alla utöver postlådans ägare skicka e-post från den delade postlådan. Båda behörigheterna krävs för att den delade postlådan ska kunna hanteras.

4. Välj **Spara** för att spara ändringarna.


## <a name="block-sign-in-for-the-shared-mailbox-account"></a>Blockera inloggning för den delade postlådans konto

Alla delade postlådor har ett motsvarande användarkonto. Lade du märke till att du inte behövde ange något lösenord när du skapade den delade postlådan? Kontot har ett lösenord, men det genereras av systemet (okänt). Du ska inte använda kontot för att logga in på den delade postlådan.

Men vad händer om en administratör återställer lösenordet för den delade postlådans användarkonto? Eller om en angripare får åtkomst till kontoautentiseringsuppgifterna för den delade postlådan? Det skulle innebära att användarkontot kan logga in på den delade postlådan och skicka e-post. För att förhindra detta måste du blockera inloggningen för det konto som är kopplat till den delade postlådan.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.
::: moniker-end

1. Leta reda på kontot för den delade postlådan i listan med användarkonton (ändra t.ex. filtret till **Användare utan licens**).

1. Välj användaren för att öppna fönstret Egenskaper och välj sedan ikonen **Blockera den här användaren** ![Skärmbild av ikonen Blockera den här användaren](../../media/block-user-icon.png).

   **Obs**! Om kontot redan är blockerat visas **Inloggning blockerad** längst upp och ikonen är **Avblockera den här användaren**.

1. I fönstret **Blockera den här användaren?** väljer du **Blockera användaren från att logga in** och sedan **Spara ändringarna**.

Om du vill ha anvisningar om hur du blockerar inloggning för konton som använder Azure AD PowerShell (med flera konton samtidigt), kan du läsa [Blockera användarkonton med Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).

## <a name="add-the-shared-mailbox-to-outlook"></a>Lägga till den delade postlådan i Outlook

Om ditt företag har aktiverat automatisk mappning (det har de flesta som standard), visas den delade postlådan i användarnas Outlook-app automatiskt när de har stängt och startat om Outlook. 

Automatisk mappning är inställt på användarens postlåda, inte på den delade postlådan.   Det här innebär att automatisk mappning inte fungerar om du försöker använda säkerhetsgruppen för att hantera vem som har åtkomst till den delade postlådan. Om du vill använda automatisk mappning måste du uttryckligen tilldela behörigheter. Automatisk mappning är aktiverat som standard. Mer information om hur du inaktiverar funktionen finns i [Ta bort automatisk mappning för en delad postlåda](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).

Mer information om delade postlådor i Outlook finns i:

- <a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Öppna och använda en delad postlåda i Outlook</a>

- <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Lägga till en delad postlåda i Outlook på webben</a>

- <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Lägga till en delad postlåda i Outlook Mobile</a>

- <a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Öppna en delad mapp eller postlåda i Outlook för Mac</a>

- <a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Lägga till regler i en delad postlåda</a>

## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>Använda en delad postlåda på en mobil enhet (mobiltelefon eller surfplatta)

Du kan komma åt en delad postlåda på en mobil enhet på två sätt:
- Lägg till den delade postlådan i <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook för iOS-appen</a> eller <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook för Android-mobilappen</a>. 
    
    Anvisningar finns i <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Lägga till en delad postlåda i Outlook Mobile</a>.

- Öppna webbläsaren, logga in och gå sedan till Outlook på webben. Från Outlook på webben har du tillgång till den delade postlådan.

    Anvisningar finns i <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Lägga till en delad postlåda i Outlook på webben</a>.
    
> [!NOTE]
> Delad postlåda kan bara läggas till i Outlook för iOS-appen eller Outlook för Android-mobilappen

## <a name="use-the-shared-calendar"></a>Använda den delade kalendern

När du skapade den delade postlådan skapade du automatiskt en delad kalender. Vi föredrar den delade postlådekalendern framför en SharePoint-kalender när det handlar om att hålla koll på avtalade tider och var personer befinner sig. En delad kalender är integrerad med Outlook och den är mycket enklare att använda än en SharePoint-kalender.

1. Öppna kalendervyn i Outlook-appen och välj den delade postlådan.

2. Alla medlemmar i den delade postlådan ser avtalade tider som du lägger in. 

3. Alla medlemmar i den delade postlådan kan skapa, visa och hantera avtalade tider i kalendern på samma sätt som med privata avtalade tider. Alla som är medlemmar i en delad postlåda kan se sina ändringar i den delade kalendern.

## <a name="related-content"></a>Relaterat innehåll

[Om delade postlådor](about-shared-mailboxes.md) (artikel)\
[Konfigurera en delad postlåda](configure-a-shared-mailbox.md) (artikel)\
[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md) (artikel)\
[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md) (artikel)\
[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md) (artikel)