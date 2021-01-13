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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: 在商務用 Skype Server Enterprise Voice 中，設定、填入及發佈 E9-1-1 位置資料庫。
ms.openlocfilehash: 70158864446c12b2e7636a2962aced05d87c49a0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804083"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="77372-103">在商務用 Skype Server 中設定位置資料庫</span><span class="sxs-lookup"><span data-stu-id="77372-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="77372-104">在商務用 Skype Server Enterprise Voice 中，設定、填入及發佈 E9-1-1 位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="77372-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="77372-105">若要讓用戶端自動偵測網路內部的位置，您必須先設定位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="77372-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="77372-106">若要設定位置資料庫，請執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="77372-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="77372-107">以網元對應至位置，填入資料庫。</span><span class="sxs-lookup"><span data-stu-id="77372-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="77372-108">如果您使用緊急位置識別號碼 (ELIN) 閘道，您必須在欄位中包含 ELIN \<CompanyName\> 。</span><span class="sxs-lookup"><span data-stu-id="77372-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="77372-109">如果您未填入位置資料庫，且位置原則中 **所需的位置** 設定為 **[是]** 或 [ **免責聲明**]，用戶端將會提示使用者手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="77372-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="77372-110">對照主要街道通訊指南 (MSAG) 來驗證 E9-1-1 服務提供者所維護的位址。</span><span class="sxs-lookup"><span data-stu-id="77372-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="77372-111">發佈更新的資料庫。</span><span class="sxs-lookup"><span data-stu-id="77372-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="77372-112">填入位置資料庫</span><span class="sxs-lookup"><span data-stu-id="77372-112">Populate the location database</span></span>

<span data-ttu-id="77372-113">若要自動在網路中尋找用戶端，您必須先以網路線路圖填入位置資料庫，它會將網路元素對應至市政 (，也就是街道) 位址。</span><span class="sxs-lookup"><span data-stu-id="77372-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="77372-114">您可以使用子網、無線存取點、開關及埠來定義線路圖。</span><span class="sxs-lookup"><span data-stu-id="77372-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="77372-115">您可以個別地將位址新增至位置資料庫，或是使用包含下表所述欄格式的 CSV 檔案大量新增位址。</span><span class="sxs-lookup"><span data-stu-id="77372-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="77372-116">如果您使用緊急位置識別號碼 (ELIN) 閘道，請在每個位置的 [ **CompanyName** ] 欄位中包含 ELIN。</span><span class="sxs-lookup"><span data-stu-id="77372-116">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="77372-117">您可以在每個位置中包含多個 Elin，每個位置都是以分號分隔。</span><span class="sxs-lookup"><span data-stu-id="77372-117">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="77372-118">**網元**</span><span class="sxs-lookup"><span data-stu-id="77372-118">**Network Element**</span></span>|<span data-ttu-id="77372-119">**必要欄**</span><span class="sxs-lookup"><span data-stu-id="77372-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77372-120">**無線存取點**</span><span class="sxs-lookup"><span data-stu-id="77372-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="77372-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="77372-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="77372-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="77372-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="77372-123">**子網路**</span><span class="sxs-lookup"><span data-stu-id="77372-123">**Subnet**</span></span> <br/> |<span data-ttu-id="77372-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="77372-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="77372-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="77372-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="77372-126">**Port**</span><span class="sxs-lookup"><span data-stu-id="77372-126">**Port**</span></span> <br/> |<span data-ttu-id="77372-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span><span class="sxs-lookup"><span data-stu-id="77372-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="77372-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="77372-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="77372-129">**參數**</span><span class="sxs-lookup"><span data-stu-id="77372-129">**Switch**</span></span> <br/> |<span data-ttu-id="77372-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="77372-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="77372-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="77372-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="77372-132">若要將網路元素新增至位置資料庫</span><span class="sxs-lookup"><span data-stu-id="77372-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="77372-133">執行下列 Cmdlet，將子網位置新增至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="77372-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="77372-134">若為 ELIN 閘道，請將 ELIN 放在 [CompanyName] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="77372-134">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="77372-135">您可以包含一個以上的 ELIN。</span><span class="sxs-lookup"><span data-stu-id="77372-135">You can include more than one ELIN.</span></span> <span data-ttu-id="77372-136">例如：</span><span class="sxs-lookup"><span data-stu-id="77372-136">For example:</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="77372-137">或者，您也可以執行下列指令程式，並使用名為 "subnets.csv" 的檔案大量更新子網位置。</span><span class="sxs-lookup"><span data-stu-id="77372-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="77372-138">執行下列 Cmdlet，將無線位置新增至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="77372-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="77372-139">或者，您也可以執行下列指令程式，並使用名為 "waps.csv" 的檔案大量更新無線位置。</span><span class="sxs-lookup"><span data-stu-id="77372-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="77372-140">執行下列 Cmdlet，將切換位置新增至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="77372-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="77372-141">或者，您也可以執行下列指令程式，並使用名為 "switches.csv" 的檔案大量更新切換位置。</span><span class="sxs-lookup"><span data-stu-id="77372-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="77372-142">執行下列 Cmdlet，將埠位置新增至位置資料庫</span><span class="sxs-lookup"><span data-stu-id="77372-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="77372-143">PortIDSubType 的預設值為 LocallyAssigned。</span><span class="sxs-lookup"><span data-stu-id="77372-143">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="77372-144">您也可以將它設定為 InterfaceAlias 或 InterfaceName</span><span class="sxs-lookup"><span data-stu-id="77372-144">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="77372-145">或者，您也可以執行下列指令程式，並使用名為 "ports.csv" 的檔案大量更新埠位置。</span><span class="sxs-lookup"><span data-stu-id="77372-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="77372-146">驗證位址</span><span class="sxs-lookup"><span data-stu-id="77372-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="77372-147">驗證位於位置資料庫中的位址</span><span class="sxs-lookup"><span data-stu-id="77372-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="77372-148">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="77372-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="77372-149">執行下列 Cmdlet 以設定緊急服務提供者連線。</span><span class="sxs-lookup"><span data-stu-id="77372-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="77372-150">執行下列 Cmdlet 來驗證位置資料庫中的位址。</span><span class="sxs-lookup"><span data-stu-id="77372-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="77372-151">您也可以使用 **Test-CsLisCivicAddress** Cmdlet 來驗證個別的位址。</span><span class="sxs-lookup"><span data-stu-id="77372-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="77372-152">發佈位置資料庫</span><span class="sxs-lookup"><span data-stu-id="77372-152">Publish the location database</span></span>

<span data-ttu-id="77372-153">在發佈之前，您新增至位置資料庫的新位置將不會供用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="77372-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="77372-154">如果您使用緊急位置識別號碼 (ELIN) 閘道，您也必須將 Elin 上傳至您公用交換電話網路 (PSTN) 電信公司的自動位置識別， (阿裡) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="77372-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="77372-155">您的 PSTN 電信公司可能需要使用特定的 ELIN 記錄格式。</span><span class="sxs-lookup"><span data-stu-id="77372-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="77372-156">如需詳細資訊，請與您的 PSTN 電信公司聯繫。</span><span class="sxs-lookup"><span data-stu-id="77372-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="77372-157">您可以匯出位置資訊服務資料庫中的記錄，並視需要進行格式化。</span><span class="sxs-lookup"><span data-stu-id="77372-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="77372-158">發佈位置資料庫</span><span class="sxs-lookup"><span data-stu-id="77372-158">To publish the location database</span></span>

-  <span data-ttu-id="77372-159">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="77372-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="77372-160">執行下列 Cmdlet 來發佈位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="77372-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```powershell
  Publish-CsLisConfiguration
  ```


