---
title: 在商務用 Skype Server 中設定位置資料庫
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
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: 在商務用 Skype Server Enterprise Voice 中, 設定、填入及發佈 E9-1-1 位置資料庫。
ms.openlocfilehash: 82182a27c1459005d19c8a50d0a1babc83b178c9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193274"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="26692-103">在商務用 Skype Server 中設定位置資料庫</span><span class="sxs-lookup"><span data-stu-id="26692-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="26692-104">在商務用 Skype Server Enterprise Voice 中, 設定、填入及發佈 E9-1-1 位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="26692-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="26692-105">若要讓用戶端能在網路中自動偵測其位置, 您必須先設定位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="26692-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="26692-106">若要設定位置資料庫, 請執行下列任務:</span><span class="sxs-lookup"><span data-stu-id="26692-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="26692-107">使用網路元素對應至位置來填入資料庫。</span><span class="sxs-lookup"><span data-stu-id="26692-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="26692-108">如果您使用緊急位置身分識別號碼 (ELIN) 閘道, 您必須在 [ \<公司名稱\> ] 欄位中包含該 ELIN。</span><span class="sxs-lookup"><span data-stu-id="26692-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="26692-109">如果您沒有填入位置資料庫, 且位置原則中**所需的位置**設定為 **[是]** 或 [**免責聲明**], 則用戶端會提示使用者手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="26692-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="26692-110">根據 E9-1-1 服務提供者所維護的主要街道位址指南 (MSAG) 驗證位址。</span><span class="sxs-lookup"><span data-stu-id="26692-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="26692-111">發佈更新後的資料庫。</span><span class="sxs-lookup"><span data-stu-id="26692-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="26692-112">填入位置資料庫</span><span class="sxs-lookup"><span data-stu-id="26692-112">Populate the location database</span></span>

<span data-ttu-id="26692-113">若要在網路中自動找到用戶端, 您必須先使用網路 wiremap 填入位置資料庫, 並將網元對應至市政 (亦即街道) 位址。</span><span class="sxs-lookup"><span data-stu-id="26692-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="26692-114">您可以使用子網、無線存取點、開關和埠來定義 wiremap。</span><span class="sxs-lookup"><span data-stu-id="26692-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="26692-115">您可以個別地將位址新增到位置資料庫, 或使用包含下表所述之欄格式的 CSV 檔案, 大量新增位址。</span><span class="sxs-lookup"><span data-stu-id="26692-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="26692-116">如果您使用緊急位置識別號碼 (ELIN) 閘道, 請在 [**公司名稱**] 欄位中, 為每個位置加入 ELIN。</span><span class="sxs-lookup"><span data-stu-id="26692-116">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="26692-117">您可以在每個位置包含多個 ELINs, 並以分號分隔。</span><span class="sxs-lookup"><span data-stu-id="26692-117">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="26692-118">**Network 元素**</span><span class="sxs-lookup"><span data-stu-id="26692-118">**Network Element**</span></span>|<span data-ttu-id="26692-119">**必要欄**</span><span class="sxs-lookup"><span data-stu-id="26692-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="26692-120">**無線存取點**</span><span class="sxs-lookup"><span data-stu-id="26692-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="26692-121">\<BSSID\>、\<描述\>、\<位置\>、\<公司\>名稱\<、\>HouseNumber\<、\>HouseNumberSuffix\<、\>PreDirectional,.。。</span><span class="sxs-lookup"><span data-stu-id="26692-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="26692-122">...\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<City\>、\<State\>、\<郵遞區號\>、\<國家/地區\></span><span class="sxs-lookup"><span data-stu-id="26692-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="26692-123">**端子**</span><span class="sxs-lookup"><span data-stu-id="26692-123">**Subnet**</span></span> <br/> |<span data-ttu-id="26692-124">\<子\>網\<、\>描述\<、\>位置\<、\>公司\<名稱\>、\<HouseNumber\>、\<HouseNumberSuffix\>、PreDirectional,.。。</span><span class="sxs-lookup"><span data-stu-id="26692-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="26692-125">...\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<City\>、\<State\>、\<郵遞區號\>、\<國家/地區\></span><span class="sxs-lookup"><span data-stu-id="26692-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="26692-126">**通道**</span><span class="sxs-lookup"><span data-stu-id="26692-126">**Port**</span></span> <br/> |<span data-ttu-id="26692-127">\<ChassisID\>、\<PortIDSubType\>、\<PortID\>、\<描述\>、\<位置\>、\<公司\>名稱\<、\>HouseNumber\< 、HouseNumberSuffix\>,.。。</span><span class="sxs-lookup"><span data-stu-id="26692-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="26692-128">...\<PreDirectional\>、\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<City\>、\<State\>、\<\>郵遞區號\<國家\></span><span class="sxs-lookup"><span data-stu-id="26692-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="26692-129">**Switch**</span><span class="sxs-lookup"><span data-stu-id="26692-129">**Switch**</span></span> <br/> |<span data-ttu-id="26692-130">\<ChassisID\>、\<描述\>、\<位置\>、\<公司\>名稱\<、\>HouseNumber\<、\>HouseNumberSuffix\<、\>PreDirectional,.。。</span><span class="sxs-lookup"><span data-stu-id="26692-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="26692-131">...\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<City\>、\<State\>、\<郵遞區號\>、\<國家/地區\></span><span class="sxs-lookup"><span data-stu-id="26692-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="26692-132">在位置資料庫中新增網路元素</span><span class="sxs-lookup"><span data-stu-id="26692-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="26692-133">執行下列 Cmdlet, 將子網位置新增至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="26692-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="26692-134">針對 ELIN 閘道, 請將 ELIN 放在 [公司名稱] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="26692-134">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="26692-135">您可以包含一個以上的 ELIN。</span><span class="sxs-lookup"><span data-stu-id="26692-135">You can include more than one ELIN.</span></span> <span data-ttu-id="26692-136">例如：</span><span class="sxs-lookup"><span data-stu-id="26692-136">For example:</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="26692-137">或者, 您也可以執行下列 Cmdlet, 並使用名為「subnet .csv」的檔案來大量更新子網位置。</span><span class="sxs-lookup"><span data-stu-id="26692-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="26692-138">執行下列 Cmdlet, 以將無線位置新增至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="26692-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="26692-139">或者, 您可以執行下列 Cmdlet, 並使用名為 "waps" 的檔案來大量更新無線位置。</span><span class="sxs-lookup"><span data-stu-id="26692-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="26692-140">執行下列 Cmdlet, 將切換位置新增到位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="26692-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="26692-141">或者, 您也可以執行下列 Cmdlet, 並使用一個名為 "users.csv" 的檔案來大量更新切換位置。</span><span class="sxs-lookup"><span data-stu-id="26692-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="26692-142">執行下列 Cmdlet 以將埠位置新增到位置資料庫</span><span class="sxs-lookup"><span data-stu-id="26692-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="26692-143">PortIDSubType 的預設值是 LocallyAssigned。</span><span class="sxs-lookup"><span data-stu-id="26692-143">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="26692-144">您也可以將它設定為 InterfaceAlias 或 InterfaceName</span><span class="sxs-lookup"><span data-stu-id="26692-144">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="26692-145">或者, 您可以執行下列 Cmdlet, 並使用名為「埠 .csv」的檔案來大量更新埠位置。</span><span class="sxs-lookup"><span data-stu-id="26692-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="26692-146">驗證位址</span><span class="sxs-lookup"><span data-stu-id="26692-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="26692-147">驗證位於位置資料庫中的位址</span><span class="sxs-lookup"><span data-stu-id="26692-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="26692-148">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="26692-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="26692-149">執行下列 Cmdlet 來設定緊急服務提供者連線。</span><span class="sxs-lookup"><span data-stu-id="26692-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="26692-150">執行下列 Cmdlet 以驗證位置資料庫中的位址。</span><span class="sxs-lookup"><span data-stu-id="26692-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="26692-151">您也可以使用**Test CsLisCivicAddress** Cmdlet 來驗證個別的位址。</span><span class="sxs-lookup"><span data-stu-id="26692-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="26692-152">發佈位置資料庫</span><span class="sxs-lookup"><span data-stu-id="26692-152">Publish the location database</span></span>

<span data-ttu-id="26692-153">您新增至位置資料庫的新位置將不會提供給用戶端, 直到它們發佈為止。</span><span class="sxs-lookup"><span data-stu-id="26692-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="26692-154">如果您使用緊急位置身分識別號碼 (ELIN) 閘道, 您也需要將 ELINs 上傳到您的公用交換電話網絡</span><span class="sxs-lookup"><span data-stu-id="26692-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="26692-155">您的 PSTN 載波可能會要求您針對 ELIN 記錄使用特定的格式。</span><span class="sxs-lookup"><span data-stu-id="26692-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="26692-156">如需詳細資訊, 請與您的 PSTN 運營商聯繫。</span><span class="sxs-lookup"><span data-stu-id="26692-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="26692-157">您可以從位置資訊服務資料庫匯出記錄, 並根據需要設定其格式。</span><span class="sxs-lookup"><span data-stu-id="26692-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="26692-158">發佈位置資料庫</span><span class="sxs-lookup"><span data-stu-id="26692-158">To publish the location database</span></span>

-  <span data-ttu-id="26692-159">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="26692-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="26692-160">執行下列 Cmdlet 來發佈位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="26692-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```
  Publish-CsLisConfiguration
  ```


