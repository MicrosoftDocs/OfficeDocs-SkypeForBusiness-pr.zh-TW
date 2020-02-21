---
title: Lync Server 2013： 管理 ELIN 閘道位置
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
ms.openlocfilehash: 88b27e325ba8990cf239548c689d4e021397858a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="309dc-102">管理 ELIN 閘道 Lync Server 2013 中的位置</span><span class="sxs-lookup"><span data-stu-id="309dc-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="309dc-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="309dc-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="309dc-104">若要讓 Lync Server 自動提供網路內的用戶端的位置，您需要執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="309dc-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="309dc-105">填入網路接線圖，位置資訊服務資料庫，並在 CompanyName 欄位中包含緊急事故位置識別碼 (Elin)。</span><span class="sxs-lookup"><span data-stu-id="309dc-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="309dc-106">發佈位置，使其可供您網路中的用戶端。</span><span class="sxs-lookup"><span data-stu-id="309dc-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="309dc-107">將 Elin 上傳至您的公用交換的電話網路 (PSTN) 電信業者的自動位置識別 (ALI) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="309dc-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="309dc-108">如需如何執行這些工作的詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的位置資料庫](lync-server-2013-configure-the-location-database.md)。</span><span class="sxs-lookup"><span data-stu-id="309dc-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="309dc-109">除非他們已發佈使用 Lync Server 管理命令介面命令，並且會複寫到集區的本機存放區，並不適用於用戶端新增至中央位置資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="309dc-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="309dc-110">如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-publish-the-location-database.md">發佈位置資料庫從 Lync Server 2013</A> 。</span><span class="sxs-lookup"><span data-stu-id="309dc-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="309dc-111">本節說明當您規劃更新和維護位置資料庫的考量事項。</span><span class="sxs-lookup"><span data-stu-id="309dc-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="309dc-112">規劃緊急事故處理位置</span><span class="sxs-lookup"><span data-stu-id="309dc-112">Planning Emergency Locations</span></span>

<span data-ttu-id="309dc-113">當您使用 ELIN 閘道時，您會填入市街地址、 建置內的特定位置與至少一個 ELIN 為每個位置的位置資訊服務資料庫。</span><span class="sxs-lookup"><span data-stu-id="309dc-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="309dc-114">計劃階段中，它是不錯的選項，以決定要如何命名位置，以及您想要指派 Elin 的方式。</span><span class="sxs-lookup"><span data-stu-id="309dc-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="309dc-115">規劃位置名稱</span><span class="sxs-lookup"><span data-stu-id="309dc-115">Planning Location Names</span></span>

<span data-ttu-id="309dc-116">[位置資訊服務**位置**] 欄位中含有建置內的特定位置，具有長度上限為 20 個字元 （包括空格）。</span><span class="sxs-lookup"><span data-stu-id="309dc-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="309dc-117">在該限制的長度，嘗試包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="309dc-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="309dc-118">容易理解名稱，可識別 911 來電者可協助您確保的緊急回應者的特定位置迅速時找到它們都會送達市街地址的位置。</span><span class="sxs-lookup"><span data-stu-id="309dc-118">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="309dc-119">此位置名稱可能包含建築物編號、 底板數字、 蝶形指示項，會議室號碼等等。</span><span class="sxs-lookup"><span data-stu-id="309dc-119">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="309dc-120">避免只已知可能會導致移至錯誤的位置的緊急回應者的員工的暱稱。</span><span class="sxs-lookup"><span data-stu-id="309dc-120">Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="309dc-121">協助使用者輕鬆地查看，挑選的正確位置其 Lync 用戶端位置識別碼。</span><span class="sxs-lookup"><span data-stu-id="309dc-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="309dc-122">Lync 用戶端會自動將串連，並顯示探索到的**位置**] 和 [**縣/市**欄位標頭中。</span><span class="sxs-lookup"><span data-stu-id="309dc-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="309dc-123">很好的作法是將建置的街道地址新增至每個位置識別碼 (例如，"1st Floor\<街道號碼\>」)。</span><span class="sxs-lookup"><span data-stu-id="309dc-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="309dc-124">街道地址，而 「 1st 樓 」 等的一般位置識別碼無法套用至任何建置在 [縣/市。</span><span class="sxs-lookup"><span data-stu-id="309dc-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="309dc-125">如果因為它由無線存取點決定的概略位置，您可能想要加入 near 的字詞 （例如 「 靠近 1st 樓 1234年）。</span><span class="sxs-lookup"><span data-stu-id="309dc-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="309dc-126">規劃 Elin</span><span class="sxs-lookup"><span data-stu-id="309dc-126">Planning ELINs</span></span>

<span data-ttu-id="309dc-127">決定您要建置空間分成數個位置的方式之後，您需要決定多少 Elin 指派給每個位置。</span><span class="sxs-lookup"><span data-stu-id="309dc-127">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location.</span></span> <span data-ttu-id="309dc-128">例如，multifloor 或在多租用戶的建置、 中建置不同的區域可以指派不同的緊急區域。</span><span class="sxs-lookup"><span data-stu-id="309dc-128">For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones.</span></span> <span data-ttu-id="309dc-129">一般而言，每個樓層建置已指定位置。</span><span class="sxs-lookup"><span data-stu-id="309dc-129">Typically, each floor in a building is designated as a location.</span></span> <span data-ttu-id="309dc-130">每個位置就被指派一或多個 Elin 時，緊急通話當成通話轉接。</span><span class="sxs-lookup"><span data-stu-id="309dc-130">Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call.</span></span> <span data-ttu-id="309dc-131">您可以使用 Elin 的電話號碼，請連絡您 PSTN 電信業者。</span><span class="sxs-lookup"><span data-stu-id="309dc-131">Contact your PSTN carrier for phone numbers that you can use for ELINs.</span></span> <span data-ttu-id="309dc-132">下表提供特定的街道地址的位置的範例。</span><span class="sxs-lookup"><span data-stu-id="309dc-132">The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="309dc-133">範例位置和 ELIN 指派作業</span><span class="sxs-lookup"><span data-stu-id="309dc-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="309dc-134">建築物區域</span><span class="sxs-lookup"><span data-stu-id="309dc-134">Building Area</span></span></th>
<th><span data-ttu-id="309dc-135">位置</span><span class="sxs-lookup"><span data-stu-id="309dc-135">Location</span></span></th>
<th><span data-ttu-id="309dc-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="309dc-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="309dc-137">一樓</span><span class="sxs-lookup"><span data-stu-id="309dc-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="309dc-138">1</span><span class="sxs-lookup"><span data-stu-id="309dc-138">1</span></span></p></td>
<td><p><span data-ttu-id="309dc-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="309dc-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="309dc-140">二樓</span><span class="sxs-lookup"><span data-stu-id="309dc-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="309dc-141">2</span><span class="sxs-lookup"><span data-stu-id="309dc-141">2</span></span></p></td>
<td><p><span data-ttu-id="309dc-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="309dc-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="309dc-143">三樓</span><span class="sxs-lookup"><span data-stu-id="309dc-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="309dc-144">3</span><span class="sxs-lookup"><span data-stu-id="309dc-144">3</span></span></p></td>
<td><p><span data-ttu-id="309dc-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="309dc-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="309dc-146">您定義的位置應符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="309dc-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="309dc-147">遵守本機和國家/區域法令每個位置及每個街道地址的位置數目的最大區域。</span><span class="sxs-lookup"><span data-stu-id="309dc-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="309dc-148">特有足以讓您輕鬆找到緊急來電者。</span><span class="sxs-lookup"><span data-stu-id="309dc-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="309dc-149">填入位置資料庫</span><span class="sxs-lookup"><span data-stu-id="309dc-149">Populating the Location Database</span></span>

<span data-ttu-id="309dc-150">下列問題可協助您決定如何填入位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="309dc-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="309dc-151">**您將使用何種程序填入位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="309dc-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="309dc-152">其中是否存在的資料，以及您需要將資料轉換成位置資料庫所需的格式採取哪些步驟？</span><span class="sxs-lookup"><span data-stu-id="309dc-152">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="309dc-153">將您新增位置會個別或大量使用 CSV 檔案？</span><span class="sxs-lookup"><span data-stu-id="309dc-153">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="309dc-154">**您必須已經包含位置對應的協力廠商資料庫？**</span><span class="sxs-lookup"><span data-stu-id="309dc-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="309dc-155">使用 Lync Server 的次要位置資訊服務] 選項，以連線至協力廠商資料庫，您可以群組，並使用離線平台管理位置。</span><span class="sxs-lookup"><span data-stu-id="309dc-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="309dc-156">這種方法的好處是，除了建立關聯至網路識別碼的位置，您可以建立關聯的使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="309dc-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="309dc-157">這表示位置資訊服務可以傳回多個地址，源自次要位置資訊服務，Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="309dc-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="309dc-158">然後，使用者可以選擇最適合的位置。</span><span class="sxs-lookup"><span data-stu-id="309dc-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="309dc-159">若要整合與位置資訊服務，協力廠商資料庫必須遵循 Lync 伺服器位置要求讀回應結構描述。</span><span class="sxs-lookup"><span data-stu-id="309dc-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="309dc-160">如需詳細資訊，請參閱<https://go.microsoft.com/fwlink/p/?linkid=213819>。</span><span class="sxs-lookup"><span data-stu-id="309dc-160">For details, see <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="309dc-161">如需部署次要位置資訊服務的詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的次要位置資訊服務](lync-server-2013-configure-a-secondary-location-information-service.md)。</span><span class="sxs-lookup"><span data-stu-id="309dc-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="309dc-162">如需填入位置資料庫的詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的位置資料庫](lync-server-2013-configure-the-location-database.md)。</span><span class="sxs-lookup"><span data-stu-id="309dc-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="309dc-163">維護位置資料庫</span><span class="sxs-lookup"><span data-stu-id="309dc-163">Maintaining the Location Database</span></span>

<span data-ttu-id="309dc-164">填入位置資料庫之後，您需要開發更新資料庫作為網路組態變更的策略。</span><span class="sxs-lookup"><span data-stu-id="309dc-164">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="309dc-165">下列問題可協助您決定如何維護位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="309dc-165">The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="309dc-166">**您要如何更新位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="309dc-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="309dc-167">有幾種情況，需要更新至位置資料庫，包括新增無線存取點 (Wap)、 office recabling （產生不同的參數指派），和子網路擴充。</span><span class="sxs-lookup"><span data-stu-id="309dc-167">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="309dc-168">將您直接更新每個個別的位置，或將使用 CSV 檔案來執行的所有位置大量更新？</span><span class="sxs-lookup"><span data-stu-id="309dc-168">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="309dc-169">**您將使用 SNMP 應用程式符合 Lync 用戶端 MAC 位址來連接埠和交換器識別碼？**</span><span class="sxs-lookup"><span data-stu-id="309dc-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="309dc-170">如果您使用 SNMP 應用程式，您需要開發將交換器底座和連接埠資訊保持一致 SNMP 應用程式和資料庫位置之間的手動程序。</span><span class="sxs-lookup"><span data-stu-id="309dc-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="309dc-171">如果 SNMP 應用程式傳回底座 IP 位址或連接埠編號不包含在資料庫中，將位置資訊服務將無法傳回給用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="309dc-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

