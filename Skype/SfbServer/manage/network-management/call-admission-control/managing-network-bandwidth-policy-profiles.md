---
title: 管理網路頻寬原則設定檔
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
description: 使用本文中的程式來查看、建立、修改或刪除網路頻寬原則設定檔。
ms.openlocfilehash: a9203c0935673e0dfd12d052876f06583c7c92c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817502"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>管理商務用 Skype Server 中的網路頻寬原則設定檔

使用本文中的程式來查看、建立、修改或刪除網路頻寬原則設定檔。

## <a name="view-network-bandwidth-policy-profile-information"></a>查看網路頻寬原則設定檔資訊

在呼叫許可控制（CAC）中，頻寬原則是用來定義特定形式的頻寬限制。 在商務用 Skype Server 中，只有音訊和視頻形式可以指派頻寬限制。 您可以設定整體頻寬限制及會話限制。 您可以使用商務用 Skype Server [控制台] 來建立、修改或刪除這些原則的容器設定檔。 每個頻寬原則設定檔都可以與一個或多個網路網站建立關聯。 使用下列程式來查看頻寬原則設定檔。 

### <a name="to-view-a-bandwidth-policy-profile"></a>若要查看頻寬原則設定檔

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。

4.  在 [**頻寬原則**] 頁面上，按一下您要查看的頻寬原則設定檔。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看網路頻寬原則設定檔資訊

您可以使用 Windows PowerShell 和 CsNetworkBandwidthPolicyProfile Cmdlet 來查看網路頻寬設定檔。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>若要查看網路頻寬原則設定檔資訊

  - 若要查看所有網路頻寬策略設定檔的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsNetworkBandwidthPolicyProfile
    
    這會傳回如下所示的資訊：
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


如需詳細資訊，請參閱[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) Cmdlet 的說明主題。


## <a name="create-or-modify-bandwidth-policy-profiles"></a>建立或修改頻寬原則設定檔

在呼叫許可控制（CAC）中，頻寬原則是用來定義特定形式的頻寬限制。 在商務用 Skype Server 中，只有音訊和視頻形式可以指派頻寬限制。 您可以設定整體頻寬限制及會話限制。 您可以使用商務用 Skype Server [控制台] 來建立、修改或刪除這些原則的容器設定檔。 每個頻寬原則設定檔都可以與一個或多個網路網站建立關聯。 使用下列程式來建立或修改頻寬原則設定檔。 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>建立新的頻寬原則設定檔

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。

4.  在 [**頻寬原則**] 頁面上，按一下 [**新增**]。

5.  在**新的頻寬原則設定檔**中，在 [**名稱**] 欄位中輸入名稱。 這個名稱在所有頻寬原則設定檔中都必須是唯一的。

6.  在 [**音訊限制**] 欄位中，輸入一個數值。 此值為所有音訊連線所要配置的最大頻寬量，以 kbps 表示。

7.  在 [**音訊會話限制**] 欄位中輸入一個數值。 此值為個別音訊連線所要配置的最大頻寬量，以 kbps 表示。 此值必須是40或更高版本。

8.  在 [**影片限制**] 欄位中輸入一個數值。 此值為所有視頻連線所要配置的最大頻寬量，以 kbps 表示。

9.  在 [**視頻會話限制**] 欄位中輸入一個數值。 此值為個別視頻連線所要配置的最大頻寬量，以 kbps 表示。 此值必須是100或更高版本。

10. 可選在**描述**欄位中輸入一個值，以提供此頻寬原則設定檔無法單獨表示的詳細資訊。

11. 按一下 [認可]****。

    > [!NOTE]  
    > 建立新的頻寬原則設定檔並不會自動強制執行頻寬限制。 您必須先將原則設定檔與網站建立關聯。 


### <a name="to-modify-a-bandwidth-policy-profile"></a>修改頻寬原則設定檔

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。

4.  在 [**頻寬原則**] 頁面上，按一下您要修改的頻寬原則設定檔。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯頻寬策略設定檔**] 頁面上，視需要修改欄位（如需詳細資訊，請參閱[建立新的頻寬原則設定檔](#to-create-a-new-bandwidth-policy-profile)）。

7.  按一下 [認可]****。

    > [!NOTE]  
    > 當您修改頻寬原則設定檔時，它會立即更新與此頻寬原則設定檔相關聯之所有網路網站的頻寬限制。

  
## <a name="delete-network-bandwidth-policy-profiles"></a>刪除網路頻寬原則設定檔

在呼叫許可控制（CAC）中，頻寬原則是用來定義特定形式的頻寬限制。 在商務用 Skype Server 中，只有音訊和視頻形式可以指派頻寬限制。 您可以設定整體頻寬限制及會話限制。 您可以使用商務用 Skype Server [控制台] 來建立、修改或刪除這些原則的容器設定檔。 使用下列程式刪除網路頻寬原則設定檔。 

### <a name="to-delete-a-bandwidth-policy-profile"></a>刪除頻寬原則設定檔

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。

4.  在 [**頻寬原則**] 頁面上，按一下您要刪除的頻寬原則設定檔。

    > [!NOTE]  
    > 您可以一次刪除一個以上的設定檔。 若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個設定檔。 或者，若要選取所有設定檔，請按一下 [**編輯**] 功能表上的 [全**選**]。

5.  在 [**編輯**] 功能表上，按一下 [**刪除**]。
   

    > [!WARNING]  
    > 您無法刪除與網路網站相關聯的頻寬原則設定檔。 您必須先移除與網路網站的關聯，然後才能刪除設定檔。 


## <a name="see-also"></a>請參閱

[管理網站的呼叫許可控制](managing-call-admission-control-for-sites.md)
 
[新-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[移除-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

