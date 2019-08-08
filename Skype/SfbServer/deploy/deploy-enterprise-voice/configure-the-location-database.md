---
title: 在商務用 Skype Server 中設定位置資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: 在商務用 Skype Server Enterprise Voice 中, 設定、填入及發佈 E9-1-1 位置資料庫。
ms.openlocfilehash: 36ddd57e39b51171581c0c6316f165f44879e3f9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233891"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>在商務用 Skype Server 中設定位置資料庫
 
在商務用 Skype Server Enterprise Voice 中, 設定、填入及發佈 E9-1-1 位置資料庫。 
  
若要讓用戶端能在網路中自動偵測其位置, 您必須先設定位置資料庫。 
  
若要設定位置資料庫, 請執行下列任務:
  
- 使用網路元素對應至位置來填入資料庫。 如果您使用緊急位置身分識別號碼 (ELIN) 閘道, 您必須在 [ \<公司名稱\> ] 欄位中包含該 ELIN。
    
    如果您沒有填入位置資料庫, 且位置原則中**所需的位置**設定為 **[是]** 或 [**免責聲明**], 則用戶端會提示使用者手動輸入位置。
    
- 根據 E9-1-1 服務提供者所維護的主要街道位址指南 (MSAG) 驗證位址。
    
- 發佈更新後的資料庫。
    
## <a name="populate-the-location-database"></a>填入位置資料庫

若要在網路中自動找到用戶端, 您必須先使用網路 wiremap 填入位置資料庫, 並將網元對應至市政 (亦即街道) 位址。 您可以使用子網、無線存取點、開關和埠來定義 wiremap。
  
您可以個別地將位址新增到位置資料庫, 或使用包含下表所述之欄格式的 CSV 檔案, 大量新增位址。
  
如果您使用緊急位置識別號碼 (ELIN) 閘道, 請在 [**公司名稱**] 欄位中, 為每個位置加入 ELIN。 您可以在每個位置包含多個 ELINs, 並以分號分隔。
  
|**Network 元素**|**必要欄**|
|:-----|:-----|
|**無線存取點** <br/> |\<BSSID\>、\<描述\>、\<位置\>、\<公司\>名稱\<、\>HouseNumber\<、\>HouseNumberSuffix\<、\>PreDirectional,.。。  <br/> ...\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<City\>、\<State\>、\<郵遞區號\>、\<國家/地區\>  <br/> |
|**端子** <br/> |\<子\>網\<、\>描述\<、\>位置\<、\>公司\<名稱\>、\<HouseNumber\>、\<HouseNumberSuffix\>、PreDirectional,.。。  <br/> ...\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<City\>、\<State\>、\<郵遞區號\>、\<國家/地區\>  <br/> |
|**通道** <br/> |\<ChassisID\>、\<PortIDSubType\>、\<PortID\>、\<描述\>、\<位置\>、\<公司\>名稱\<、\>HouseNumber\< 、HouseNumberSuffix\>,.。。  <br/> ...\<PreDirectional\>、\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<City\>、\<State\>、\<\>郵遞區號\<國家\>  <br/> |
|**Switch** <br/> |\<ChassisID\>、\<描述\>、\<位置\>、\<公司\>名稱\<、\>HouseNumber\<、\>HouseNumberSuffix\<、\>PreDirectional,.。。  <br/> ...\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<City\>、\<State\>、\<郵遞區號\>、\<國家/地區\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>在位置資料庫中新增網路元素

1. 執行下列 Cmdlet, 將子網位置新增至位置資料庫。
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    針對 ELIN 閘道, 請將 ELIN 放在 [公司名稱] 欄位中。 您可以包含一個以上的 ELIN。 例如：
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    或者, 您也可以執行下列 Cmdlet, 並使用名為「subnet .csv」的檔案來大量更新子網位置。
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. 執行下列 Cmdlet, 以將無線位置新增至位置資料庫。
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   或者, 您可以執行下列 Cmdlet, 並使用名為 "waps" 的檔案來大量更新無線位置。
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. 執行下列 Cmdlet, 將切換位置新增到位置資料庫。
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   或者, 您也可以執行下列 Cmdlet, 並使用一個名為 "users.csv" 的檔案來大量更新切換位置。
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. 執行下列 Cmdlet 以將埠位置新增到位置資料庫
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   PortIDSubType 的預設值是 LocallyAssigned。 您也可以將它設定為 InterfaceAlias 或 InterfaceName
    
   或者, 您可以執行下列 Cmdlet, 並使用名為「埠 .csv」的檔案來大量更新埠位置。
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>驗證位址

### <a name="to-validate-addresses-located-in-the-location-database"></a>驗證位於位置資料庫中的位址

1.  啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
2. 執行下列 Cmdlet 來設定緊急服務提供者連線。
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. 執行下列 Cmdlet 以驗證位置資料庫中的位址。
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   您也可以使用**Test CsLisCivicAddress** Cmdlet 來驗證個別的位址。
    
## <a name="publish-the-location-database"></a>發佈位置資料庫

您新增至位置資料庫的新位置將不會提供給用戶端, 直到它們發佈為止。
  
如果您使用緊急位置身分識別號碼 (ELIN) 閘道, 您也需要將 ELINs 上傳到您的公用交換電話網絡 您的 PSTN 載波可能會要求您針對 ELIN 記錄使用特定的格式。 如需詳細資訊, 請與您的 PSTN 運營商聯繫。 您可以從位置資訊服務資料庫匯出記錄, 並根據需要設定其格式。
  
### <a name="to-publish-the-location-database"></a>發佈位置資料庫

-  啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
- 執行下列 Cmdlet 來發佈位置資料庫。
    
  ```
  Publish-CsLisConfiguration
  ```


