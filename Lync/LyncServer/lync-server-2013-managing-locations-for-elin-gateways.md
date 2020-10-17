---
title: Lync Server 2013：管理 ELIN 閘道的位置
description: Lync Server 2013：管理 ELIN 閘道的位置。
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
ms.openlocfilehash: 94fe7797c0f25adb219512cef4a6c0fb7d84b48d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557479"
---
# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="c8340-103">在 Lync Server 2013 中管理 ELIN 閘道的位置</span><span class="sxs-lookup"><span data-stu-id="c8340-103">Managing locations for ELIN gateways in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8340-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c8340-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c8340-105">若要讓 Lync Server 自動為網路中的用戶端提供位置，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="c8340-105">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="c8340-106">以網路線路圖填入 Location 資訊服務資料庫，並在 [CompanyName] 欄位中包含緊急位置標識號 (Elin) 。</span><span class="sxs-lookup"><span data-stu-id="c8340-106">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="c8340-107">發佈位置，以供網路中的用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="c8340-107">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="c8340-108">將 Elin 上傳至您公用交換電話網路 (PSTN) 承運商的自動位置識別 (阿裡) database。</span><span class="sxs-lookup"><span data-stu-id="c8340-108">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="c8340-109">如需如何執行這些工作的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md) 。</span><span class="sxs-lookup"><span data-stu-id="c8340-109">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8340-110">新增至中央位置資料庫的位置直到使用 Lync Server 管理命令介面命令加以發佈，而且會複製到集區的本機存放區，才可供用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="c8340-110">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="c8340-111">如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-publish-the-location-database.md">從 Lync Server 2013 發佈位置資料庫</A> 。</span><span class="sxs-lookup"><span data-stu-id="c8340-111">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="c8340-112">本節說明當您計畫更新及維護位置資料庫時，應考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="c8340-112">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="c8340-113">規劃緊急位置</span><span class="sxs-lookup"><span data-stu-id="c8340-113">Planning Emergency Locations</span></span>

<span data-ttu-id="c8340-114">當您使用 ELIN 閘道時，會使用市政位址、大樓內的特定位置，以及每個位置至少一個 ELIN 來填入位置資訊服務資料庫。</span><span class="sxs-lookup"><span data-stu-id="c8340-114">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="c8340-115">在規劃階段期間，最好決定要如何命名位置，以及您要如何指派 Elin。</span><span class="sxs-lookup"><span data-stu-id="c8340-115">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="c8340-116">規劃位置名稱</span><span class="sxs-lookup"><span data-stu-id="c8340-116">Planning Location Names</span></span>

<span data-ttu-id="c8340-117">位置資訊服務 **位置** 欄位（容納大樓內的特定位置）的長度上限為20個字元 (包含空格) 。</span><span class="sxs-lookup"><span data-stu-id="c8340-117">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="c8340-118">在此有限長度內，嘗試包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="c8340-118">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="c8340-119">易於辨識的名稱，可識別911呼叫者的位置，以協助確保緊急回應程式在到達市政位址時立即找到特定位置。</span><span class="sxs-lookup"><span data-stu-id="c8340-119">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="c8340-120">此位置名稱可以包含大樓編號、底價編號、翼標示符、會議室編號等等。</span><span class="sxs-lookup"><span data-stu-id="c8340-120">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="c8340-121">避免只有員工知道的昵稱，這可能會造成緊急回應程式進入錯誤的位置。</span><span class="sxs-lookup"><span data-stu-id="c8340-121">Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="c8340-122">一個位置識別碼，可協助使用者輕鬆查看其 Lync 用戶端是否已挑選正確的位置。</span><span class="sxs-lookup"><span data-stu-id="c8340-122">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="c8340-123">Lync 用戶端會自動連接並顯示其頁首中已探索的 **位置** 和 **城市** 欄位。</span><span class="sxs-lookup"><span data-stu-id="c8340-123">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="c8340-124">最佳作法是將大樓的街道位址新增至每個位置識別碼 (例如，"第一層 \<street number\> " ) 。</span><span class="sxs-lookup"><span data-stu-id="c8340-124">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="c8340-125">沒有街道位址，「第一層」等一般位置識別碼可以套用到城市中的任何辦公樓。</span><span class="sxs-lookup"><span data-stu-id="c8340-125">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="c8340-126">如果位置是由無線存取點所決定，您可能會想要新增文字近 (例如，「接近第一層1234」 ) 。</span><span class="sxs-lookup"><span data-stu-id="c8340-126">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="c8340-127">規劃 Elin</span><span class="sxs-lookup"><span data-stu-id="c8340-127">Planning ELINs</span></span>

<span data-ttu-id="c8340-128">決定如何將大樓空間分割成多個位置之後，您必須決定要將多少 Elin 指派給每個位置。</span><span class="sxs-lookup"><span data-stu-id="c8340-128">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location.</span></span> <span data-ttu-id="c8340-129">例如，在 multifloor 或多租戶組建中，可以將組建中的不同區域指派給不同的急診區域。</span><span class="sxs-lookup"><span data-stu-id="c8340-129">For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones.</span></span> <span data-ttu-id="c8340-130">一般來說，大樓中的每一層都指定為位置。</span><span class="sxs-lookup"><span data-stu-id="c8340-130">Typically, each floor in a building is designated as a location.</span></span> <span data-ttu-id="c8340-131">然後將每個地點指派一或多個 Elin，在緊急通話期間會將其當作通話號碼 (s) 使用。</span><span class="sxs-lookup"><span data-stu-id="c8340-131">Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call.</span></span> <span data-ttu-id="c8340-132">請與您的 PSTN 電信公司聯繫，以取得可用於 Elin 的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c8340-132">Contact your PSTN carrier for phone numbers that you can use for ELINs.</span></span> <span data-ttu-id="c8340-133">下表提供特定街道位址的位置範例。</span><span class="sxs-lookup"><span data-stu-id="c8340-133">The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="c8340-134">範例位置和 ELIN 指派</span><span class="sxs-lookup"><span data-stu-id="c8340-134">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8340-135">組建區域</span><span class="sxs-lookup"><span data-stu-id="c8340-135">Building Area</span></span></th>
<th><span data-ttu-id="c8340-136">位置</span><span class="sxs-lookup"><span data-stu-id="c8340-136">Location</span></span></th>
<th><span data-ttu-id="c8340-137">愛琳</span><span class="sxs-lookup"><span data-stu-id="c8340-137">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8340-138">第一層</span><span class="sxs-lookup"><span data-stu-id="c8340-138">First floor</span></span></p></td>
<td><p><span data-ttu-id="c8340-139">1 </span><span class="sxs-lookup"><span data-stu-id="c8340-139">1</span></span></p></td>
<td><p><span data-ttu-id="c8340-140">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="c8340-140">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8340-141">第二個基底</span><span class="sxs-lookup"><span data-stu-id="c8340-141">Second floor</span></span></p></td>
<td><p><span data-ttu-id="c8340-142">第</span><span class="sxs-lookup"><span data-stu-id="c8340-142">2</span></span></p></td>
<td><p><span data-ttu-id="c8340-143">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="c8340-143">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8340-144">第三個地板</span><span class="sxs-lookup"><span data-stu-id="c8340-144">Third floor</span></span></p></td>
<td><p><span data-ttu-id="c8340-145">個</span><span class="sxs-lookup"><span data-stu-id="c8340-145">3</span></span></p></td>
<td><p><span data-ttu-id="c8340-146">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="c8340-146">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c8340-147">您定義的位置應符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="c8340-147">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="c8340-148">在 [每個位置的最大區域] 和 [每個街道的位置數目] 等方面，遵循本機和國家/地區規定。</span><span class="sxs-lookup"><span data-stu-id="c8340-148">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="c8340-149">都有足夠的針對性，可讓您輕鬆找到緊急來電者。</span><span class="sxs-lookup"><span data-stu-id="c8340-149">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="c8340-150">填充位置資料庫</span><span class="sxs-lookup"><span data-stu-id="c8340-150">Populating the Location Database</span></span>

<span data-ttu-id="c8340-151">下列問題可協助您決定如何填入位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="c8340-151">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="c8340-152">**您將使用哪個程式填入位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="c8340-152">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="c8340-153">資料存在的位置，以及您需要採取哪些步驟將資料轉換成位置資料庫所需的格式？</span><span class="sxs-lookup"><span data-stu-id="c8340-153">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="c8340-154">是否要使用 CSV 檔案個別新增位置，還是大量使用 CSV 檔案？</span><span class="sxs-lookup"><span data-stu-id="c8340-154">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="c8340-155">**您是否有已包含位置對應的協力廠商資料庫？**</span><span class="sxs-lookup"><span data-stu-id="c8340-155">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="c8340-156">使用 Lync Server 的次要位置資訊服務選項來連線至協力廠商資料庫，您可以使用離線平臺來分組和管理位置。</span><span class="sxs-lookup"><span data-stu-id="c8340-156">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="c8340-157">這種方法的好處是，除了將位置與網路識別碼相關聯之外，也可以將位置與使用者產生關聯。</span><span class="sxs-lookup"><span data-stu-id="c8340-157">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="c8340-158">這表示位置資訊服務可以傳回多個來自次要位置資訊服務的位址給 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="c8340-158">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="c8340-159">然後，使用者可以選擇最適合的位置。</span><span class="sxs-lookup"><span data-stu-id="c8340-159">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="c8340-160">若要與位置資訊服務整合，協力廠商資料庫必須遵循 Lync Server 位置要求/回應架構。</span><span class="sxs-lookup"><span data-stu-id="c8340-160">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="c8340-161">如需詳細資訊，請參閱 <https://go.microsoft.com/fwlink/p/?linkid=213819> 。</span><span class="sxs-lookup"><span data-stu-id="c8340-161">For details, see <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="c8340-162">如需部署次要位置資訊服務的詳細資訊，請參閱部署檔中的 [Configure a 輔 Location information service In Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) 。</span><span class="sxs-lookup"><span data-stu-id="c8340-162">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c8340-163">如需有關填充位置資料庫的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md) 。</span><span class="sxs-lookup"><span data-stu-id="c8340-163">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="c8340-164">維護位置資料庫</span><span class="sxs-lookup"><span data-stu-id="c8340-164">Maintaining the Location Database</span></span>

<span data-ttu-id="c8340-165">填滿位置資料庫之後，您需要開發一個策略，以在網路設定變更時更新資料庫。</span><span class="sxs-lookup"><span data-stu-id="c8340-165">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="c8340-166">下列問題可協助您決定如何維護位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="c8340-166">The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="c8340-167">**您將如何更新位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="c8340-167">**How will you update the location database?**</span></span>  
    <span data-ttu-id="c8340-168">有幾個案例需要更新位置資料庫，包括新增無線存取點 (Wap) 、office recabling (導致不同的切換指派) 及子網擴充。</span><span class="sxs-lookup"><span data-stu-id="c8340-168">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="c8340-169">您是否會直接更新每個個別位置，或是使用 CSV 檔案執行所有位置的大量更新？</span><span class="sxs-lookup"><span data-stu-id="c8340-169">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="c8340-170">**您是否會使用 SNMP 應用程式，將 Lync 用戶端 MAC 位址與埠及切換識別碼對應？**</span><span class="sxs-lookup"><span data-stu-id="c8340-170">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="c8340-171">如果您使用 SNMP 應用程式，則必須開發手動程式，以在 SNMP 應用程式和位置資料庫之間保持切換底盤及埠資訊的一致性。</span><span class="sxs-lookup"><span data-stu-id="c8340-171">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="c8340-172">如果 SNMP 應用程式傳回資料庫中未包含的主機殼 IP 位址或埠識別碼，則位置資訊服務將無法傳回用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="c8340-172">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

