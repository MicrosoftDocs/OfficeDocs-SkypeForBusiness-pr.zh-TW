---
title: 管理網路頻寬原則設定檔
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 使用本文中的程式來查看、建立、修改或刪除網路頻寬原則設定檔。
ms.openlocfilehash: 47a4d268c24cd8d57c8aeda4deacc6b03e795c2c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096669"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>管理商務用 Skype Server 中的網路頻寬原則設定檔

使用本文中的程式來查看、建立、修改或刪除網路頻寬原則設定檔。

## <a name="view-network-bandwidth-policy-profile-information"></a>查看網路頻寬原則設定檔資訊

頻寬原則為通話許可控制 (CAC) 的一部分，用於定義某些形式的頻寬限制。 在商務用 Skype Server 中，只有音訊和影片形式可以獲指派頻寬限制。 您可以設定整體頻寬限制和工作階段限制。 您可以使用商務用 Skype Server 控制台建立、修改或刪除這些原則的容器設定檔。 每個頻寬原則設定檔可以與一或多個網路網站產生關聯。 請使用下列程式來查看頻寬原則設定檔。 

### <a name="to-view-a-bandwidth-policy-profile"></a>若要查看頻寬原則設定檔

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，按一下 **[網路設定]**，再按一下 **[頻寬原則]**。

4.  在 [ **頻寬原則** ] 頁面上，按一下您要查看的頻寬原則設定檔。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路頻寬原則設定檔資訊

您可以使用 Windows PowerShell 和 Get-CsNetworkBandwidthPolicyProfile Cmdlet 來查看網路頻寬設定檔。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>若要查看網路頻寬原則設定檔資訊

  - 若要查看所有網路頻寬原則設定檔的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsNetworkBandwidthPolicyProfile
    
    如此將傳回類似如下的資訊：
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


如需詳細資訊，請參閱 [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) Cmdlet 的 [說明] 主題。


## <a name="create-or-modify-bandwidth-policy-profiles"></a>建立或修改頻寬原則設定檔

頻寬原則為通話許可控制 (CAC) 的一部分，用於定義某些形式的頻寬限制。 在商務用 Skype Server 中，只有音訊和影片形式可以獲指派頻寬限制。 您可以設定整體頻寬限制和工作階段限制。 您可以使用商務用 Skype Server 控制台建立、修改或刪除這些原則的容器設定檔。 每個頻寬原則設定檔可以與一或多個網路網站產生關聯。 請使用下列程序來建立或修改頻寬原則設定檔。 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>若要建立新的頻寬原則設定檔

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **頻寬原則**]。

4.  在「頻寬原則」頁面上，按一下 [新增]。

5.  在 **[新增頻寬原則設定檔]** 的 **[名稱]** 欄位中輸入名稱。在所有頻寬原則設定檔中，此名稱必須是唯一的。

6.  在 **[音訊限制]** 欄位中輸入數值。此值是要配置給所有音訊連線的最大頻寬數量 (以 kbps 表示)。

7.  在 **[音訊工作階段限制]** 欄位中輸入數值。此值是要配置給個別音訊連線的最大頻寬數量 (以 kbps 表示)。此值必須為 40 或更大。

8.  在 **[視訊限制]** 欄位中輸入數值。此值是要配置給所有視訊連線的最大頻寬數量 (以 kbps 表示)。

9.  在 **[視訊工作階段限制]** 欄位中輸入數值。此值是要配置給個別視訊連線的最大頻寬數量 (以 kbps 表示)。此值必須為 100 或更大。

10. (選用) 在 **[描述]** 欄位中輸入值，以提供更多有關此頻寬原則設定檔 (無法單獨以名稱表示) 的資訊。

11. 按一下 **[認可]**。

    > [!NOTE]  
    > 建立新的頻寬原則設定檔並不會自動強制頻寬限制。 您必須先讓原則設定檔與網站產生關聯。 


### <a name="to-modify-a-bandwidth-policy-profile"></a>若要修改頻寬原則設定檔

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **頻寬原則**]。

4.  在「頻寬原則」頁面上，按一下您要修改的頻寬原則設定檔。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 [ **編輯頻寬原則設定檔** ] 頁面上，視需要修改欄位 (如需詳細資訊，請參閱 [建立新的頻寬原則設定檔](#to-create-a-new-bandwidth-policy-profile)) 。

7.  按一下 **[認可]**。

    > [!NOTE]  
    > 當您修改頻寬原則設定檔時，將會立即更新與此頻寬原則設定檔關聯的所有網路網站的頻寬限制。

  
## <a name="delete-network-bandwidth-policy-profiles"></a>刪除網路頻寬原則設定檔

頻寬原則為通話許可控制 (CAC) 的一部分，用於定義某些形式的頻寬限制。 在商務用 Skype Server 中，只有音訊和影片形式可以獲指派頻寬限制。 您可以設定整體頻寬限制和工作階段限制。 您可以使用商務用 Skype Server 控制台建立、修改或刪除這些原則的容器設定檔。 請使用下列程序來刪除網路頻寬原則設定檔。 

### <a name="to-delete-a-bandwidth-policy-profile"></a>刪除頻寬原則設定檔

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **頻寬原則**]。

4.  在 **[頻寬原則]** 頁面上，按一下您要刪除的頻寬原則設定檔。

    > [!NOTE]  
    > 您可以一次刪除一個以上的設定檔。若要這麼做，請按住 CTRL 鍵並同時選取多個設定檔。或者，若要選取所有設定檔，請按一下 **[編輯]** 功能表上的 **[全選]**。

5.  在 **[編輯]** 功能表上，按一下 **[刪除]**。
   

    > [!WARNING]  
    > 您無法刪除與網站關聯的頻寬原則設定檔。 您必須先移除與網站的關聯，才可以刪除設定檔。 


## <a name="see-also"></a>另請參閱

[管理網站的通話許可控制](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
