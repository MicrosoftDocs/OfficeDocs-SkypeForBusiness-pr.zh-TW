---
title: 在商務用 Skype 中部署網路地區、網站和子網
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 在商務用 Skype Server 中建立或修改網路地區、網路網站和關聯網路子網。 所有這些都是用於高級企業語音功能：媒體旁路、通話許可控制和位置基礎路由。
---

# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>在商務用 Skype 中部署網路地區、網站和子網

在商務用 Skype Server 中建立或修改網路地區、網路網站和關聯網路子網。 所有這些都是用於高級企業語音功能：媒體旁路、通話許可控制和位置基礎路由。

「高級企業語音」功能是[通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)、[媒體旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)、[位置基礎路由](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)和[E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md)。 這些功能全部都需要您建立網路地區、網路網站和子網。 例如，所有這些功能都要求拓撲中的每個子網都與特定網路網站相關聯，而且每個網路網站都必須與網路地區產生關聯。 如需這些術語的詳細資訊，請參閱[商務用 Skype Server 中的「高級企業語音功能的網路設定](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)。

通話許可控制及 E9-1-1 具有其他的網站設定需求：

- 通話許可控制需要指定透過 WAN 頻寬限制所限制之每個網站的「頻寬原則設定檔」。 如果您打算部署通話許可控制，您必須先[在商務用 Skype Server 中建立頻寬原則設定檔](create-bandwidth-policy-profiles.md)，再設定網路網站。

- E9-1-1 需要指定每個網站的「位置原則」。 如果您打算部署 E9-1-1，您必須先[在商務用 Skype Server 中建立位置原則](create-location-policies.md)，然後才能設定網路網站。

## <a name="create-or-modify-a-network-region"></a>建立或修改網路地區

如果您已經為這些功能之一建立網路地區，則不需要建立新的網路地區;其他的「高級企業語音功能會使用相同的網路地區。

不過，您必須修改現有的網路區域定義，以套用功能特定的設定。 例如，您已為 E9-1-1 (其不需要相關的中央網站) 建立網路區域，而您接著要部署通話許可控制，您便必須修改網路區域定義來指定中央網站。

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面建立網路地區

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

2. 執行 New-CsNetworkRegion Cmdlet 來建立網路地區：

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    例如：

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    在此範例中，您會建立一個名為「NorthAmerica」的網路地區，該網路地區與網站識別碼芝加哥相關聯的中央網站。

3. 若要完成建立拓撲的網路地區，請使用每個網路地區的設定重複步驟2。

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立網路地區

1. 開啟商務用 Skype Server 控制台]。

2. 在左導覽列中，按一下 **[網路組態]**。

3. 按一下 [ **地區**]。

4. 按一下 [ **新增**]。

5. 在 [ **新地區** ] 頁面上，按一下 [ **名稱** ]，然後輸入網路地區的名稱。

6. 按一下 [ **中央網站**]，然後按一下清單中的中央網站。

7. (選用) 按一下 **[描述]**，然後輸入用來描述此網站的其他資訊。

8. 按一下 **[認可]**。

9. 若要完成建立拓撲的網路地區，請使用其他地區的設定重複步驟4到8。

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面修改網路地區

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

2. 執行 Set-CsNetworkRegion Cmdlet 以修改現有的網路地區：

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    例如：

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    在此範例中，您會使用本) 主題稍早的程式（透過變更描述）來建立名為「NorthAmerica」 (的現有網路地區。 如果「NorthAmerica」區域的描述存在，此命令會以此值覆寫該描述。如果未設定任何描述，則此命令會將其設定。

3. 若要修改其他網路地區，請使用其他地區的設定重複步驟2。

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台修改網路地區

1. 開啟商務用 Skype Server 控制台]。

2. 在左導覽列中，按一下 **[網路組態]**。

3. 按一下 [ **地區** ] 導覽按鈕。

4. 在表格中，按一下您要修改的網路地區。

5. 按一下 **[編輯]**，然後按一下 **[顯示詳細資料...]**。

6. 在 [ **編輯地區** ] 頁面上，視需要變更此網路地區的設定值。

7. 按一下 **[認可]**。

8. 若要完成修改網路地區，請使用其他地區的設定重複步驟4到7。

## <a name="create-or-modify-a-network-site"></a>建立或修改網路網站

如果您已建立這些功能的網站，則不需要建立新的網路網站;其他的高級企業語音功能會使用相同的網路網站。 不過，您可能需要修改現有網站定義，以便套用特定的功能設定。 例如，如果已為 E9-1-1 建立了網站，在部署通話許可控制期間需要修改網站，以便套用頻寬原則設定檔。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面建立網路網站

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

2. 執行 New-CsNetworkSite Cmdlet 建立網站：

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    例如：

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    在此範例中，您已在「NorthAmerica」網路地區中建立名為 "芝加哥" 的網路網站。

    > [!NOTE]
    > 「北美地區」網路地區必須已經存在，此命令才能成功執行。

3. 使用其他網站的設定重複執行步驟 2，完成建立拓撲的網站。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立網路網站

1. 開啟商務用 Skype Server 控制台]。

2. 在左導覽列中，按一下 **[網路組態]**。

3. 按一下 **[站台]** 導覽按鈕。

4. 按一下 **[新增]**。

5. 在 **[新增站台]** 頁面上，按一下 **[名稱]**，然後為網站輸入名稱。

6. 按一下 **[地區]**，然後按一下清單中的地區。

7. (選用) 按一下 **[頻寬原則]**，然後按一下清單中的頻寬原則。

    > [!NOTE]
    > 如果您要在網站部署通話許可控制，才需要頻寬原則。

8. (選用) 按一下 **[位置原則]**，然後按一下清單中的位置原則。

    > [!NOTE]
    > 如果您要在網站部署 E9-1-1，才需要位置原則。

9. (選用) 按一下 **[描述]**，然後輸入用來描述此網站的其他資訊。

10. 按一下 **[認可]**。

11. 使用其他網站的設定重複執行步驟 4 至 10，完成建立拓撲的網站。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面來修改網路網站

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

2. 執行 Set-CsNetworkSite Cmdlet 以修改網站：

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    例如：

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    在此範例中，名為 "阿布奎基" 的網站會移至「NorthAmerica」網路地區。 若要修改網站設定以便部署通話許可控制、E9-1-1 或媒體旁路，請執行 Set-CsNetworkSite Cmdlet 並分別搭配 BWPolicyProfileID 或 LocationPolicy 參數，修改網站設定。

    > [!NOTE]
    > 媒體旁路還有一個 BypassID 參數，但強烈建議您不要覆寫自動產生的旁路 ID。為媒體旁路設定網站時，不需要指定其他參數。

3. 使用其他網站的設定重複執行步驟 2，完成修改拓撲的網站。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台修改網路網站

1. 開啟商務用 Skype Server 控制台]。

2. 在左導覽列中，按一下 **[網路組態]**。

3. 按一下 **[站台]** 導覽按鈕。

4. 在表格中，按一下您要修改的網站。

5. 按一下 **[編輯]**，然後按一下 **[顯示詳細資料...]**。

6. 在 [ **編輯網站** ] 頁面上，視需要變更此網路網站的設定值。

7. 按一下 **[認可]**。

8. 使用其他網站的設定重複執行步驟 4 至 7，完成修改網站。

## <a name="associate-a-subnet-with-a-network-site"></a>建立子網與網路網站的關聯
<a name="BKMK_AssociateSubnets"> </a>

您網路中的每個子網都必須與特定網路網站產生關聯，因為子網資訊是用來決定端點所在的網路網站，而啟動新的會話時。 在會話中每一方的位置已知時，「高級企業語音功能會套用該資訊，以決定如何處理通話設定或路由傳送。

您部署中 Audio/Video Edge Server 的所有已設定公用 IP 位址，都必須新增至您的網路設定。 這兩個 IP 位址會新增為遮罩為32的子網。 相關聯的網路網站應該對應至適當設定的網站。 例如，與中央網站芝加哥的 A/V Edge service 對應的公用 IP 位址，將會 NetworkSiteID 芝加哥。

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面建立子網與網路網站的關聯

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

2. 執行 **New-CsNetworkSubnet** Cmdlet 以將子網與網路網站產生關聯：

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    例如：

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    在此範例中，您已建立子網172.11.12.13 與網路網站 "芝加哥" 之間的關聯性。

3. 對拓撲中的所有子網重複步驟2。

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>若要將子網與網站結合匯入 CSV 檔案

1. 建立包含您要新增之所有子網的 CSV 檔案。 例如，使用下列內容建立名為 **subnet.csv** 的檔案：

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

3. 執行下列 Cmdlet 以匯入 **subnet.csv**，然後將其內容儲存在 Lync Server management store 中：

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立子網與網路網站的關聯

1. 開啟商務用 Skype Server 控制台]。

2. 在左導覽列中，按一下 **[網路組態]**。

3. 按一下 [ **子網** ] 導覽按鈕。

4. 按一下 [ **新增**]。

5. 在 [ **新建子網上** ] 頁面上，按一下 [ **子網識別碼**]，然後輸入您要與網路網站建立關聯之子網所定義之 IP 位址範圍中的第一個位址。

6. 按一下 [ **遮罩**]，然後輸入要套用至子網的位元遮罩。

7. 按一下 [ **網路網站識別碼**]，然後選取您要新增此子網的網站的網站識別碼。

    > [!NOTE]
    > 如果您尚未建立網路網站，此清單將會是空的。 如需程式的詳細資訊，請參閱 [建立或修改網路網站](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site)。 您也可以執行 **Get-CsNetworkSite** Cmdlet，以取得部署的網站 IDs。 如需詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。

8. （選用）按一下 [ **描述**]，然後輸入其他資訊以描述這個子網。

9. 按一下 **[認可]**。

重複這些步驟，將其他子網新增至網路網站。
> [!NOTE]
> 會引發重要狀態指示器 (KHI) 通知，指定存在於您的網路中，但未與子網路相關聯，或包含 IP 位址的子網路未與網站相關聯的 IP 位址清單。 在8小時內，將不會多次引發此警示。

以下是相關的通知資訊與範例：

 **來源**：CS 頻寬原則服務 (核心)

 **事件號碼**：36034

 **層級**：2

 **描述**：下列 IP 位址的子網： \<List of IP Addresses\> 未設定，或子網未與網路網站產生關聯。

 **原因**：網路組態設定中遺漏對應 IP 位址的子網路，或是子網路未與網站相關聯。

 **解決** 方式：將對應至 IP 位址清單的子網新增至網路設定設定，並將每個子網與網路網站產生關聯。

例如，如果警示中的 IP 位址清單指定10.121.248.226 和10.121.249.20，則這些 IP 位址不會與子網產生關聯，或與其相關聯的子網不屬於網路網站。 如果 10.121.248.0/24 與 10.121.249.0/24 是這些位址的對應子網路，您可以透過下列方式解決此問題：

1. 確定 IP 位址 10.121.248.226 與 10.121.248.0/24 子網路相關聯，而 IP 位址 10.121.249.20 與 10.121.249.0/24 子網路相關聯。

2. 確定 10.121.248.0/24 與 10.121.249.0/24 兩個子網路分別與一個網站相關聯。

## <a name="see-also"></a>另請參閱
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)