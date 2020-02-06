---
title: 啟用呼叫許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " 在您設定 [呼叫許可控制（CAC）] 網路之後，您必須啟用 CAC 來強制執行頻寬限制。"
ms.openlocfilehash: 4f9f3f09f943b417ec589f26dc5c6505d30831f9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817532"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用通話許可控制

通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。 在您設定 CAC 網路之後，您必須啟用 CAC 來強制執行頻寬限制。 您可以使用商務用 Skype Server 的 [控制台] 來執行這項作業。


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>若要從商務用 Skype Server 的 [控制台] 啟用 CAC

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**全域**]。

4.  在 [**全域**] 頁面上，按一下 [**全域**配置]。
   
    > [!NOTE]  
    > 您只能針對任何商務用 Skype Server 部署設定一個網路，因此清單中永遠不會有一個以上的網路設定。 您無法重新命名全域配置。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯全域設定**] 頁面上，選取 [**啟用通話許可控制**] 核取方塊，然後按一下 [**確認**]。

當您按一下 [**提交**] 時，就會執行設定測試。 [**編輯全域設定**] 對話方塊隨即關閉，並返回 [**全域**] 頁面。 如果您的網路設定中發現任何錯誤或不一致，都將會收到警告，避免它無法正常運作（例如，如果每個地區都未透過 interregion 路線連線到其他所有區域）。

如果您對網路設定進行變更，您可以開啟 [全域設定] 並按一下 [ **Commit**]，再次執行驗證檢查。 您不需要先停用 CAC，請選取核取方塊，然後按一下 [ **Commit**] （確認）。 您可以隨時執行此動作，而不需變更任何設定。

## <a name="see-also"></a>請參閱

[規劃通話許可控制](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[設定通話許可控制](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[移除-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
