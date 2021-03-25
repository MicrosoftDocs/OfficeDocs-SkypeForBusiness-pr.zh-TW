---
title: Skype 會議室系統網域加入考慮
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: 系統管理員可以瞭解如何將 Skype Room System 裝置電腦加入 Active Directory 網域，以及這麼做的考慮。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117551"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Skype 會議室系統網域加入考慮
 
請閱讀本主題，瞭解如何將 Skype Room System 裝置電腦加入您的網域。
  
## <a name="domain-joining-considerations"></a>網域加入考慮

您可以將 Skype Room System 裝置電腦加入 Active Directory 網域，或將它留在工作組中。 在做出此決策之前，請考慮下列各點：
  
- 網域加入 Skype Room System 裝置電腦可協助自動導入貴組織的專用根憑證鏈。
- 網域加入 Skype Room System 裝置電腦可讓您授予網域使用者和群組系統管理許可權。 如此一來，您就不需要記住本機電腦層級系統管理員帳戶密碼。
- 當您將 Skype Room System 裝置電腦加入網域時，您必須建立個別的組織單位 (OU) ，這樣您才能將群組原則物件 (GPO) 排除功能提供給所有 Skype 會議室系統電腦物件所在的 OU。 當您這麼做時，在加入 Skype Room System 裝置電腦至網域之前，先在 OU 中建立電腦物件。
- 許多組織都有下列 GPO，這會影響 Skype Room System 裝置 PC 功能。 確保您在 Skype 會議室系統 OU 中重寫或封鎖這些 GPO 的繼承：

  - 登入會話的超時 (自動鎖定) 
  - 與電源管理相關的政策
  - 需要其他驗證步驟
  - 拒絕存取本地磁片磁碟機
  - 提示使用者網路連接速度緩慢
  - 登入時啟動特定程式
  - 在所有加入網域的電腦上建立另一個網域使用者帳戶。
  - 將 Windows Update 推送到 Skype 會議室系統
    
- 或者，您可能會決定將裝置電腦留在工作組中。 與桌上出版 Microsoft Teams 或商務用 Skype 用戶端一樣，這要求您在 Skype Room System 裝置 PC 上手動導入根憑證鏈。 如果您的部署是使用公用憑證 (例如，委託、VeriSign 等等，則不需要將根憑證鏈) 。 
    
如果您打算將 Skype Room System 電腦加入網域，為了避免不小心將 Skype 會議室系統電腦加入非預期的 OU ，而此 OU 可能並非 GPO 所提供，請確定您加入正確的 OU。 您可以使用 Skype Room System 電腦中的下列 Cmdlet 加入正確的 OU，而且不會收到可能會封鎖 LRS 功能的 GPO。 請與您的系統管理員或 OEM 合作夥伴聯繫，以執行這些 Cmdlet：
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

即使您建立個別的 OU 和封鎖繼承，也有一些可能會導致較高層級的問題。 具有 No Override 設定的群組原則會以封鎖策略繼承設定比對 OU。 若要詳細資訊，請參閱群組原則檔中與封鎖 [策略繼承](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 比較的無重寫。
  
您可能有多種方法可以解決這些問題。 我們建議您諮詢 Active Directory 專家，以確保您獲得具有適當 GPO 設定的 OU，或至少提供不存在先前所述之策略的 OU。 我們建議您針對 Skype 會議室系統裝置啟用 QoS (QoS) 服務品質。

## <a name="related-topics"></a>相關主題
  
[裝置組態：建立新的或編輯現有組態](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[管理服務品質](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)