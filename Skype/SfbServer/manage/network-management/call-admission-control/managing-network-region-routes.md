---
title: 管理網路區域路由
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
description: 網路區域路由定義一對網路區域之間的路由。 通話許可控制部署中的每一組網路區域都需要網路區域路由。
ms.openlocfilehash: 5e0c099b8c461873b96963c721d835f1ccdf4705
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817492"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>管理商務用 Skype Server 中的網路地區路由

*網路區域路由*定義一對網路區域之間的路由。 通話許可控制部署中的每一組網路區域都需要網路區域路由。 這可讓部署中的每個網路區域存取每一個其他區域。 使用此 artilce 中的程式來查看、建立、修改或刪除網路區路由。

## <a name="view-network-region-route-information"></a>查看網路區域路線資訊 

呼叫許可控制（CAC）配置中的每個地區都必須有一些方法，才能存取其他每個區域。 雖然 [地區] 連結會針對區域之間的連線設定頻寬限制，同時也代表物理連結，但是路由會判斷連線從一個地區到另一個區域的連結路徑。 使用下列程式，在商務用 Skype Server 控制台或商務用 Skype Server Management Shell 中，查看現有的網路區域路由。 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>若要在商務用 Skype Server [控制台] 中查看網路區域路線資訊

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路線**]。

4.  在 [**地區路線**] 頁面上，按一下您要查看的地區路線。


    > [!NOTE]  
    > 一次只能查看一個區域路線。


5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看網路區域路由資訊

您可以使用 Windows PowerShell 和 CsNetworkInterRegionRoute Cmdlet 來查看網路區域路由資訊。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 

### <a name="to-view-network-region-route-information"></a>若要查看網路區域路線資訊

  - 若要查看所有網路區域路由的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsNetworkInterRegionRoute
    
    這會傳回如下所示的資訊：
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

如需詳細資訊，請參閱[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) Cmdlet 的說明主題。


## <a name="create-or-modify-network-region-routes"></a>建立或修改網路區路由

呼叫許可控制（CAC）配置中的每個地區都必須有一些方法，才能存取其他每個區域。 雖然 [地區] 連結會針對區域之間的連線設定頻寬限制，同時也代表物理連結，但是路由會判斷連線從一個地區到另一個區域的連結路徑。 您可以使用商務用 Skype Server 的 [控制台] 來設定網路區域路由。 從商務用 Skype Server 的 [控制台] 中，您可以建立、修改或刪除網路區域路由。 使用本主題來建立或修改網路區域路由。 

### <a name="to-create-a-network-region-route"></a>建立網路區域路由

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路線**]。

4.  在 [**地區路線**] 頁面上，按一下 [**新增**]。

5.  在 [**新區域路由**] 中，于 [**名稱**] 欄位中輸入值。
   
    > [!NOTE]  
    > 此值在您的商務用 Skype Server 部署中必須是唯一的。

6.  從 [**網路區域\#1** ] 下拉式清單中，選取要由此路由連接的兩個區域中的其中一個。

7.  從 [**網路區域\#2** ] 下拉式清單中，選取此路由的另一個區域。 這個區域必須與針對 [網路區\#1] 所選取的區域不同。

8.  使用 [**網路區域連結**] 清單方塊來新增路由的區域連結。 按一下 [**新增**] 按鈕以顯示 [**地區連結**] 頁面。 按一下要新增至此路線的區域連結，然後按一下 **[確定]**。
    
    > [!NOTE]  
    > 繼續按一下 [**新增**] 按鈕以新增更多連結，或選取連結，然後按一下 [**移除**] 以移除連結。

9.  按一下 [認可]****。


### <a name="to-modify-a-network-region-route"></a>修改網路區域路由

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路線**]。

4.  在 [**地區路線**] 頁面上，按一下您要修改的地區路線。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯區域] 路由**中，您可以修改由此路由加入的區域，以及與路由相關聯的區域連結。

7.  按一下 [認可]****。


## <a name="delete-existing-network-region-routes"></a>刪除現有的網路區域路由

呼叫許可控制（CAC）配置中的每個地區都必須有一些方法，才能存取其他每個區域。 雖然 [地區] 連結會針對區域之間的連線設定頻寬限制，同時也代表物理連結，但是路由會判斷連線從一個地區到另一個區域的連結路徑。 您可以使用商務用 Skype Server 的 [控制台] 來設定網路區域路由。 從商務用 Skype Server 的 [控制台] 中，您可以建立、修改或刪除網路區域路由。 使用本主題刪除現有的網路區域路由。 

### <a name="to-delete-a-network-region-route"></a>刪除網路區域路線

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路線**]。

4.  在 [**地區路線**] 頁面上，按一下您要刪除的地區路線。

    > [!NOTE]  
    > 您可以一次刪除一個以上的區域路由。 若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個區域路由。 或者，若要選取所有地區路線，請按一下 [**編輯**] 功能表上的 [全**選**]。

5.  在 [**編輯**] 功能表上，按一下 [**刪除**]。

6.  按一下 [確定]****。



## <a name="see-also"></a>請參閱

[管理商務用 Skype Server 中的網路地區](managing-network-regions.md)

[新-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[移除-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
