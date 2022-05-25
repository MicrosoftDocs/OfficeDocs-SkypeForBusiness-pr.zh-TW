---
title: 在 商務用 Skype Server 中設定位置資料庫
ms.reviewer: ''
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
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: 在 商務用 Skype Server 企業語音 中設定、填入及發佈 E9-1-1 位置資料庫。
ms.openlocfilehash: fc7f53e1b62ec23e8075a9eac0d1158ee0143a5b
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671559"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>在 商務用 Skype Server 中設定位置資料庫
 
在 商務用 Skype Server 企業語音 中設定、填入及發佈 E9-1-1 位置資料庫。 
  
若要讓用戶端自動偵測其在網路中的位置，您必須先設定位置資料庫。 
  
若要設定位置資料庫，請執行下列工作：
  
- 在資料庫中填入網路元素與位置的對應。 如果您使用緊急位置識別碼 (ELIN) 閘道，則必須在 欄位中 \<CompanyName\> 包含 ELIN。
    
    如果您未填入位置資料庫，且 [位置原則] 中的 [ **需要的位置** ] 設定為 [ **是** ] 或 [ **免責聲明**]，用戶端會提示使用者手動輸入位置。
    
- 根據由 E9-1-1 服務提供者維護的 MSAG)  (主要街地道址指南來驗證位址。
    
- 發佈更新的資料庫。
    
## <a name="populate-the-location-database"></a>填入位置資料庫

若要自動找出網路內的用戶端，您必須先使用網路線條填入位置資料庫，以將網路元素對應至公民 (，也就是街道) 位址。 您可以使用子網、無線存取點、交換器和埠來定義 Wiremap。
  
您可以個別將位址新增至位置資料庫，或使用包含下表所述之資料行格式的 CSV 檔案大量新增位址。
  
如果您使用緊急位置識別碼 (ELIN) 閘道，請在每個位置的 **[公司名稱]** 欄位中包含 ELIN。 您可以為每個位置包含多個 ELIN，每個位置都以分號分隔。
  
|**Network 元素**|**必要資料行**|
|:-----|:-----|
|**無線存取點** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**子網路** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Port** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,...  <br/> ...\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**參數** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>將網路元素新增至位置資料庫

1. 執行下列 Cmdlet，將子網位置新增至位置資料庫。
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    針對 ELIN 閘道，請將 ELIN 放在 [公司名稱] 欄位中。 您可以包含多個 ELIN。 例如：
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    或者，您可以執行下列 Cmdlet，並使用名為 「subnets.csv」 的檔案來大量更新子網位置。
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. 執行下列 Cmdlet，將無線位置新增至位置資料庫。
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   或者，您可以執行下列 Cmdlet，並使用名為 「waps.csv」 的檔案來大量更新無線位置。
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. 執行下列 Cmdlet，將交換器位置新增至位置資料庫。
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   或者，您可以執行下列 Cmdlet，並使用名為 「switches.csv」 的檔案來大量更新交換器位置。
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. 執行下列 Cmdlet，將埠位置新增至位置資料庫
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   PortIDSubType 的預設值為 LocallyAssigned。 您也可以將它設定為 InterfaceAlias 或 InterfaceName
    
   或者，您可以執行下列 Cmdlet，並使用名為 「ports.csv」 的檔案來大量更新埠位置。
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>驗證位址

### <a name="to-validate-addresses-located-in-the-location-database"></a>驗證位置資料庫中的位址

1.  啟動商務用 Skype Server管理命令介面：依序按一下 [**開始**]、[**所有程式]** 和 **[商務用 Skype 2015**]，然後按一下 **[商務用 Skype Server 管理命令介面]**。
    
2. 執行下列 Cmdlet 來設定緊急服務提供者連線。
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. 執行下列 Cmdlet 來驗證位置資料庫中的位址。
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   您也可以使用 **Test-CsLisCivicAddress** Cmdlet 來驗證個別位址。
    
## <a name="publish-the-location-database"></a>發佈位置資料庫

您新增至位置資料庫的新位置在發佈之前，將無法提供給用戶端使用。
  
如果您使用緊急位置識別碼 (ELIN) 閘道，您也需要將 ELIN 上傳至公用交換電話網路絡 (PSTN) 電信業者的自動位置識別 (ALI) 資料庫。 您的 PSTN 貨運公司可能會要求您針對 ELIN 記錄使用特定格式。 如需詳細資訊，請連絡您的 PSTN 貨運公司。 您可以從位置資訊服務資料庫匯出記錄，並視需要加以格式化。
  
### <a name="to-publish-the-location-database"></a>若要發佈位置資料庫

-  啟動商務用 Skype Server管理命令介面：依序按一下 [**開始**]、[**所有程式]** 和 **[商務用 Skype 2015**]，然後按一下 **[商務用 Skype Server 管理命令介面]**。
    
- 執行下列 Cmdlet 以發佈位置資料庫。
    
  ```powershell
  Publish-CsLisConfiguration
  ```


