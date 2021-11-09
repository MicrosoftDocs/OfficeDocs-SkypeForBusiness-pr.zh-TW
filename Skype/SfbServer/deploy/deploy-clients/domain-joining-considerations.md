---
title: Skype會議室系統網域加入考慮
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 閱讀此主題以瞭解如何將 Skype 的會議室系統裝置電腦加入您的網域。
ms.openlocfilehash: d3c94a4983bddb051bda29badf5c569eeef635a3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844866"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype會議室系統網域加入考慮
 
閱讀此主題以瞭解如何將 Skype 的會議室系統裝置電腦加入您的網域。
  
## <a name="domain-joining-considerations"></a>網域聯結考量

您可以將 Skype 的會議室系統裝置電腦加入至 Active Directory 網域，或將它保留在工作組中。 作出這項決策之前，請先考慮下列幾點：
  
- 網域加入 Skype 的會議室系統裝置電腦可協助您自動匯入組織的私人根憑證鏈。
    
- 網域-加入 Skype 室系統裝置電腦可讓您授與網域使用者和群組的管理許可權。 這樣一來，您就不需要記住本機電腦層級管理員帳戶密碼。
    
- 當您將 Skype 的會議室系統裝置電腦加入網域時，必須建立個別的組織單位 (OU) ，這樣您就可以在所有) 的會議室系統電腦物件所在的 OU 中提供群組原則物件 (GPO Skype 排除專案。 當您這麼做時，請先在 OU 中建立電腦物件，然後再將 Skype 的會議室系統裝置電腦加入網域。
    
- 許多組織都有下列 gpo，這會影響 Skype 房間系統裝置的電腦功能。 確定您覆寫或封鎖 Skype 聊天室系統中這些 gpo 的繼承性 OU: 
    
  - 登入會話的超時 (自動鎖定) 
    
  - 電源管理相關原則
    
  - 需要其他驗證步驟
    
  - 拒絕存取本機磁片磁碟機
    
  - 提示使用者輸入慢速網路連接
    
  - 登入時啟動特定程式
    
  - 在所有加入網域的機器上建立另一個網域使用者帳戶。
    
  - 將 Windows 更新推入 Skype 會議室系統
    
- 或者，您也可以決定在工作組中留下裝置電腦。 就像使用桌面商務用 Skype 用戶端一樣，這需要您在 Skype 室系統裝置電腦上手動匯入根憑證鏈。 如果您的商務用 Skype 部署使用的是公用憑證 (例如，Entrust、VeriSign 等) ，您就不需要匯入根憑證鏈。 
    
如果您打算將 Skype 的會議室系統機器加入網域，請避免無意中將 Skype 會議室系統機器加入非預期的 ou，而不是 gpo 中，請確定您加入正確的 ou。 您可以從 Skype 聊天室系統機器使用下列 Cmdlet，以加入正確的 OU，而且不會收到可能封鎖 LRS 功能的 gpo。 請與系統管理員或 OEM 合作夥伴聯繫，以執行下列 Cmdlet：
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

即使您建立個別的 OU 和封鎖繼承，有些原則也有可能導致較高等級的問題。 [不含覆寫的群組原則] 設定會勝過使用 [封鎖原則繼承] 設定的 OU。 如需詳細資訊，請參閱與群組原則檔中的 [封鎖原則繼承](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 一文中的「沒有覆寫」一文。
  
您可能會有多種方法可解決這些問題。 我們建議您與您的 Active Directory 專家協商，以確保您已在具有適當 GPO 設定的 OU 中提供，或是至少在先前描述的原則不存在的 OU 中提供。 建議您為 Skype 的會議室系統裝置啟用 [服務品質 (QoS) ]。

## <a name="see-also"></a>另請參閱
  
[裝置組態：建立新的或編輯現有組態](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[管理服務品質](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)