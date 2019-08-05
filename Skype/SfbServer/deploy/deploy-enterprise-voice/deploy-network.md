---
title: 在商務用 Skype 中部署網路區域、網站和子網
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: '在商務用 Skype Server 中建立或修改網路區域、網路網站, 以及建立網路子網的關聯。 所有這些都適用于高級企業語音功能: [媒體旁路]、[通話許可控制] 和 [位置] 路由。'
ms.openlocfilehash: 3ce0f4dcf011f57e25c4741c34135bc4ba62085a
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36193956"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>在商務用 Skype 中部署網路區域、網站和子網

在商務用 Skype Server 中建立或修改網路區域、網路網站, 以及建立網路子網的關聯。 所有這些都適用于高級企業語音功能: [媒體旁路]、[通話許可控制] 和 [位置] 路由。

[高級企業語音功能] 是 [[呼叫許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)]、[[媒體旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)]、[[位置] 路由](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), 以及[E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md)。 這些功能全都需要您建立網路區域、網路網站和子網。 例如, 所有這些功能都要求拓撲中的每個子網都與特定的網路網站相關聯, 且每個網路網站都必須與一個網路區域建立關聯。 如需這些詞彙的詳細資訊, 請參閱[商務用 Skype Server 中的 [高級企業語音功能網路設定](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)]。

[通話許可控制] 和 [E9-1-1] 有網路網站的其他配置需求:

- 呼叫許可控制要求為受 WAN 頻寬限制所限制的每個網站指定頻寬原則設定檔。 如果您打算部署通話許可控制, 您必須先[在商務用 Skype Server 中建立頻寬原則設定檔](create-bandwidth-policy-profiles.md), 然後才能設定您的網路網站。

- E9-1-1-1 需要為每個網站指定位置原則。 如果您打算部署 E9-1-1, 您必須先[在商務用 Skype Server 中建立位置原則](create-location-policies.md), 然後才能設定您的網路網站。

## <a name="create-or-modify-a-network-region"></a>建立或修改網路區域

如果您已經為其中一個功能建立網路區域, 則不需要建立新的網路區域;其他高級企業語音功能將會使用相同的網路區域。

不過, 您可能需要修改現有的網路區域定義, 才能套用特定功能的設定。 例如, 如果您已建立 E9 的網路區域 (不需要關聯的中央網站), 而您想要部署 [呼叫許可控制], 您必須修改網路區域定義, 以指定中央網站。

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 建立網路區域

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。

2. 執行新的 CsNetworkRegion Cmdlet 來建立網路區域:

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    例如：

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    在這個範例中, 您建立了一個名為「北美洲」的網路區域, 該區域與含「網站 ID 芝加哥」的中央網站相關聯。

3. 若要為您的拓撲建立網路區域, 請對每個網路區域重複步驟2的設定。

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 建立網路區域

1. 開啟商務用 Skype Server 的 [控制台]。

2. 在左側導覽列中, 按一下 [**網路**設定]。

3. 按一下 [**地區**]。

4. 按一下 [**新增**]。

5. 在 [**新區域**] 頁面上, 按一下 [**名稱**], 然後輸入網路區域的名稱。

6. 按一下 [**中央網站**], 然後按一下清單中的中央網站。

7. 或者, 按一下 [**描述**], 然後輸入說明此網路網站的其他資訊。

8. 按一下 [認可]****。

9. 若要為您的拓撲建立網路區域, 請重複步驟4至8及其他地區的設定。

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來修改網路區域

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。

2. 執行 CsNetworkRegion Cmdlet 來修改現有的網路區域:

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    例如：

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    在這個範例中, 您修改了「北美」 (使用本主題先前的程式建立) 的現有網路區域, 方法是變更說明。 如果「北美」區域的描述存在, 這個命令會以這個值覆寫;如果沒有設定描述, 則這個命令會將其設定。

3. 若要修改其他網路區域, 請對其他地區的設定重複步驟2。

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 修改網路區域

1. 開啟商務用 Skype Server 的 [控制台]。

2. 在左側導覽列中, 按一下 [**網路**設定]。

3. 按一下 [**地區**] 導覽按鈕。

4. 在表格中, 按一下您要修改的網路區域。

5. 按一下 [**編輯**], 然後按一下 [**顯示詳細資料 ...**]。

6. 在 [**編輯區域**] 頁面上, 視需要變更這個網路區域設定的值。

7. 按一下 [認可]****。

8. 若要完成修改網路區域, 請重複步驟4至7及其他地區的設定。

## <a name="create-or-modify-a-network-site"></a>建立或修改網站

如果您已經為其中一個功能建立網路網站, 就不需要建立新的網路網站;其他高級企業語音功能將會使用相同的網路網站。 不過, 您可能需要修改現有的網路網站定義, 才能套用特定功能的設定。 例如, 如果您已建立 E9 的網路網站-1-1, 您需要在部署通話許可控制期間修改網路網站, 以套用頻寬原則設定檔。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 建立網路網站

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。

2. 執行新的 CsNetworkSite Cmdlet 來建立網路網站:

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    例如：

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    在這個範例中, 您已建立名為「芝加哥」的網路網站, 該網路網站是「北美」網路區域。

    > [!NOTE]
    > [北美] 網路區域必須已經存在, 此命令才能順利執行。

3. 若要為拓撲建立網路網站, 請對 [其他網站] 的設定重複步驟2。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 建立網路網站

1. 開啟商務用 Skype Server 的 [控制台]。

2. 在左側導覽列中, 按一下 [**網路**設定]。

3. 按一下 [**網站導航**] 按鈕。

4. 按一下 [**新增**]。

5. 在 [**新網站**] 頁面上, 按一下 [**名稱**], 然後輸入網路網站的名稱。

6. 按一下 [**地區**], 然後按一下清單中的區域。

7. 或者, 按一下 [**頻寬原則**], 然後按一下清單中的頻寬原則。

    > [!NOTE]
    > 只有當您在網站上部署 [通話許可控制] 時, 才需要頻寬原則。

8. 或者, 按一下 [**位置原則**], 然後按一下清單中的位置原則。

    > [!NOTE]
    > 只有當您在網站上部署 E9-1-1 時, 才需要位置原則。

9. 或者, 按一下 [**描述**], 然後輸入說明此網路網站的其他資訊。

10. 按一下 [認可]****。

11. 若要為您的拓撲建立網路網站, 請重複步驟4至 10, 並使用 [其他網站] 的設定。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來修改網路網站

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。

2. 執行 CsNetworkSite Cmdlet 來修改網路網站:

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    例如：

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    在這個範例中, 名為 "Albuquerque" 的網站會移至 [北美] 網路區域。 若要修改網路網站設定以部署呼叫許可控制、E9-1 或媒體旁路, 請分別執行設定 CsNetworkSite Cmdlet 及 BWPolicyProfileID 或 LocationPolicy 參數, 以修改網路網站設定。

    > [!NOTE]
    > 雖然 BypassID 參數存在於媒體旁路, 但我們強烈建議您不要覆寫自動產生的旁路 Id。 您不需要指定其他參數, 即可設定媒體旁路的網路網站。

3. 若要完成拓撲的網路網站修改, 請對 [其他網站] 的設定重複步驟2。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 修改網路網站

1. 開啟商務用 Skype Server 的 [控制台]。

2. 在左側導覽列中, 按一下 [**網路**設定]。

3. 按一下 [**網站導航**] 按鈕。

4. 在表格中, 按一下您要修改的網路網站。

5. 按一下 [**編輯**], 然後按一下 [**顯示詳細資料 ...**]。

6. 在 [**編輯網站**] 頁面上, 視需要變更此網路網站設定的值。

7. 按一下 [認可]****。

8. 若要完成修改網路網站, 請重複步驟4至7及 [其他網站] 的設定。

## <a name="associate-a-subnet-with-a-network-site"></a>建立子網路與網路站台的關聯
<a name="BKMK_AssociateSubnets"> </a>

您網路中的每個子網都必須與特定的網路網站相關聯, 因為子網資訊是用來判斷在啟動新的會話時, 端點所在的網路網站。 當會話中每一方的位置已知時, 高級企業語音功能可以套用該資訊來決定如何處理通話設定或路由。

您必須將部署中音訊/視頻邊緣伺服器的所有已設定公用 IP 位址新增至您的網路設定。 這些 IP 位址會新增成遮罩為32的子網。 相關的網路網站應該對應至適當設定的網路網站。 例如, 與中央網站芝加哥中的 A/V Edge 服務相對應的公用 IP 位址會是 NetworkSiteID 芝加哥。

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management 命令介面將子網與網路網站建立關聯

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。

2. 執行**新的 CsNetworkSubnet** Cmdlet, 以將子網與網路網站建立關聯:

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    例如：

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    在這個範例中, 您已在子網172.11.12.13 和網路網站 "芝加哥" 之間建立關聯。

3. 針對您的拓撲中的所有子網, 重複步驟2。

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>匯入 CSV 檔案以將子網與網路網站建立關聯

1. 建立包含您要新增之所有子網的 CSV 檔案。 例如, 建立名為**subnet**的檔案, 並提供下列內容:

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。

3. 執行下列 Cmdlet 以匯入**子網 .csv**, 然後將其內容儲存在 Lync Server 管理儲存區:

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 將子網與網路網站建立關聯

1. 開啟商務用 Skype Server 的 [控制台]。

2. 在左側導覽列中, 按一下 [**網路**設定]。

3. 按一下**子網**導覽按鈕。

4. 按一下 [**新增**]。

5. 在 [**新的子網**] 頁面上, 按一下 [**子網識別碼**], 然後在您想要與網路網站建立關聯的子網所定義的 IP 位址範圍中輸入第一個位址。

6. 按一下 [**遮罩**], 然後輸入要套用至子網的位元遮罩。

7. 按一下 [**網路網站識別碼**], 然後選取您要新增此子網的網站的 [網站識別碼]。

    > [!NOTE]
    > 如果您尚未建立網路網站, 此清單將會是空白的。 如需程式的詳細資訊, 請參閱[建立或修改網路網站](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)。 您也可以執行**CsNetworkSite** Cmdlet, 以取得您的部署的網站識別碼。 如需詳細資訊, 請參閱商務用 Skype Server 管理命令介面檔。

8. 或者, 按一下 [**描述**], 然後輸入說明這個子網上的其他資訊。

9. 按一下 [認可]****。

重複這些步驟, 將其他子網新增至網路網站。
> [!NOTE]
> 會產生一個金鑰健康情況指標 (KHI) 警示, 指定您網路中存在的 IP 位址清單, 但不與子網建立關聯, 或者包含 IP 位址的子網不與網路網站產生關聯。 在8小時內, 不會多次引發此通知。

相關的警示資訊和範例如下所示:

 **來源**: CS 頻寬原則服務 (核心)

 **事件號碼**: 36034

 **層級**: 2

 **描述**: 下列 ip 位址的子網: \<未設定 ip 位址\>清單, 或子網不與網路網站相關聯。

 **原因**: 網路設定中缺少對應 IP 位址的子網, 或子網不會與網路網站產生關聯。

 **解決**方式: 將與 IP 位址清單相對應的子網新增至 [網路設定], 並將每個子網與網路網站建立關聯。

例如, 如果警示中的 IP 位址清單指定10.121.248.226 和 10.121.249.20, 則這些 IP 位址不會與子閘道聯, 或與其相關聯的子網不屬於網路網站。 如果 10.121.248.0/24 和 10.121.249.0/24 是這些位址對應的子網, 您可以解決此問題, 如下所示:

1. 請確定 IP 位址10.121.248.226 已與 10.121.249.0/24 子網相關聯的 10.121.248.0/24 子網和 IP 位址10.121.249.20 相關聯。

2. 請確定 10.121.248.0/24 和 10.121.249.0/24 子網分別與網路網站產生關聯。

## <a name="see-also"></a>另請參閱
<a name="BKMK_AssociateSubnets"> </a>


[新-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[移除-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[新-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[移除-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

