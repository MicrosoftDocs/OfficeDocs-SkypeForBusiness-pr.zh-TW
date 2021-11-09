---
title: 管理網路地區路由
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 網路地區路由會定義一對網路地區之間的路由。 在您的通話許可控制部署中的每一對網路地區都需要網路地區路由。
ms.openlocfilehash: 18bee9a28eed10affae1b0dab855c379709b37bb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864750"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>管理商務用 Skype Server 中的網路地區路由

*網路地區路由* 會定義一對網路地區之間的路由。 在您的通話許可控制部署中的每一對網路地區都需要網路地區路由。 這可讓部署中的每一個網路地區都可以存取所有其他的地區。 使用此 artilce 中的程式來查看、建立、修改或刪除網路地區路由。

## <a name="view-network-region-route-information"></a>查看網路地區路由資訊 

通話許可控制服務 (CAC) 組態內的每個地區，都必須要有辦法存取其他每個地區。 地區連結會設定地區間連線的頻寬限制，也代表實體連結，路由則會決定從甲地連線到乙地時要周遊的連結路徑。 使用下列程式可在商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面中查看現有的網路地區路由。 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>在商務用 Skype Server 控制台中查看網路地區路由資訊

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，依序按一下 [ **網路** 設定] 和 [ **地區路由**]。

4.  在 [ **地區路由** ] 頁面上，按一下您要查看的地區路由。


    > [!NOTE]
    > 您一次只能查看一個區域路由。


5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路地區路由資訊

您可以使用 Windows PowerShell 和 Get-CsNetworkInterRegionRoute Cmdlet 來查看網路地區路由資訊。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行此 Cmdlet。 

### <a name="to-view-network-region-route-information"></a>若要查看網路地區路由資訊

  - 若要查看所有網路地區路由的資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 enter：
    
    **Get-CsNetworkInterRegionRoute**
    
    如此將傳回類似如下的資訊：
    
    身分識別： TransAmericaRoute<br/>
    NetworkRegionLinks : {NorthwestToNortheast}<br/>
    InterNetworkRegionRouteID : TransAmericaRoute<br/>
    NetworkRegionID1：太平洋西北部<br/>
    NetworkRegionID2：東北<br/>

如需詳細資訊，請參閱 [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute) Cmdlet 的 [說明] 主題。


## <a name="create-or-modify-network-region-routes"></a>建立或修改網路地區路由

通話許可控制服務 (CAC) 組態內的每個地區，都必須要有辦法存取其他每個地區。 地區連結會設定地區間連線的頻寬限制，也代表實體連結，路由則會決定從甲地連線到乙地時要周遊的連結路徑。 您可以使用商務用 Skype Server 控制台設定網路地區路由。 從商務用 Skype Server 控制台，您可以建立、修改或刪除網路地區路由。 若要建立或修改網路地區路由，請利用本節主題。 

### <a name="to-create-a-network-region-route"></a>若要建立網路地區路由

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，依序按一下 [ **網路** 設定] 和 [ **地區路由**]。

4.  在 **[地區路由]** 頁面上，按一下 **[新增]**。

5.  在 **[新的地區路由]** 的 **[名稱]** 欄位中，輸入一個值。
   
    > [!NOTE]  
    > 此值在您的商務用 Skype Server 部署中必須是唯一的。

6.  從 [ **網路地區 \# 1** ] 下拉式清單中，選取兩個區域中的其中一個要透過此路由來連線。

7.  從 [ **網路地區 \# 2** ] 下拉式清單中，選取此路由的其他地區。 此區域必須與為網路地區1所選取的區域不同 \# 。

8.  使用 **[網路地區連結]** 清單方塊，將地區連結新增至路由。按一下 **[新增]** 按鈕以顯示 **[地區連結]** 頁面。按一下要新增至此路由的地區連結，然後按一下 **[確定]**。
    
    > [!NOTE]  
    > 若要新增更多連結，請繼續按 **[新增]** 按鈕；若要移除連結，請選取連結，然後按一下 **[移除]**。

9.  按一下 **[認可]**。


### <a name="to-modify-a-network-region-route"></a>若要修改網路地區路由

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，依序按一下 [ **網路** 設定] 和 [ **地區路由**]。

4.  在 **[地區路由]** 頁面上，按一下您要修改的地區路由。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 **[編輯地區路由]** 中，您可以修改此路由所聯結的地區，以及與路由相關聯的地區連結。

7.  按一下 **[認可]**。


## <a name="delete-existing-network-region-routes"></a>刪除現有的網路地區路由

通話許可控制服務 (CAC) 組態內的每個地區，都必須要有辦法存取其他每個地區。 地區連結會設定地區間連線的頻寬限制，也代表實體連結，路由則會決定從甲地連線到乙地時要周遊的連結路徑。 您可以使用商務用 Skype Server 控制台設定網路地區路由。 從商務用 Skype Server 控制台，您可以建立、修改或刪除網路地區路由。 若要刪除現有的網路地區路由，請利用本主題。 

### <a name="to-delete-a-network-region-route"></a>刪除網路地區路由

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，依序按一下 [ **網路** 設定] 和 [ **地區路由**]。

4.  在 **[地區路由]** 頁面上，按一下您要刪除的地區路由。

    > [!NOTE]  
    > 您可以同時刪除多個地區路由。如果要執行這項作業，請按住 CTRL 鍵，然後選取多個地區路由。或者，若要選取所有地區路由，請按一下 **[編輯]** 功能表上的 **[全選]**。

5.  在 **[編輯]** 功能表中，按一下 **[刪除]**。

6.  按一下 [確定]。



## <a name="see-also"></a>另請參閱

[管理商務用 Skype Server 中的網路地區](managing-network-regions.md)

[新 CsNetworkInterRegionRoute](/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[CsNetworkInterRegionRoute](/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute)