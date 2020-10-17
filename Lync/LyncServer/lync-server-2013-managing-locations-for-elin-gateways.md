---
title: Lync Server 2013：管理 ELIN 閘道的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e33f05f0a05b1225f1687faa00cf48af02fa1410
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498160"
---
# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="e930d-102">在 Lync Server 2013 中管理 ELIN 閘道的位置</span><span class="sxs-lookup"><span data-stu-id="e930d-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e930d-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e930d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e930d-104">若要讓 Lync Server 自動為網路中的用戶端提供位置，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="e930d-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="e930d-105">以網路線路圖填入 Location 資訊服務資料庫，並在 [CompanyName] 欄位中包含緊急位置標識號 (Elin) 。</span><span class="sxs-lookup"><span data-stu-id="e930d-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="e930d-106">發佈位置，以供網路中的用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="e930d-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="e930d-107">將 Elin 上傳至您公用交換電話網路 (PSTN) 承運商的自動位置識別 (阿裡) database。</span><span class="sxs-lookup"><span data-stu-id="e930d-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="e930d-108">如需如何執行這些工作的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md) 。</span><span class="sxs-lookup"><span data-stu-id="e930d-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e930d-109">新增至中央位置資料庫的位置直到使用 Lync Server 管理命令介面命令加以發佈，而且會複製到集區的本機存放區，才可供用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="e930d-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="e930d-110">如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-publish-the-location-database.md">從 Lync Server 2013 發佈位置資料庫</A> 。</span><span class="sxs-lookup"><span data-stu-id="e930d-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="e930d-111">本節說明當您計畫更新及維護位置資料庫時，應考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="e930d-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="e930d-112">規劃緊急位置</span><span class="sxs-lookup"><span data-stu-id="e930d-112">Planning Emergency Locations</span></span>

<span data-ttu-id="e930d-113">當您使用 ELIN 閘道時，會使用市政位址、大樓內的特定位置，以及每個位置至少一個 ELIN 來填入位置資訊服務資料庫。</span><span class="sxs-lookup"><span data-stu-id="e930d-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="e930d-114">在規劃階段期間，最好決定要如何命名位置，以及您要如何指派 Elin。</span><span class="sxs-lookup"><span data-stu-id="e930d-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="e930d-115">規劃位置名稱</span><span class="sxs-lookup"><span data-stu-id="e930d-115">Planning Location Names</span></span>

<span data-ttu-id="e930d-116">位置資訊服務 **位置** 欄位（容納大樓內的特定位置）的長度上限為20個字元 (包含空格) 。</span><span class="sxs-lookup"><span data-stu-id="e930d-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="e930d-117">在此有限長度內，嘗試包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="e930d-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="e930d-118">易於辨識的名稱，可識別911呼叫者的位置，以協助確保緊急回應程式在到達市政位址時立即找到特定位置。</span><span class="sxs-lookup"><span data-stu-id="e930d-118">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="e930d-119">此位置名稱可以包含大樓編號、底價編號、翼標示符、會議室編號等等。</span><span class="sxs-lookup"><span data-stu-id="e930d-119">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="e930d-120">避免只有員工知道的昵稱，這可能會造成緊急回應程式進入錯誤的位置。</span><span class="sxs-lookup"><span data-stu-id="e930d-120">Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="e930d-121">一個位置識別碼，可協助使用者輕鬆查看其 Lync 用戶端是否已挑選正確的位置。</span><span class="sxs-lookup"><span data-stu-id="e930d-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="e930d-122">Lync 用戶端會自動連接並顯示其頁首中已探索的 **位置** 和 **城市** 欄位。</span><span class="sxs-lookup"><span data-stu-id="e930d-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="e930d-123">最佳作法是將大樓的街道位址新增至每個位置識別碼 (例如，"第一層 \<street number\> " ) 。</span><span class="sxs-lookup"><span data-stu-id="e930d-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="e930d-124">沒有街道位址，「第一層」等一般位置識別碼可以套用到城市中的任何辦公樓。</span><span class="sxs-lookup"><span data-stu-id="e930d-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="e930d-125">如果位置是由無線存取點所決定，您可能會想要新增文字近 (例如，「接近第一層1234」 ) 。</span><span class="sxs-lookup"><span data-stu-id="e930d-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="e930d-126">規劃 Elin</span><span class="sxs-lookup"><span data-stu-id="e930d-126">Planning ELINs</span></span>

<span data-ttu-id="e930d-127">決定如何將大樓空間分割成多個位置之後，您必須決定要將多少 Elin 指派給每個位置。</span><span class="sxs-lookup"><span data-stu-id="e930d-127">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location.</span></span> <span data-ttu-id="e930d-128">例如，在 multifloor 或多租戶組建中，可以將組建中的不同區域指派給不同的急診區域。</span><span class="sxs-lookup"><span data-stu-id="e930d-128">For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones.</span></span> <span data-ttu-id="e930d-129">一般來說，大樓中的每一層都指定為位置。</span><span class="sxs-lookup"><span data-stu-id="e930d-129">Typically, each floor in a building is designated as a location.</span></span> <span data-ttu-id="e930d-130">然後將每個地點指派一或多個 Elin，在緊急通話期間會將其當作通話號碼 (s) 使用。</span><span class="sxs-lookup"><span data-stu-id="e930d-130">Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call.</span></span> <span data-ttu-id="e930d-131">請與您的 PSTN 電信公司聯繫，以取得可用於 Elin 的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e930d-131">Contact your PSTN carrier for phone numbers that you can use for ELINs.</span></span> <span data-ttu-id="e930d-132">下表提供特定街道位址的位置範例。</span><span class="sxs-lookup"><span data-stu-id="e930d-132">The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="e930d-133">範例位置和 ELIN 指派</span><span class="sxs-lookup"><span data-stu-id="e930d-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e930d-134">組建區域</span><span class="sxs-lookup"><span data-stu-id="e930d-134">Building Area</span></span></th>
<th><span data-ttu-id="e930d-135">位置</span><span class="sxs-lookup"><span data-stu-id="e930d-135">Location</span></span></th>
<th><span data-ttu-id="e930d-136">愛琳</span><span class="sxs-lookup"><span data-stu-id="e930d-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e930d-137">第一層</span><span class="sxs-lookup"><span data-stu-id="e930d-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="e930d-138">1 </span><span class="sxs-lookup"><span data-stu-id="e930d-138">1</span></span></p></td>
<td><p><span data-ttu-id="e930d-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="e930d-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e930d-140">第二個基底</span><span class="sxs-lookup"><span data-stu-id="e930d-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="e930d-141">第</span><span class="sxs-lookup"><span data-stu-id="e930d-141">2</span></span></p></td>
<td><p><span data-ttu-id="e930d-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="e930d-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e930d-143">第三個地板</span><span class="sxs-lookup"><span data-stu-id="e930d-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="e930d-144">個</span><span class="sxs-lookup"><span data-stu-id="e930d-144">3</span></span></p></td>
<td><p><span data-ttu-id="e930d-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="e930d-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e930d-146">您定義的位置應符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="e930d-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="e930d-147">在 [每個位置的最大區域] 和 [每個街道的位置數目] 等方面，遵循本機和國家/地區規定。</span><span class="sxs-lookup"><span data-stu-id="e930d-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="e930d-148">都有足夠的針對性，可讓您輕鬆找到緊急來電者。</span><span class="sxs-lookup"><span data-stu-id="e930d-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="e930d-149">填充位置資料庫</span><span class="sxs-lookup"><span data-stu-id="e930d-149">Populating the Location Database</span></span>

<span data-ttu-id="e930d-150">下列問題可協助您決定如何填入位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="e930d-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="e930d-151">**您將使用哪個程式填入位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="e930d-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="e930d-152">資料存在的位置，以及您需要採取哪些步驟將資料轉換成位置資料庫所需的格式？</span><span class="sxs-lookup"><span data-stu-id="e930d-152">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="e930d-153">是否要使用 CSV 檔案個別新增位置，還是大量使用 CSV 檔案？</span><span class="sxs-lookup"><span data-stu-id="e930d-153">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="e930d-154">**您是否有已包含位置對應的協力廠商資料庫？**</span><span class="sxs-lookup"><span data-stu-id="e930d-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="e930d-155">使用 Lync Server 的次要位置資訊服務選項來連線至協力廠商資料庫，您可以使用離線平臺來分組和管理位置。</span><span class="sxs-lookup"><span data-stu-id="e930d-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="e930d-156">這種方法的好處是，除了將位置與網路識別碼相關聯之外，也可以將位置與使用者產生關聯。</span><span class="sxs-lookup"><span data-stu-id="e930d-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="e930d-157">這表示位置資訊服務可以傳回多個來自次要位置資訊服務的位址給 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="e930d-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="e930d-158">然後，使用者可以選擇最適合的位置。</span><span class="sxs-lookup"><span data-stu-id="e930d-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="e930d-159">若要與位置資訊服務整合，協力廠商資料庫必須遵循 Lync Server 位置要求/回應架構。</span><span class="sxs-lookup"><span data-stu-id="e930d-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="e930d-160">如需詳細資訊，請參閱 <https://go.microsoft.com/fwlink/p/?linkid=213819> 。</span><span class="sxs-lookup"><span data-stu-id="e930d-160">For details, see <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="e930d-161">如需部署次要位置資訊服務的詳細資訊，請參閱部署檔中的 [Configure a 輔 Location information service In Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) 。</span><span class="sxs-lookup"><span data-stu-id="e930d-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e930d-162">如需有關填充位置資料庫的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md) 。</span><span class="sxs-lookup"><span data-stu-id="e930d-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="e930d-163">維護位置資料庫</span><span class="sxs-lookup"><span data-stu-id="e930d-163">Maintaining the Location Database</span></span>

<span data-ttu-id="e930d-164">填滿位置資料庫之後，您需要開發一個策略，以在網路設定變更時更新資料庫。</span><span class="sxs-lookup"><span data-stu-id="e930d-164">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="e930d-165">下列問題可協助您決定如何維護位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="e930d-165">The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="e930d-166">**您將如何更新位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="e930d-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="e930d-167">有幾個案例需要更新位置資料庫，包括新增無線存取點 (Wap) 、office recabling (導致不同的切換指派) 及子網擴充。</span><span class="sxs-lookup"><span data-stu-id="e930d-167">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="e930d-168">您是否會直接更新每個個別位置，或是使用 CSV 檔案執行所有位置的大量更新？</span><span class="sxs-lookup"><span data-stu-id="e930d-168">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="e930d-169">**您是否會使用 SNMP 應用程式，將 Lync 用戶端 MAC 位址與埠及切換識別碼對應？**</span><span class="sxs-lookup"><span data-stu-id="e930d-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="e930d-170">如果您使用 SNMP 應用程式，則必須開發手動程式，以在 SNMP 應用程式和位置資料庫之間保持切換底盤及埠資訊的一致性。</span><span class="sxs-lookup"><span data-stu-id="e930d-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="e930d-171">如果 SNMP 應用程式傳回資料庫中未包含的主機殼 IP 位址或埠識別碼，則位置資訊服務將無法傳回用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="e930d-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

