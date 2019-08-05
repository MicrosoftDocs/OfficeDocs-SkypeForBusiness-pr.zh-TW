---
title: 管理網站的呼叫許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Network sites 是呼叫許可控制 (CAC)、E9-1 及媒體旁路部署的每個網路區域內的辦公室或位置。
ms.openlocfilehash: a90781eae38d92d560dd1bf34db3b6918e8aeaf5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188581"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>管理商務用 Skype Server 中的網站通話許可控制

Network sites 是呼叫許可控制 (CAC)、E9-1 及媒體旁路部署的每個網路區域內的辦公室或位置。 使用本文中的程式來設定網路網站的呼叫許可控制。

## <a name="configure-network-site-links"></a>設定網路網站連結

在呼叫許可控制 (CAC) 配置中, 您可以建立網路間原則, 以定義直接連結之網站之間的頻寬限制。 當網路網站共用直接連結時, 音訊與視頻連線的頻寬限制可以在這兩個網站之間定義。 您無法使用商務用 Skype Server 的 [控制台] 來設定網路網站原則, 只能使用商務用 Skype Server Management Shell 中的 Cmdlet 來執行此操作。 您可以從商務用 Skype Server Management Shell 建立、修改及移除網路網站連結 (又稱為「網路間」原則)。

### <a name="to-create-a-network-site-link"></a>建立網路網站連結

1.  登入將商務用 Skype Server Management Shell 安裝為 RTCUniversalServerAdmins 群組的成員或必要的使用者權利的電腦。

2.  啟動商務用 Skype Server 管理命令介面: 請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype 伺服器**], 然後按一下 [**商務用 skype server 管理命令**介面]。

3.  在命令提示字元中, 輸入下列命令, 以取代有效的設定值:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    這個範例會建立名為 Reno\_的新網路網站連結, 以設定 Reno 與新的網路網站之間的頻寬限制。 在執行這個命令之前, 必須已經存在網路網站和頻寬原則設定檔。

如需詳細的參數描述, 請參閱[新的 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)。 若要取得可套用至 network site link 的頻寬原則配置檔案清單, 請呼叫**CsNetworkBandwidthPolicyProfile** Cmdlet。 如需詳細資訊, 請參閱[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。

### <a name="to-modify-a-network-site-link"></a>修改網路網站連結

1.  登入將商務用 Skype Server Management Shell 安裝為 RTCUniversalServerAdmins 群組的成員或必要的使用者權利的電腦。

2.  啟動商務用 Skype Server 管理命令介面: 請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype 伺服器**], 然後按一下 [**商務用 skype server 管理命令**介面]。

3.  使用**CsNetworkInterSitePolicy** Cmdlet 來修改指定的網路網站連結的屬性。 您可以修改 (或兩者) 或連線的網站, 也可以修改與連結相關聯的頻寬原則設定檔。 以下是修改名為 Reno\_的網站連結的頻寬原則設定檔範例:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

如需詳細的參數描述, 請參閱[設定 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)。


### <a name="to-delete-a-network-site-link"></a>刪除網路網站連結

1.  登入將商務用 Skype Server Management Shell 安裝為 RTCUniversalServerAdmins 群組的成員或必要的使用者權利的電腦。

2.  啟動商務用 Skype Server 管理命令介面: 請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype 伺服器**], 然後按一下 [**商務用 skype server 管理命令**介面]。

3.  使用**CsNetworkInterSitePolicy** Cmdlet 來移除網路網站連結。 下列範例會刪除 Reno\_的 [上海網路] 網站連結:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

如需詳細的參數描述, 請參閱[移除-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。


## <a name="view-network-site-information"></a>查看網路網站資訊

[網路網站] 是在通話許可控制 (CAC) 或增強型9-1-1 部署的每個區域中設定的辦公室或位置。 您可以在商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理] 命令介面上, 查看網路網站資訊。 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>若要在商務用 Skype Server [控制台] 中查看網路網站資訊

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**網站**]。

4.  在 [**網站**] 頁面上, 按一下您要查看的網站。
 
    > [!NOTE]  
    > 您一次只能查看一個網站的資訊。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看網路網站資訊

您可以使用 Windows PowerShell 和 CsNetworkSite Cmdlet 來查看網路網站資訊。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 

### <a name="to-view-network-site-information"></a>若要查看網路網站資訊

  - 若要查看所有網路網站的相關資訊, 請在商務用 Skype Server 管理命令介面中輸入下列命令, 然後按 ENTER 鍵:
    
        Get-CsNetworkSite
    
    這會傳回如下所示的資訊:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

如需詳細資訊, 請參閱[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) Cmdlet 的說明主題。


## <a name="create-or-modify-network-sites"></a>建立或修改網路網站 

[網路網站] 是在通話許可控制 (CAC) 或增強型9-1-1 部署的每個區域中設定的辦公室或位置。 您可以使用商務用 Skype Server 的 [控制台] 來設定網站, 並將它們與區域建立關聯。 例如, 北美的網路區域可能會與「芝加哥」、「雷德蒙」和「范與范」等網路網站相關聯。 您必須針對組織中的每個網站建立 CAC 網路網站, 即使該網站沒有頻寬限制也一樣。 您可以從商務用 Skype Server 的 [控制台] 建立、修改及刪除網路網站。 使用下列程式來建立或修改網路網站。 

### <a name="to-create-a-network-site"></a>建立網路網站

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**網站**]。

4.  在 [**網站**] 頁面上, 按一下 [**新增**]。

5.  在 [**新增網站**] 的 [**名稱**] 欄位中, 輸入此網站的名稱。

    > [!NOTE]  
    > 網站名稱在商務用 Skype Server 部署中必須是唯一的。

6.  在 [**地區**] 下拉式清單中, 選取要與此網站建立關聯的網路區域。

7.  可選如果您想要將音訊或視頻通話的頻寬限制放到此網站, 請從 [**頻寬原則**] 下拉式清單中選取 [頻寬原則] 設定檔和適當的設定。
 
    > [!NOTE]  
    > 您可以在 [**網路**設定] 群組的 [**原則 Profil** ] 頁面上, 查看可用頻寬原則設定檔的詳細資料, 或建立新的頻寬原則設定檔。 如需詳細資訊, 請參閱[管理網路頻寬原則設定檔](managing-network-bandwidth-policy-profiles.md)。

8.  可選如果您想要提供此網站的位置設定, 請從 [**位置原則**] 下拉式清單中選取位置原則。

    > [!NOTE]  
    > 位置原則會將特定的增強型 9-1-1 (E9-1-1) 及用戶端位置設定指派至網站。 您可以從 [**網路**設定] 群組的 [**位置原則**] 頁面, 查看可用位置原則的詳細資料, 或建立新的位置原則。 

9.  可選在 [**描述**] 欄位中輸入一個值, 以提供此網站的詳細資訊, 而不能單獨以名稱表示。

10. 按一下 [認可]****。

    > [!NOTE]  
    > 當您建立新的網路網站時, 請不要使用**相關聯的子網**資料表。 當您建立或修改子網時, 您可以將子網與網站建立關聯。 如需詳細資訊, 請參閱[管理網路子網](managing-network-subnets.md)。

### <a name="to-modify-a-network-site"></a>修改網路網站

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**網站**]。

4.  在 [**網站**] 頁面上, 按一下您要修改的網站。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯網站**] 頁面上, 您可以修改與網站相關聯的描述、區域、頻寬原則設定檔, 以及位置原則。 如需詳細資訊, 請參閱上面的[建立網路網站](#to-create-a-network-site)。

7.  按一下 [認可]****。

您無法在此頁面上修改**關聯的子網**資料表。 相關子網的清單是為參考提供的, 因此您在修改網站設定時, 您會發現哪些子網會受到影響。


## <a name="delete-an-existing-network-site"></a>刪除現有的網路網站

[網路網站] 是在通話許可控制 (CAC) 或增強型9-1-1 部署的每個區域中設定的辦公室或位置。 您可以使用商務用 Skype Server 的 [控制台] 來設定網站, 並將它們與區域建立關聯。 例如, 北美的網路區域可能會與「芝加哥」、「雷德蒙」和「范與范」等網路網站相關聯。 您必須針對組織中的每個網站建立 CAC 網路網站, 即使該網站沒有頻寬限制也一樣。 您可以從商務用 Skype Server 的 [控制台] 建立、修改及刪除網路網站。 使用下列程式刪除現有的網路網站。 如需建立或修改網路網站的詳細資料, 請參閱[管理網站的呼叫許可控制](managing-call-admission-control-for-sites.md)。


### <a name="to-delete-a-network-site"></a>刪除網路網站

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**網站**]。

4.  在 [**網站**] 頁面上, 按一下您要刪除的網站。

    > [!NOTE]  
    > 您可以一次刪除一個以上的網站。 若要這樣做, 請按住 CTRL 並在按住 CTRL 鍵的同時選取多個網站。 或者, 若要選取 [所有網站], 請按一下 [**編輯**] 功能表上的 [全**選**]。

5.  在 [**編輯**] 功能表上, 按一下 [**刪除**]。

6.  按一下 [確定]****。
    

    > [!WARNING]  
    > 如果網路網站與網路子網相關聯, 您就無法移除它。 如果您嘗試移除與子網相關聯的網站, 您會收到錯誤訊息。 若要查看網站是否與任何子網產生關聯, 請按一下該網站, 然後按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。


## <a name="see-also"></a>請參閱


[新-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[移除-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[新-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[移除-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
