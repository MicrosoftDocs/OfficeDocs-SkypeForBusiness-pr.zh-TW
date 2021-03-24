---
title: 連結網路地區
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
description: '您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。 '
ms.openlocfilehash: 163f214b05ba0dca3bc7dd4ec722f148cafe724e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096679"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>連結商務用 Skype Server 中的網路地區

您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。 請使用本文中的章節來查看 newtwork 區域連結資訊，或設定或刪除網路區域連結。 

## <a name="view-network-region-link-information"></a>查看網路地區連結資訊 

您可以透過通話許可控制 (CAC) 檢視兩個網路地區之間的連結。 網路中的地區是透過實體廣域網路 (WAN) 連線相連結。 您可以使用商務用 Skype Server 控制台，以查看兩個網路地區之間的現有連結。 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>在商務用 Skype Server 控制台中查看網路地區連結

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區連結**]。

4.  在 [區域連結] 頁面中，按一下要檢視的區域連結。
    
    > [!NOTE]  
    > 一次只能檢視一個區域的資訊。

5.  從 [編輯] 功能表中，選取 [顯示詳細資料]。

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路地區連結資訊

您可以使用 Windows PowerShell 和 **Get-CsNetworkRegionLink** Cmdlet 來查看網路地區連結。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。 


### <a name="to-view-network-region-link-information"></a>檢視網路地區連結資訊

  - 若要查看所有網路地區連結的資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsNetworkRegionLink
    
    此命令會傳回與下列相似的資訊：
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


如需詳細資訊，請參閱 [Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink)。


## <a name="configure-network-region-links"></a>設定網路地區連結 

您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。 網路中的地區是透過實體廣域網路 (WAN) 連線相連結。 您可以使用商務用 Skype Server 控制台來定義兩個網路地區之間的連結，並設定這些地區之間音訊和影片連線的頻寬限制。

### <a name="to-create-a-network-region-link"></a>建立網路地區連結

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區連結**]。

4.  在 [ **地區連結** ] 頁面上，按一下 [ **新增**]。

5.  在 [ **新增地區連結**] 的 [ **名稱** ] 欄位中輸入值。
 
    > [!NOTE]  
    > 此值在商務用 Skype Server 部署中必須是唯一的。

6.  從 [ **網路地區 \# 1** ] 下拉式清單中，選取兩個要連結的地區之一。

7.  從 [ **網路地區 \# 2** ] 下拉式清單中，選取要連結的其他地區。 此區域必須與為網路地區1所選取的區域不同 \# 。

8.   (選用) 若您想要在這些地區之間的音訊或視頻通話上進行頻寬限制，請從 [ **頻寬原則** ] 下拉式清單中選取頻寬原則設定檔。

9.  按一下 **[認可]**。

### <a name="to-modify-a-network-region-link"></a>若要修改網路地區連結

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區連結**]。

4.  在 [ **地區連結** ] 頁面上，按一下您要修改的地區連結。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 [ **編輯地區連結**] 中，您可以修改連結的區域或此連結的頻寬原則設定檔。

7.  按一下 **[認可]**。


## <a name="delete-network-region-links"></a>刪除網路地區連結

您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。 網路中的地區是透過實體廣域網路 (WAN) 連線相連結。 您可以使用商務用 Skype Server 控制台刪除兩個網路地區之間的現有連結。 

### <a name="to-delete-a-network-region-link"></a>刪除網路地區連結

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區連結**]。

4.  在 [地區連結] 頁面中，按一下要刪除的地區連結。
 
    > [!NOTE]  
    > 您可以一次刪除一個以上的地區連結。若要一次刪除一個以上的地區連結，請按住 CTRL 鍵並同時選取多個地區連結。若要選取多個地區，您也可以按一下 [編輯]<STRONG></STRONG> 功能表中的 [全選]<STRONG></STRONG>。

5.  選取 [編輯] 功能表中的 [刪除]。

6.  按一下 [確定]。


## <a name="see-also"></a>另請參閱

[新 CsNetworkRegionLink](/powershell/module/skype/New-CsNetworkRegionLink)  

[CsNetworkRegionLink](/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink)