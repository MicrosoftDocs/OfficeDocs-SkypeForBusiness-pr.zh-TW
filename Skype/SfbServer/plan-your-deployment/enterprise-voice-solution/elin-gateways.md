---
title: 在商務用 Skype Server 中管理 ELIN 閘道的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: 在商務用 Skype Server Enterprise Voice 中使用 ELIN 閘道部署的位置資訊資料庫，或類似的外部資料庫來規劃 E9。
ms.openlocfilehash: 39e6c4170adc18687b284ec6f69a252c6efefab4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803033"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a><span data-ttu-id="2a7f9-103">在商務用 Skype Server 中管理 ELIN 閘道的位置</span><span class="sxs-lookup"><span data-stu-id="2a7f9-103">Manage locations for ELIN gateways in Skype for Business Server</span></span>

<span data-ttu-id="2a7f9-104">在商務用 Skype Server Enterprise Voice 中使用 ELIN 閘道部署的位置資訊資料庫，或類似的外部資料庫來規劃 E9。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-104">Decisions necessary for planning an the location information database, or a similar external database, for an E9-1-1 deployment using ELIN gateways, in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="2a7f9-105">若要讓商務用 Skype 伺服器自動為網路中的用戶端提供位置，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="2a7f9-105">To have Skype for Business Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

- <span data-ttu-id="2a7f9-106">使用網路 wiremap 填入位置資訊服務資料庫，並在 [公司名稱] 欄位中包含緊急位置識別號碼（ELINs）。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-106">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

- <span data-ttu-id="2a7f9-107">發佈位置，讓您的網路上的客戶可以使用它們。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-107">Publish the locations so that they are available for clients in your network.</span></span>

- <span data-ttu-id="2a7f9-108">將 ELINs 上傳到您的公用交換電話網絡（PSTN）電信公司的自動位置識別（阿裡）資料庫。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-108">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="2a7f9-109">如需如何執行這些工作的詳細資訊，請參閱在部署檔中[設定位置資料庫](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-109">For details about how to perform these tasks, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="2a7f9-110">除非已使用商務用 Skype Server Management Shell 命令發佈並複製到該池的本機存儲區，否則用戶端不能使用新增到中央位置資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-110">Locations added to the central location database are not available to the client until they have been published by using a Skype for Business Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="2a7f9-111">如需詳細資訊，請參閱在部署檔中[發佈位置資料庫](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-111">For details, see [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in the Deployment documentation.</span></span>

<span data-ttu-id="2a7f9-112">本節說明您規劃更新及維護位置資料庫時應考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-112">This section describes things to consider as you plan to update and maintain the location database.</span></span>

## <a name="planning-emergency-locations"></a><span data-ttu-id="2a7f9-113">規劃緊急位置</span><span class="sxs-lookup"><span data-stu-id="2a7f9-113">Planning Emergency Locations</span></span>

<span data-ttu-id="2a7f9-114">當您使用 ELIN 閘道時，您會使用市政位址、組建中的特定位置，以及為每個位置至少一個 ELIN 來填入位置資訊服務資料庫。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-114">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="2a7f9-115">在規劃階段，最好決定您要如何命名位置，以及您想要如何指派 ELINs。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-115">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

### <a name="planning-location-names"></a><span data-ttu-id="2a7f9-116">規劃位置名稱</span><span class="sxs-lookup"><span data-stu-id="2a7f9-116">Planning Location Names</span></span>

<span data-ttu-id="2a7f9-117">[位置資訊服務**位置**] 欄位會存放建築物內的特定位置，最大長度為20個字元（包括空格）。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-117">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="2a7f9-118">在該長度有限的範圍內，嘗試包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="2a7f9-118">Within that limited length, try to include the following:</span></span>

- <span data-ttu-id="2a7f9-119">識別911呼叫者位置的易於理解的名稱，可協助確保緊急回應程式在到達市政位址時能快速找到特定位置。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-119">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="2a7f9-120">這個位置名稱可以包含建築物編號、樓層編號、翼標示符、房間號碼等。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-120">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="2a7f9-121">避免只提供給員工的昵稱，這可能會導致緊急回應程式移至錯誤的位置。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-121">Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

- <span data-ttu-id="2a7f9-122">可協助使用者輕鬆查看其用戶端挑選正確位置的位置識別碼。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-122">A location identifier that helps users to easily see that their client picked up the correct location.</span></span> <span data-ttu-id="2a7f9-123">商務用 Skype 用戶端會自動連接並在其標題中顯示 [已探索的**位置**] 和 [**城市**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-123">The Skype for Business client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="2a7f9-124">最佳做法是將建築物的街道位址新增至每個位置識別碼（例如，"1 層<street number>"）。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-124">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor <street number>").</span></span> <span data-ttu-id="2a7f9-125">如果沒有街道位址，一般位置識別碼（例如「第一層」）會套用至城市中的任何建築物。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-125">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

- <span data-ttu-id="2a7f9-126">如果該位置是由無線存取點決定，您可能會想要新增 **[靠近]** （例如，"靠近1層樓 1234"）的字。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-126">If the location is approximate because it's determined by a wireless access point, you may want to add the word **[Near]** (for example, "Near 1st Floor 1234").</span></span>

### <a name="planning-elins"></a><span data-ttu-id="2a7f9-127">規劃 ELINs</span><span class="sxs-lookup"><span data-stu-id="2a7f9-127">Planning ELINs</span></span>

<span data-ttu-id="2a7f9-128">在您決定要如何將建築物空間劃分至多個位置之後，您必須決定要將多少 ELINs 指派給每個位置。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-128">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location.</span></span> <span data-ttu-id="2a7f9-129">例如，在 multifloor 或多租戶組建中，組建中的不同區域可以指定不同的緊急區域。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-129">For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones.</span></span> <span data-ttu-id="2a7f9-130">一般來說，建築物中的每個樓層都指定為一個位置。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-130">Typically, each floor in a building is designated as a location.</span></span> <span data-ttu-id="2a7f9-131">接著，系統會為每個位置指派一個或多個 ELINs，在緊急通話期間，就會用來做為電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-131">Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call.</span></span> <span data-ttu-id="2a7f9-132">請與您的 PSTN 運營商聯繫，以取得您可以用來 ELINs 的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-132">Contact your PSTN carrier for phone numbers that you can use for ELINs.</span></span> <span data-ttu-id="2a7f9-133">下表提供特定街道位址的位置範例。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-133">The following table provides an example of locations for a specific street address.</span></span>

<span data-ttu-id="2a7f9-134">**範例位置與 ELIN 作業**</span><span class="sxs-lookup"><span data-stu-id="2a7f9-134">**Sample Location and ELIN Assignments**</span></span>

|<span data-ttu-id="2a7f9-135">**建築物區域**</span><span class="sxs-lookup"><span data-stu-id="2a7f9-135">**Building Area**</span></span>|<span data-ttu-id="2a7f9-136">**位置**</span><span class="sxs-lookup"><span data-stu-id="2a7f9-136">**Location**</span></span>|<span data-ttu-id="2a7f9-137">**ELIN**</span><span class="sxs-lookup"><span data-stu-id="2a7f9-137">**ELIN**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a7f9-138">第一層</span><span class="sxs-lookup"><span data-stu-id="2a7f9-138">First floor</span></span>  <br/> |<span data-ttu-id="2a7f9-139">1</span><span class="sxs-lookup"><span data-stu-id="2a7f9-139">1</span></span>  <br/> |<span data-ttu-id="2a7f9-140">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="2a7f9-140">425-555-0100</span></span>  <br/> |
|<span data-ttu-id="2a7f9-141">第二層</span><span class="sxs-lookup"><span data-stu-id="2a7f9-141">Second floor</span></span>  <br/> |<span data-ttu-id="2a7f9-142">2</span><span class="sxs-lookup"><span data-stu-id="2a7f9-142">2</span></span>  <br/> |<span data-ttu-id="2a7f9-143">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="2a7f9-143">425-555-0111</span></span>  <br/> |
|<span data-ttu-id="2a7f9-144">第三層</span><span class="sxs-lookup"><span data-stu-id="2a7f9-144">Third floor</span></span>  <br/> |<span data-ttu-id="2a7f9-145">3</span><span class="sxs-lookup"><span data-stu-id="2a7f9-145">3</span></span>  <br/> |<span data-ttu-id="2a7f9-146">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="2a7f9-146">425-555-0123</span></span>  <br/> |

<span data-ttu-id="2a7f9-147">您定義的位置應該符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="2a7f9-147">The locations you define should meet the following requirements:</span></span>

- <span data-ttu-id="2a7f9-148">在每個位置的最大區域及每個街道位址的位置數方面，遵守當地和國家/地區管理法規。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-148">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

- <span data-ttu-id="2a7f9-149">都有足夠的針對性，便於您找到緊急來電者。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-149">Are specific enough to make it easy to locate the emergency caller.</span></span>

## <a name="populating-the-location-database"></a><span data-ttu-id="2a7f9-150">填充位置資料庫</span><span class="sxs-lookup"><span data-stu-id="2a7f9-150">Populating the Location Database</span></span>

<span data-ttu-id="2a7f9-151">下列問題將協助您決定將如何填入位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-151">The following questions will help you determine how to will populate the location database.</span></span>

 <span data-ttu-id="2a7f9-152">**您將使用哪個程式來填入位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="2a7f9-152">**What process will you use to populate the location database?**</span></span>

<span data-ttu-id="2a7f9-153">資料在哪裡存在，您需要採取哪些步驟才能將資料轉換成位置資料庫所需的格式？</span><span class="sxs-lookup"><span data-stu-id="2a7f9-153">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="2a7f9-154">您會使用 CSV 檔案個別地新增位置，還是大量新增位置？</span><span class="sxs-lookup"><span data-stu-id="2a7f9-154">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

 <span data-ttu-id="2a7f9-155">**您是否有已包含位置對應的協力廠商資料庫？**</span><span class="sxs-lookup"><span data-stu-id="2a7f9-155">**Do you have a third party database that already contains a mapping of locations?**</span></span>

<span data-ttu-id="2a7f9-156">透過使用 [次要位置資訊服務] 選項來連線至協力廠商資料庫，您可以使用離線平臺來分組及管理位置。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-156">By using the Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="2a7f9-157">這種方法的優點是，除了將位置與網路識別碼相關聯之外，您還可以將位置與使用者建立關聯。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-157">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="2a7f9-158">這表示位置資訊服務可以傳回多個位址（源自次要位置資訊服務）到商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-158">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Skype for Business client.</span></span> <span data-ttu-id="2a7f9-159">然後，使用者可以選擇最適合的位置。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-159">The user can then choose the most appropriate location.</span></span>

<span data-ttu-id="2a7f9-160">若要整合位置資訊服務，協力廠商資料庫必須遵循商務用 Skype Server 位置要求/回應架構。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-160">To integrate with the Location Information service, the third-party database must follow the Skype for Business Server Location Request/Response schema.</span></span> <span data-ttu-id="2a7f9-161">如需詳細資訊，請參閱[Web 服務以取得 E911 支援通訊協定](https://go.microsoft.com/fwlink/p/?linkid=213819)。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-161">For details, see [Web Service for E911 Support Protocol](https://go.microsoft.com/fwlink/p/?linkid=213819).</span></span> <span data-ttu-id="2a7f9-162">如需有關部署次要位置資訊服務的詳細資訊，請參閱在部署檔中的[商務用 Skype Server 中設定次要位置資訊服務](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-162">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="2a7f9-163">如需有關填充位置資料庫的詳細資訊，請參閱在部署檔中[設定位置資料庫](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-163">For details about populating the location database, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="2a7f9-164">維護位置資料庫</span><span class="sxs-lookup"><span data-stu-id="2a7f9-164">Maintaining the Location Database</span></span>

<span data-ttu-id="2a7f9-165">在您填入 location 資料庫之後，您需要開發一個策略，在網路設定變更時更新資料庫。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-165">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="2a7f9-166">下列問題將協助您決定如何維護位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-166">The following questions will help you determine how to maintain the location database.</span></span>

 <span data-ttu-id="2a7f9-167">**如何更新位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="2a7f9-167">**How will you update the location database?**</span></span>

<span data-ttu-id="2a7f9-168">有幾種情況需要更新位置資料庫，包括新增無線存取點（WAPs）、office recabling （產生不同的切換作業），以及子網延伸。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-168">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="2a7f9-169">您是否會直接更新每個個別位置，或是使用 CSV 檔案執行所有位置的大量更新？</span><span class="sxs-lookup"><span data-stu-id="2a7f9-169">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

 <span data-ttu-id="2a7f9-170">**您是否會使用 SNMP 應用程式，將商務用 Skype 用戶端 MAC 位址與埠和切換識別碼相符？**</span><span class="sxs-lookup"><span data-stu-id="2a7f9-170">**Will you use an SNMP application to match Skype for Business client MAC addresses to port and switch identifiers?**</span></span>

<span data-ttu-id="2a7f9-171">如果您使用的是 SNMP 應用程式，您必須開發手動程式，以保持 SNMP 應用程式和位置資料庫之間的切換底盤和埠資訊一致。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-171">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="2a7f9-172">如果 SNMP 應用程式傳回的是不包含在資料庫中的主機殼 IP 位址或埠 ID，位置資訊服務將無法傳回用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="2a7f9-172">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>


