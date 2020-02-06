---
title: 連結網路區域
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
description: '您可以設定兩個網路區域之間的連結，作為通話許可控制（CAC）的一部分。 '
ms.openlocfilehash: 4a643f34b9525b53168b9015b77a7f8292abd417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817522"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>連結商務用 Skype Server 中的網路地區

您可以設定兩個網路區域之間的連結，作為通話許可控制（CAC）的一部分。 使用本文中的章節來查看 newtwork 區域連結資訊，或設定或刪除 netwrok 區域連結。 

## <a name="view-network-region-link-information"></a>[查看網路區域] 連結資訊 

您可以在 [呼叫許可控制] （CAC）中，查看兩個網路區域之間的連結。 網路中的區域是透過物理廣域網路（WAN）連線來連結。 您可以使用商務用 Skype Server [控制台] 來查看兩個網路區域之間的現有連結。 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>若要在商務用 Skype Server [控制台] 中查看網路區域連結

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區連結**]。

4.  在 [**地區連結**] 頁面上，按一下您要查看的區域連結。
    
    > [!NOTE]  
    > 您一次只能查看一個區域連結的相關資訊。

5.  從 [**編輯**] 功能表中，選取 [**顯示詳細資料**]。

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路區域連結資訊

您可以使用 Windows PowerShell 和**CsNetworkRegionLink** Cmdlet 來查看網路區域連結。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 


### <a name="to-view-network-region-link-information"></a>若要查看網路區域連結資訊

  - 若要查看所有網路區域連結的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER：
    
        Get-CsNetworkRegionLink
    
    這個命令會傳回如下所示的資訊：
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


如需詳細資訊，請參閱[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。


## <a name="configure-network-region-links"></a>設定網路區域連結 

您可以設定兩個網路區域之間的連結，作為通話許可控制（CAC）的一部分。 網路中的區域是透過物理廣域網路（WAN）連線來連結。 您可以使用商務用 Skype Server 的 [控制台] 來定義兩個網路區域之間的連結，並設定這些區域之間音訊與視頻連線的頻寬限制。

### <a name="to-create-a-network-region-link"></a>建立網路區域連結

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區連結**]。

4.  在 [**地區連結**] 頁面上，按一下 [**新增**]。

5.  在 [**新區域] 連結**的 [**名稱**] 欄位中輸入值。
 
    > [!NOTE]  
    > 此值在您的商務用 Skype Server 部署中必須是唯一的。

6.  從 [**網路區域\#1** ] 下拉式清單中，選取兩個要連結的區域之一。

7.  從 [**網路區域\#2** ] 下拉式清單中，選取要連結的其他區域。 這個區域必須與針對 [網路區\#1] 所選取的區域不同。

8.  可選如果您想要將頻寬限制放在這些區域之間的音訊或視頻通話中，請從 [**頻寬原則**] 下拉式清單中選取 [頻寬原則] 設定檔。

9.  按一下 [認可]****。

### <a name="to-modify-a-network-region-link"></a>修改網路區域連結

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區連結**]。

4.  在 [**地區連結**] 頁面上，按一下您要修改的區域連結。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯區域] 連結**中，您可以修改連結的區域或此連結的頻寬原則設定檔。

7.  按一下 [認可]****。


## <a name="delete-network-region-links"></a>刪除網路區域連結

您可以設定兩個網路區域之間的連結，作為通話許可控制（CAC）的一部分。 網路中的區域是透過物理廣域網路（WAN）連線來連結。 您可以使用商務用 Skype Server [控制台] 來刪除兩個網路區域之間的現有連結。 

### <a name="to-delete-a-network-region-link"></a>刪除網路區域連結

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區連結**]。

4.  在 [**地區連結**] 頁面上，按一下您要刪除的區域連結。
 
    > [!NOTE]  
    > 您可以一次刪除一個以上的區域連結。 若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個區域連結。 或者，若要選取所有區域連結，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。

5.  從 [**編輯**] 功能表中，選取 [**刪除**]。

6.  按一下 [確定]****。


## <a name="see-also"></a>請參閱

[新-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[移除-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
