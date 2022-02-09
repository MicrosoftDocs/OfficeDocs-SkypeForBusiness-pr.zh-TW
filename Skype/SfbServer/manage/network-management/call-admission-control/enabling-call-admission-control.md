---
title: 啟用通話許可控制
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: " 將通話許可控制設定 (CAC) 網路之後，您必須啟用 CAC 以強制執行頻寬限制。"
ms.openlocfilehash: 4a61fbb9587469c483f95e544bf168fe8dec4ab7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410766"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用通話許可控制

通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。 在您設定 CAC 網路之後，您必須啟用 CAC 以強制實施頻寬限制。 您可以使用商務用 Skype Server 控制台執行這項作業。


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>從商務用 Skype Server 控制台啟用 CAC

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **通用**]。

4.  在 **[全域]** 頁面上，按一下 **[全域]** 設定。
   
    > [!NOTE]  
    > 任何商務用 Skype Server 部署只能設定一個網路，所以清單中永遠不會有一個以上的網路設定。 您無法重新命名 [全域] 設定。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 **[編輯通用設定]** 頁面上，選取 **[啟用通話許可控制]** 核取方塊，然後按一下 **[認可]**。

當您按一下 **[認可]** 時，便會執行設定的測試。**[編輯通用設定]** 對話方塊隨即關閉，您會回到 **[全域]** 頁面。如果在網路設定中發現任何會使網路無法正常運作 (例如，每個區域未透過區域間路由彼此連線) 的錯誤或不一致情形，您將會收到警告。

如果您變更了網路設定，您可以開啟 [全域] 設定並按一下 **[認可]**，再次執行驗證檢查。您不需要先停用 CAC：使核取方塊保持已勾選狀態並按一下 **[認可]**。您可以隨時這麼做，而不需進行任何設定變更。

## <a name="see-also"></a>另請參閱

[規劃通話許可控制](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[設定通話許可控制](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](/powershell/module/skype/Get-CsNetworkConfiguration)  

[CsNetworkConfiguration](/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](/powershell/module/skype/Remove-CsNetworkConfiguration)