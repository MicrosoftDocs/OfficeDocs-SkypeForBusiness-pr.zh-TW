---
title: 在商務用 Skype Server 中設定位置資料庫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 在商務用 Skype Server 企業語音中，設定、填入及發佈 E9-1-1 位置資料庫。
ms.openlocfilehash: 0eb2fd8e09c09688cf8c8282b35328ca7eb1761b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597737"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>在商務用 Skype Server 中設定位置資料庫
 
在商務用 Skype Server 企業語音中，設定、填入及發佈 E9-1-1 位置資料庫。 
  
若要讓用戶端自動偵測網路內部的位置，您必須先設定位置資料庫。 
  
若要設定位置資料庫，請執行下列工作：
  
- 以網元對應至位置，填入資料庫。 如果您使用緊急位置識別號碼 (ELIN) 閘道，您必須在欄位中包含 ELIN \<CompanyName\> 。
    
    如果您未填入位置資料庫，且位置原則中 **所需的位置** 設定為 **[是]** 或 [ **免責聲明**]，用戶端將會提示使用者手動輸入位置。
    
- 對照主要街道通訊指南 (MSAG) 來驗證 E9-1-1 服務提供者所維護的位址。
    
- 發佈更新的資料庫。
    
## <a name="populate-the-location-database"></a>填入位置資料庫

若要自動在網路中尋找用戶端，您必須先以網路線路圖填入位置資料庫，它會將網路元素對應至市政 (，也就是街道) 位址。 您可以使用子網、無線存取點、開關及埠來定義線路圖。
  
您可以個別地將位址新增至位置資料庫，或是使用包含下表所述欄格式的 CSV 檔案大量新增位址。
  
如果您使用緊急位置識別號碼 (ELIN) 閘道，請在每個位置的 [ **CompanyName** ] 欄位中包含 ELIN。 您可以在每個位置中包含多個 Elin，每個位置都是以分號分隔。
  
|**網元**|**必要欄**|
|:-----|:-----|
|**無線存取點** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**子網路** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Port** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…  <br/> …\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**參數** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>若要將網路元素新增至位置資料庫

1. 執行下列 Cmdlet，將子網位置新增至位置資料庫。
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    若為 ELIN 閘道，請將 ELIN 放在 [CompanyName] 欄位中。 您可以包含一個以上的 ELIN。 例如：
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    或者，您也可以執行下列指令程式，並使用名為 "subnets.csv" 的檔案大量更新子網位置。
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. 執行下列 Cmdlet，將無線位置新增至位置資料庫。
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   或者，您也可以執行下列指令程式，並使用名為 "waps.csv" 的檔案大量更新無線位置。
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. 執行下列 Cmdlet，將切換位置新增至位置資料庫。
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   或者，您也可以執行下列指令程式，並使用名為 "switches.csv" 的檔案大量更新切換位置。
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. 執行下列 Cmdlet，將埠位置新增至位置資料庫
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   PortIDSubType 的預設值為 LocallyAssigned。 您也可以將它設定為 InterfaceAlias 或 InterfaceName
    
   或者，您也可以執行下列指令程式，並使用名為 "ports.csv" 的檔案大量更新埠位置。
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>驗證位址

### <a name="to-validate-addresses-located-in-the-location-database"></a>驗證位於位置資料庫中的位址

1.  啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 執行下列 Cmdlet 以設定緊急服務提供者連線。
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. 執行下列 Cmdlet 來驗證位置資料庫中的位址。
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   您也可以使用 **Test-CsLisCivicAddress** Cmdlet 來驗證個別的位址。
    
## <a name="publish-the-location-database"></a>發佈位置資料庫

在發佈之前，您新增至位置資料庫的新位置將不會供用戶端使用。
  
如果您使用緊急位置識別號碼 (ELIN) 閘道，您也必須將 Elin 上傳至您公用交換電話網路 (PSTN) 電信公司的自動位置識別， (阿裡) 資料庫。 您的 PSTN 電信公司可能需要使用特定的 ELIN 記錄格式。 如需詳細資訊，請與您的 PSTN 電信公司聯繫。 您可以匯出位置資訊服務資料庫中的記錄，並視需要進行格式化。
  
### <a name="to-publish-the-location-database"></a>發佈位置資料庫

-  啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
- 執行下列 Cmdlet 來發佈位置資料庫。
    
  ```powershell
  Publish-CsLisConfiguration
  ```


