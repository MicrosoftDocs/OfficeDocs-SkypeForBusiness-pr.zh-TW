---
title: 在 Office 365 中預配 Skype 會議室系統帳戶
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 請閱讀本主題，以瞭解如何在 Office 365 中預配 Skype 室系統帳戶。
ms.openlocfilehash: 33c3acf2f0fffc69da55468e8c16902ec7fa4f88
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768746"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>在 Office 365 中預配 Skype 會議室系統帳戶
 
請閱讀本主題，以瞭解如何在 Office 365 中預配 Skype 室系統帳戶。
  
下節涵蓋 Office 365 租使用者的 Skype 會議室系統帳戶配置。
  
## <a name="office-365-prerequisites"></a>Office 365 先決條件

您的線上租使用者必須符合下列需求：
  
- Office 365 方案必須包含商務用 Skype Online 方案2，或 Office 365 E1、E3 或 E5。 <br/>如需商務用 Skype Online 方案的詳細資料，請參閱[商務用 Skype Online 服務說明](https://technet.microsoft.com/library/jj822172.aspx)。
    
- 您的租使用者必須具備啟用商務用 Skype 的會議功能。
    
- 您的租使用者必須啟用 Exchange Online。 
    
- 您的租使用者遠端系統管理員必須具備下列 PowerShell 存取權：
    
  - Exchange 遠端 PowerShell 存取
    
  - 商務用 Skype Online 遠端 PowerShell 存取
    
  - 適用于 Windows PowerShell 的 windows Azure Active Directory 模組以存取 Office 365 目錄存取權
    
若是 Skype 室帳戶，則需要下列授權：
  
- 需要商務用 Skype Online 方案2或 Office 365 E1 或 E3 授權，才能啟用 Skype 會議。
    
- 若要使用企業語音功能 entitle 會議室，讓會議室可以使用電話號碼來啟用，必須有手機系統授權或 Office 365 E5 的商務用 Skype Online 方案2（1）。
    
- 如果您需要來自會議的撥入功能，您將需要音訊會議和電話系統授權。  如果您需要來自會議的撥出功能，您需要國內或國內和國際通話方案。 
    
- Skype 室帳戶不需要 Exchange Online 授權，因為應該將帳戶設定為資源信箱帳戶。
    
## <a name="provisioning-overview"></a>提供概覽

下圖提供 Office 365 中 Skype 室系統帳戶置備流程的概覽。
  
![O365 版 Skype 會議室系統的提供步驟](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>找出新的會議室

您可能已經在 Exchange 中有一個資源室信箱提供排程功能，或者您可能會在第一次建立資源信箱來協助 Skype 室系統部署。 在任何情況下，您都必須找出要在租使用者中使用的聊天室帳戶。 Exchange Online 的 [設定] 和 [商務用 Skype] 設定區段提供這兩種帳戶的指導方針。 例如，假設您有下列兩個房間，而您想要為兩者部署 Skype 室系統：
  
- 現有的資源信箱帳戶： confrm1@contoso.onmicrosoft.com
    
- 新的資源信箱帳戶： confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online 配

首先，請依照主題中的[[連線至 Exchange Online Powershell]](https://go.microsoft.com/fwlink/p/?LinkId=396554)中的指示，連線至 Exchange online powershell。
  
若要為 Skype 會議室系統設定現有的資源會議室信箱帳戶，請在 Exchange Online PowerShell 中執行下列命令：
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

若要為 Skype 會議室系統建立新的 Exchange 資源信箱帳戶，請在 Exchange Online PowerShell 中執行下列命令：
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

先前的命令會啟用帳戶，為 Skype 室系統使用量設定或建立新的 Exchange 資源信箱帳戶。
  
建立信箱之後，您可以在 Exchange Online PowerShell 中使用 CalendarProcessing Cmdlet 來設定信箱。 如需詳細資訊，請參閱單一目錄林內部部署的步驟3到6

## <a name="assigning-a-skype-for-business-online-license"></a>指派商務用 Skype Online 授權

現在，您可以使用 Office 365 系統管理入口網站（如[指派或移除商務用 office 365](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)或[商務用 skype 附加元件授權](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)）中所述的步驟，將商務用 skype online （方案2）或商務用 skype online （方案3）授權指派給您。 
  
在您指派商務用 Skype Online 的授權之後，您就可以登入並驗證該帳戶是使用任何商務用 Skype 用戶端。
  
## <a name="skype-for-business-online-provisioning"></a>商務用 Skype Online 的提供

如先前所示建立並啟用資源室信箱帳戶之後，且您已取得商務用 Skype Online 帳戶的授權，帳戶將會從 Exchange Online 林同步處理到商務用 Skype Online 樹林，方法是使用Windows Azure Active Directory 林。 若要在商務用 Skype Online 池中預配 Skype 室系統帳戶，必須執行下列步驟。 針對現有的資源信箱帳戶或新建立的帳戶（confrm1 或 confrm2），這些步驟都是相同的，因為 Exchange Online 中啟用這兩個帳戶後，就能以同樣的方式同步處理到商務用 Skype Online：
  
1. 建立遠端 PowerShell 會話。 請注意，您需要下載商務用 Skype Online 連接器模組與 Microsoft Online Services 登入小幫手，並確認您的電腦已設定。 如需詳細資訊，請參閱[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. 若要啟用商務用 Skype 的 Skype 會議室系統帳戶，請執行下列命令：
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    您可以使用下列命令來傳回這個屬性，以取得商務用 Skype 使用者從您現有的帳戶中駐留的 RegistrarPool 位址：
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Skype 室系統帳戶不支援多重要素驗證（MFA）。 

## <a name="password-expiration"></a>密碼到期日

在 Office 365 中，除非您設定不同的密碼過期原則，否則所有使用者帳戶的預設密碼過期原則都會是90天。 若是 Skype 室系統帳戶，您可以使用下列步驟選取 [密碼永不過期] 設定。
  
1. 使用您的租使用者全域系統管理員認證建立 Windows Azure Active Directory 會話。
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 針對先前使用下列命令建立的 Skype 會議室系統房間帳戶，設定 [密碼永不過期] 設定：
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

如需詳細資訊，請參閱[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  
## <a name="validate"></a>核實

針對驗證，您應該能夠使用任何商務用 Skype 用戶端登入您所建立的帳戶。

