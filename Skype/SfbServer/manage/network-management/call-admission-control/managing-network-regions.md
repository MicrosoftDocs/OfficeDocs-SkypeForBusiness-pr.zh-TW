---
title: 管理網路區域
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
description: Network region * 是網路中樞或 backbones，用於設定通話許可控制、E9-1 及媒體旁路。
ms.openlocfilehash: c08232e455edb4388a052c2859b35e6c137b890a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817482"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>管理商務用 Skype Server 中的網路地區

*網路區域*是網路中樞或 backbones，用於設定通話許可控制、E9-1 及媒體旁路。 使用下列程式來查看、建立或修改網路區。 例如，如果您已為單一語音功能建立網路區域，就不需要建立新的網路區域;其他高級企業語音功能將會使用相同的網路區域。 不過，您可能需要修改現有的網路區域定義，才能套用特定功能的設定。 例如，如果您已建立 E9 的網路區域（不需要關聯的中央網站），而您想要部署 [呼叫許可控制]，您必須修改網路區域定義，以指定中央網站。 

使用本文中的程式來查看網路區域資訊，或建立、修改或刪除網路區域。 

## <a name="view-network-region-information"></a>查看網路區域資訊 


網路區域跨多個地理區域互連網路的各個部分。 每個網路區域都必須與一個中央網站建立關聯。 中央網站是在其上執行呼叫許可控制（CAC）頻寬原則服務的資料中心網站。 您可以使用商務用 Skype Server 的 [控制台] 來查看網路區域。 網路區域包括決定是否允許透過網際網路使用替換路徑進行音訊和視頻連線的設定。 您可以使用本主題來查看現有的網路區域。 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台查看網路區域的相關資訊

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區**]。

4.  在 [**地區**] 頁面上，按一下您要查看的地區。
  
    > [!NOTE]  
    > 一次只能查看一個區域。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路區域資訊

您可以使用 Windows PowerShell 和**CsNetworkRegion** Cmdlet 來查看網路區域資訊。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 

### <a name="to-view-network-region-information"></a>若要查看網路區域資訊

  - 若要查看所有網路區域的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsNetworkRegion
    
    這會傳回如下所示的資訊：
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

如需詳細資訊，請參閱[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) Cmdlet 的說明主題。


## <a name="create-or-modify-network-regions"></a>建立或修改網路區域 

網路區域跨多個地理區域互連網路的各個部分。 每個網路區域都必須與一個中央網站建立關聯。 中央網站是在其上執行呼叫許可控制（CAC）頻寬原則服務的資料中心網站。 您可以使用商務用 Skype Server [控制台] 來設定網路區域。 網路區域包括決定是否允許透過網際網路使用替換路徑進行音訊和視頻連線的設定。 從商務用 Skype Server 的 [控制台] 中，您可以建立、修改或刪除網路區域。 使用本主題來建立及修改網路區域。 

### <a name="to-create-a-network-region"></a>建立網路區域

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區**]。

4.  在 [**地區**] 頁面上，按一下 [**新增**]。

5.  在 [**新區域**] 頁面上的 [**名稱**] 欄位中輸入值。 此值在您的商務用 Skype Server 部署中必須是唯一的。

6.  從 [**中央網站**] 下拉式清單中，選取此網路區域的中心網站。

7.  預設會選取 [**啟用音訊備用路徑**] 核取方塊。 此欄位會判斷在主要路徑中不存在足夠頻寬的情況下，是否會透過替代路徑路由音訊通話。 如果您需要關閉卸載至網際網路，請先清除此核取方塊。 如果您的任何通話是網際網路通話，則必須核取此核取方塊（無論頻寬設定為何）。

8.  預設會選取 [**啟用影片替換路徑**] 核取方塊。 此欄位會判斷在主要路徑中不存在足夠頻寬時，是否會透過備用路徑路由視頻通話。 如果您需要關閉卸載至網際網路，請先清除此核取方塊。 如果您的任何通話是網際網路通話，則必須核取此核取方塊（無論頻寬設定為何）。

9.  可選在 [**描述**] 欄位中輸入一個值，以提供關於此區域的詳細資訊，而不能單獨以名稱表示。

10. 按一下 [認可]****。

[**關聯的網站**] 資料表不是用來建立網路區域。 您可以在建立或修改網站時，將網站與區域建立關聯。 如需詳細資訊，請參閱[管理網站的呼叫許可控制](managing-call-admission-control-for-sites.md)。

### <a name="to-modify-a-network-region"></a>修改網路區域

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區**]。

4.  在 [**地區**] 頁面上，按一下您要修改的地區。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯區域**] 頁面上，您可以修改啟用及停用音訊及視頻替代路徑的設定，以及變更描述（如需詳細資訊，請參閱本主題前面的「建立網路區域」一節。

7.  按一下 [認可]****。

您無法在此頁面上修改**關聯的網站**。 已提供相關網站的清單供參考，因此您知道在修改區域設定時，哪些網站會受到影響。


## <a name="delete-existing-network-regions"></a>刪除現有的網路區域 

網路區域跨多個地理區域互連網路的各個部分。 每個網路區域都必須與一個中央網站建立關聯。 中央網站是在其上執行呼叫許可控制（CAC）頻寬原則服務的資料中心網站。 您可以使用商務用 Skype Server [控制台] 來設定網路區域。 網路區域包括決定是否允許透過網際網路使用替換路徑進行音訊和視頻連線的設定。 從商務用 Skype Server 的 [控制台] 中，您可以建立、修改或刪除網路區域。 使用本主題刪除現有的網路區域。 

### <a name="to-delete-a-network-region"></a>刪除網路區域

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區**]。

4.  在 [**地區**] 頁面上，按一下您要刪除的地區。
  
    > [!NOTE]  
    > 您可以一次刪除一個以上的區域。 若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個區域。 或者，若要選取所有區域，請按一下 [**編輯**] 功能表上的 [全**選**]。

5.  在 [**編輯**] 功能表上，按一下 [**刪除**]。

6.  按一下 [確定]****。


    > [!WARNING]  
    > 如果網路區域與網路網站相關聯，則無法移除。 如果您嘗試移除與網站相關聯的區域，您會收到錯誤訊息。 若要查看某個地區是否與任何網站相關聯，請選取該區域，然後按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。


## <a name="see-also"></a>請參閱

[管理網路區域路由](managing-network-region-routes.md)

[新-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[移除-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
