---
title: 在 Microsoft 365 和 Office 365 中布建 Skype 會議室系統帳戶
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 閱讀此主題以瞭解如何在 Microsoft 365 或 Office 365 中布建 Skype 會議室系統帳戶。
ms.openlocfilehash: 1f4262453735baa08e16e7da03909e48ef12f4ff
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758115"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>在 Microsoft 365 和 Office 365 中布建 Skype 會議室系統帳戶
 
閱讀此主題以瞭解如何在 Microsoft 365 或 Office 365 中布建 Skype 會議室系統帳戶。
  
下列章節涵蓋 Skype 會議室系統帳戶布建。
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365 和 Office 365 必要條件

您的線上租使用者必須符合下列需求：
  
- Microsoft 365 或 Office 365 計畫必須包含商務用 Skype 線上方案2或 Office 365 E1、E3 或 E5。 <br/>如需商務用 Skype 線上方案的詳細資訊，請參閱[商務用 Skype 線上服務說明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。
    
- 您的租使用者必須啟用商務用 Skype 的會議功能。
    
- 您的租使用者必須啟用 Exchange Online。 
    
- 您的承租人遠端系統管理員必須具備下列 PowerShell 存取權：
    
  - Exchange遠端 PowerShell 存取
    
  - 商務用 Skype線上遠端 PowerShell 存取
    
  - Windows PowerShell 存取 Microsoft 365 或 Office 365 目錄存取的 Windows Azure Active Directory 模組
    
若為 Skype 的會議室帳戶，需要下列授權：
  
- 需要有商務用 Skype 線上方案2或 Office 365 E1 或 E3 授權，才能啟用 Skype 會議。
    
- 若要使用企業語音功能來 entitle 會議室，以便使用電話號碼來啟用會議室，電話系統授權或 Office 365 E5 商務用 Skype 的線上方案2必須 (1) 。
    
- 如果您需要來自會議的撥入式功能，您需要語音會議和電話系統授權。  如果您需要從會議撥出的功能，您需要國內或國內和國際通話方案。 
    
- Skype 的聊天室帳戶不需要 Exchange Online 授權，因為帳戶應設定為資源信箱帳戶。
    
## <a name="provisioning-overview"></a>布建概述

下圖概要說明 Skype 的會議室系統帳戶布建流程。
  
![Skype會議室系統布建步驟。](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>識別新的會議室

您在提供排程功能的 Exchange 中，您可能已經有資源會議室信箱，或是您第一次建立資源信箱以促進 Skype 會議室系統部署。 在任何情況下，您都必須識別要在租使用者中使用的會議室帳戶。 「Exchange Online 布建」和「商務用 Skype 布」區段提供兩種帳戶的指引。 例如，假設您有下列兩個聊天室，而您想要為兩者部署 Skype 的會議室系統：
  
- 現有資源信箱帳戶： confrm1@contoso.onmicrosoft.com
    
- 新資源信箱帳戶： confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online 布配

首先，遵循主題中的指示，將 Exchange Online PowerShell 連接至，[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。
  
若要為 Skype 的會議室系統設定現有的資源會議室信箱帳戶，請在 Exchange Online 中執行下列命令 PowerShell:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

若要在 Skype 會議室系統中建立新的 Exchange 資源信箱帳戶，請在 Exchange Online 中執行下列命令 PowerShell:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

先前的命令會設定或建立新的 Exchange 資源信箱帳戶，以供您啟用帳戶 Skype 會議室系統使用量。
  
在建立信箱之後，您可以在 Exchange Online PowerShell 中使用 Set-CalendarProcessing Cmdlet 來設定信箱。 如需詳細資訊，請參閱單一樹系內部部署的步驟3到6。

## <a name="assigning-a-skype-for-business-online-license"></a>指派商務用 Skype 線上授權

現在，您可以使用 (的管理入口網站（如[指派或移除) for Business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)或[Microsoft 365 附加元件授權](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)中所述），將商務用 Skype online (plan 2) 或商務用 Skype 線上 Microsoft 365 plan 3 商務用 Skype 授權。 
  
在您將商務用 Skype 的授權指派給線上後，您就可以使用任何商務用 Skype 用戶端，登入並驗證帳戶是否為作用中。
  
## <a name="skype-for-business-online-provisioning"></a>商務用 Skype線上布建

如先前所示建立及啟用 resource 會議室信箱帳戶後，且您已取得商務用 Skype 帳戶的授權。該帳戶會從 Exchange Online 樹系同步處理至商務用 Skype Online 樹系使用 Windows Azure Active Directory森林。 若要在商務用 Skype Online 集區中布建 Skype 的會議室系統帳戶，必須執行下列步驟。 針對現有資源信箱帳戶或新建立的帳戶 (confrm1 或 confrm2) ，這些步驟都相同，因為在 Exchange Online 中啟用這些帳戶後，這兩個帳戶會以相同方式同步處理至商務用 Skype Online：
  
1. 建立遠端 PowerShell 會話。 請注意，您必須下載[Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. 若要為商務用 Skype 啟用 Skype 的會議室系統帳戶，請執行下列命令：
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    您可以使用下列命令來傳回此屬性，以取得商務用 Skype 使用者所在的現有帳戶的 RegistrarPool 位址：
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Skype 的會議室系統帳戶不支援 Multi-Factor 驗證 (MFA) 。 

## <a name="password-expiration"></a>密碼過期

在 Microsoft 365 或 Office 365 中，所有使用者帳戶的預設密碼到期原則都會是90天，除非您設定不同的密碼到期原則。 若為 Skype 的會議室系統帳戶，您可以使用下列步驟，選取 [密碼永不到期] 設定。
  
1. 使用您的承租人全域系統管理員認證建立 Windows Azure Active Directory 會話。
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 使用下列命令，為先前建立的 Skype 聊天室系統室帳戶設定密碼永不過期設定：
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

如需詳細資訊，請參閱[設定 Windows PowerShell 的電腦](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
## <a name="validate"></a>驗證

針對驗證，您應該可以使用任何商務用 Skype 用戶端，登入您建立的帳戶。