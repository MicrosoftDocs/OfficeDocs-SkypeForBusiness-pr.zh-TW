---
title: 管理網站的通話許可控制
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
description: 網站是指通話許可控制 (CAC)、E9-1-1 和媒體旁路部署的每一個網路地區內的辦公室或位置。
ms.openlocfilehash: fd353980e7ac2a367b05c0f0be6ce760b7102fcc
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233668"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>在商務用 Skype Server 中的網站管理通話許可控制

網站是指通話許可控制 (CAC)、E9-1-1 和媒體旁路部署的每一個網路地區內的辦公室或位置。 使用本文中的程式設定網路網站的通話許可控制。

## <a name="configure-network-site-links"></a>設定網路站台連結

在通話許可控制 (CAC) 組態中，您可以建立網路網站間原則以定義直接連結的網站之間的頻寬限制。 當網路網站共用直接連結時，您可以定義這兩個網站之間音訊與視訊連線的頻寬限制。 您無法使用商務用 Skype Server 控制台設定網路網站原則，只能使用來自商務用 Skype Server 管理命令介面的 Cmdlet 來執行此動作。 您可以建立、修改及移除網路站台連結 (也稱為從商務用 Skype Server 管理命令介面) 網路內部網站原則。

### <a name="to-create-a-network-site-link"></a>若要建立網路網站連結

1.  以 RTCUniversalServerAdmins 群組成員的身分或必要的使用者權限，登入安裝商務用 Skype Server 管理命令介面的電腦。

2.  啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

3.  在命令提示字元中輸入下列命令，其中的值換成您組態適用的有效值：
    
     **CsNetworkInterSitePolicy-Identity Reno_Portland-NetworkSiteID1 雷諾-NetworkSiteID2 上的 BWPolicyProfileID LowBWLimits**
    
    這個範例會建立名為雷諾的新網路站台連結 \_ ，此連結會設定雷諾和上點網路網站之間的頻寬限制。 網路網站與頻寬原則設定檔在執行此命令前即必須存在。

如需詳細的參數描述，請參閱 [CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy)。 若要擷取可套用至網路網站連結之頻寬原則設定檔的清單，請呼叫 **Get-CsNetworkBandwidthPolicyProfile** Cmdlet。 如需詳細資訊，請參閱 [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。

### <a name="to-modify-a-network-site-link"></a>若要修改網路網站連結

1.  以 RTCUniversalServerAdmins 群組成員的身分或必要的使用者權限，登入安裝商務用 Skype Server 管理命令介面的電腦。

2.  啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

3.  使用 **Set-CsNetworkInterSitePolicy** Cmdlet 來修改某個網路網站連結的內容。 您可以修改相連網站的其中一端網站 (或兩端網站都修改)，並且可以修改與連結相關聯的頻寬原則設定檔。 以下是修改名為雷諾上海之網站連結的頻寬原則設定檔的範例 \_ ：
    
    **Set-CsNetworkInterSitePolicy-Identity Reno_Portland-BWPolicyProfileID HighBWLimits**

如需詳細的參數描述，請參閱 [Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy)。


### <a name="to-delete-a-network-site-link"></a>若要刪除網路網站連結

1.  以 RTCUniversalServerAdmins 群組成員的身分或必要的使用者權限，登入安裝商務用 Skype Server 管理命令介面的電腦。

2.  啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

3.  使用 **Remove-CsNetworkInterSitePolicy** Cmdlet 來移除網路網站連結。 下列範例會刪除雷諾 \_ 上海網路站台連結：
    
    **Remove-CsNetworkInterSitePolicy 識別碼 Reno_Portland**

如需詳細的參數描述，請參閱 [Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。


## <a name="view-network-site-information"></a>查看網路網站資訊

網路網站是設定在通話許可控制 (CAC) 或增強型 9-1-1 部署之每一個地區內部的辦公室或位置。 您可以在商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面中查看網路網站資訊。 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>在商務用 Skype Server 控制台中查看網路網站資訊

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **網站**]。

4.  在 [網站] 頁面上，按一下您要檢視的網站。
 
    > [!NOTE]
    > 您一次僅可檢視一個網站的網站資訊。

5.  在 [編輯] 功能表上，按一下 [顯示詳細資料]。


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路網站資訊

您可以使用 Windows PowerShell 和 Get-CsNetworkSite Cmdlet 來查看網路網站資訊。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行此 Cmdlet。 

### <a name="to-view-network-site-information"></a>若要檢視網路網站資訊

  - 若要查看所有網路網站的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 enter：
    
    **Get-CsNetworkSite**
    
    如此將傳回類似如下的資訊：
    
    身分識別： Redmond<br/>
    NetworkSiteID： Redmond<br/>
    描述：<br/>
    NetworkRegionID：太平洋西北部<br/>
    BypassID：3b232b84-2c1d-4da2-8181-e9330bafebe9<br/>
    BWPolicyProfileID :<br/>
    Microsoft.rtc.management.writableconfig.policy.location.locationpolicy<br/>

如需詳細資訊，請參閱＜[Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite)＞Cmdlet 的說明主題。


## <a name="create-or-modify-network-sites"></a>建立或修改網路網站 

網路網站是設定在通話許可控制 (CAC) 或增強型 9-1-1 部署之每一個地區內部的辦公室或位置。 您可以使用商務用 Skype Server 控制台來設定網站，並將其與區域產生關聯。 例如，北美洲的網路區域可能會和 Chicago、Redmond 及 Vancouver 等網路網站相關聯。 您必須為組織內的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制。 您可以從商務用 Skype Server 控制台建立、修改和刪除網路網站。 請使用下列程序來建立或修改網站。 

### <a name="to-create-a-network-site"></a>若要建立網路網站

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **網站**]。

4.  在 **[網站]** 頁面上，按 **[新增]**。

5.  在 **[新增網站]** 的 **[名稱]** 欄位中，輸入網站的名稱。

    > [!NOTE]  
    > 網站名稱在商務用 Skype Server 部署中必須是唯一的。

6.  在 **[地區]** 下拉式清單中，選取要與此網站產生關聯的網域地區。

7.  (選用) 如果您要對此網站的音訊或視訊通話限制頻寬，請從 **[頻寬原則]** 下拉式清單中選取含有適當設定的頻寬原則設定檔。
 
    > [!NOTE]  
    > 您可以在 [**網路** 設定] 群組的 [**原則 Profil** ] 頁面上，查看可用頻寬原則設定檔的詳細資料，或建立新的頻寬原則設定檔。 如需詳細資訊，請參閱 [管理網路頻寬原則設定檔](managing-network-bandwidth-policy-profiles.md)。

8.  (選用) 如果您要提供此網站的位置設定，請從 **[位置原則]** 下拉式清單中選取位置原則。

    > [!NOTE]  
    > 此位置原則將特定的增強型 9-1-1 (E9-1-1) 功能和用戶端位置設定指派給網站。 您可以在 **[網路設定]** 群組的 **[位置原則]** 頁面上，檢視可用位置原則的詳細資訊，或是建立新的位置原則。 

9.  (選用) 在 **[描述]** 欄位中輸入值，提供無法用名稱完整表達的網站的其他資訊。

10. 按一下 **[認可]**。

    > [!NOTE]  
    > 建立新的網路網站時不會使用 **[關聯的子網路]** 表格。 建立或修改子網路時才會讓子網路與網站相關聯。 如需詳細資訊，請參閱 [管理網路子網](managing-network-subnets.md)。

### <a name="to-modify-a-network-site"></a>修改網站

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **網站**]。

4.  在 **[網站]** 頁面中，按一下您要修改的網站。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 **[編輯網站]** 頁面上，您可以修改與網站相關聯的描述、地區、頻寬原則設定檔和位置原則。 如需詳細資訊，請參閱 [建立上述網路網站](#to-create-a-network-site) 。

7.  按一下 **[認可]**。

您無法修改此頁面上的 **[關聯的子網路]** 表格。關聯的子網路清單僅供參考，讓您知道修改網站設定會影響哪些子網路。


## <a name="delete-an-existing-network-site"></a>刪除現有的網路網站

網路網站是設定在通話許可控制 (CAC) 或增強型 9-1-1 部署之每一個地區內部的辦公室或位置。 您可以使用商務用 Skype Server 控制台來設定網站，並將其與區域產生關聯。 例如，北美洲的網路區域可能會和 Chicago、Redmond 及 Vancouver 等網路網站相關聯。 您必須為組織內的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制。 您可以從商務用 Skype Server 控制台建立、修改和刪除網路網站。 使用下列程序刪除現有網路網站。 如需建立或修改網路網站的詳細資訊，請參閱 [管理網站的通話許可控制](managing-call-admission-control-for-sites.md)。


### <a name="to-delete-a-network-site"></a>刪除網路網站

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **網站**]。

4.  在 [網站] 頁面上，按一下您要刪除的網站。

    > [!NOTE]  
    > 您可以一次刪除多個網站。若要這樣做，請按 CTRL 並在按住 CTRL 鍵的同時選取多個網站。或者，若要選取所有網站，請按一下 [編輯] 功能表上的 [全選]。

5.  在 **[編輯]** 功能表中，按一下 **[刪除]**。

6.  按一下 [確定]。
    

    > [!WARNING]  
    > 但是如果網站與某個網路子網路相關聯時，則無法移除該網路網站。如果您嘗試移除與子網路相關聯的網站，則會收到錯誤訊息。若要查看網站是否與子網路相關聯，請按一下網站並按一下 [編輯] 功能表上的 [顯示詳細資料]。


## <a name="see-also"></a>另請參閱


[新 CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite)