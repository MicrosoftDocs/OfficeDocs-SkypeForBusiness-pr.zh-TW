---
title: Skype 會議室系統網域加入考慮
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 若要瞭解如何將 Skype 會議室系統裝置電腦加入您的網域，請閱讀本主題。
ms.openlocfilehash: b34161f946b2c79508555145635445214159bd61
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003513"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype 會議室系統網域加入考慮
 
若要瞭解如何將 Skype 會議室系統裝置電腦加入您的網域，請閱讀本主題。
  
## <a name="domain-joining-considerations"></a>網域加入考慮

您可以將 Skype 會議室系統裝置電腦加入 Active Directory 網域，或將其留在工作組中。 在進行這項決策前，請先考慮下列幾點：
  
- 網域-加入 Skype 會議室系統裝置電腦可協助您自動匯入貴組織的私人根憑證鏈。
    
- [網域-加入 Skype 會議室系統裝置電腦] 可讓您授與網域使用者和群組的管理許可權。 如此一來，您就不需要記住本機電腦層級的系統管理員帳戶密碼。
    
- 當您將 Skype 會議室系統裝置電腦加入網域時，必須建立個別的組織單位（OU），這樣您才能將群組原則物件（GPO）排除專案提供給所有 Skype 會議室系統電腦物件所在的 OU。 當您這麼做時，請先在 OU 中建立電腦物件，然後再將 Skype 會議室系統裝置電腦加入網域。
    
- 許多組織都有下列 Gpo，這些 Gpo 會影響 Skype 室系統裝置的電腦功能。 請確定您覆寫或封鎖 Skype 會議室系統 OU 中這些 Gpo 的繼承： 
    
  - 登入會話超時（自動封鎖）
    
  - 與電源管理相關的原則
    
  - 需要其他驗證步驟
    
  - 拒絕存取本機磁片磁碟機
    
  - 提示使用者進行緩慢的網路連線
    
  - 在登入時啟動特定程式
    
  - 在所有加入網域的電腦上建立另一個網域使用者帳戶。
    
  - 將 Windows 更新推送至 Skype 會議室系統
    
- 或者，您也可以決定將裝置電腦留在工作組中。 就像桌面商務用 Skype 用戶端一樣，這需要您手動匯入 Skype 會議室 System 裝置電腦上的根憑證鏈。 如果您的商務用 Skype 部署是使用公用憑證（例如，Entrust、VeriSign 等），就不需要匯入根憑證鏈。 
    
如果您打算將 Skype 會議室系統電腦加入網域，以避免將 Skype 會議室系統電腦不小心加入非預期的 OU （可能無法從 Gpo 中移除），請確認您加入正確的 OU。 您可以使用來自 Skype 聊天室系統電腦的下列 Cmdlet，在正確的 OU 中加入，且不會收到可能會封鎖 LRS 功能的 Gpo。 請與您的系統管理員或 OEM 合作夥伴，以執行這些 Cmdlet：
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

即使您建立個別的 OU 和封鎖繼承，仍有一些原則可能會造成較高層面的問題。 沒有 [覆寫] 設定的群組原則會使用 [封鎖原則繼承] 設定來擊敗 OU。 如需詳細資訊，請參閱在群組原則檔中與[封鎖原則繼承](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))一文中的「不改寫」。
  
您可能有多種方法可以解決這些問題。 我們建議您與 Active Directory 專家協商，以確保您有提供適當 GPO 設定的 OU，或至少有先前描述之原則不存在的 OU。 建議啟用 Skype 會議室系統裝置的服務品質（QoS）。

## <a name="see-also"></a>另請參閱
  
[裝置組態：建立新的或編輯現有組態](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[管理服務品質](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
