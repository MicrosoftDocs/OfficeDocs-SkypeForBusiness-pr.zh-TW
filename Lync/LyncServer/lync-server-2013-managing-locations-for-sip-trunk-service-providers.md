---
title: Lync Server 2013：管理 SIP 中繼服務提供者的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ebc471459c8e406914f5a075d7e4cf8b69fadd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="c8c8f-102">在 Lync Server 2013 中管理 SIP 中繼服務提供者的位置</span><span class="sxs-lookup"><span data-stu-id="c8c8f-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8c8f-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c8c8f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c8c8f-104">若要將 Lync Server 設定為自動在網路中尋找用戶端，您必須使用網路 wiremap 填入位置資訊服務資料庫，然後發佈位置，或連結到已包含正確的外部資料庫映射.</span><span class="sxs-lookup"><span data-stu-id="c8c8f-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="c8c8f-105">作為此程式的一部分，您必須使用 E9-1 服務提供者驗證位置的市政位址。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="c8c8f-106">如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md)。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c8c8f-107">您可以使用緊急回應位置（ERL）來填入位置資訊服務資料庫，這是由市政位址以及建築物內的特定位址所組成。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="c8c8f-108">[位置資訊服務**位置**] 欄位是建築物內的特定位置，最大長度為20個字元（包括空格）。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="c8c8f-109">在該長度有限的範圍內，嘗試包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="c8c8f-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="c8c8f-110">識別911呼叫者位置的易於理解的名稱，可協助確保緊急回應程式在到達市政位址時能快速找到特定位置。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-110">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="c8c8f-111">這個位置名稱可以包含建築物編號、樓層編號、翼標示符、房間號碼等。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-111">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="c8c8f-112">避免只有員工知道別名，這可能會導致緊急回應程式移至錯誤的位置。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-112">Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="c8c8f-113">可協助使用者輕鬆查看其 Lync 用戶端是否已挑選正確位置的位置識別碼。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="c8c8f-114">Lync 用戶端會自動連接，並在其頁首中顯示 [已探索的**位置**] 和 [**城市**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="c8c8f-115">最好的做法是將建築物的街道位址新增至每個位置識別碼（例如，「第一層\<街道編號\>」）。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="c8c8f-116">如果沒有街道位址，一般位置識別碼（例如「第一層」）會套用至城市中的任何建築物。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="c8c8f-117">如果該位置是由無線存取點決定，您可以在附近新增該字（例如，「接近第一層1234」）。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8c8f-118">您必須先使用 Lync Server Management Shell 命令發佈並複製到該池的本機存儲區，才能讓客戶加入中央位置資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="c8c8f-119">如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-publish-the-location-database.md">從 Lync Server 2013 發佈位置資料庫</A>。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="c8c8f-120">下列各節討論當您填入及維護位置資料庫時需要考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="c8c8f-121">填充位置資料庫</span><span class="sxs-lookup"><span data-stu-id="c8c8f-121">Populating the Location Database</span></span>

<span data-ttu-id="c8c8f-122">下列問題可協助您決定如何填入位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="c8c8f-123">**您將使用哪個程式來填入位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="c8c8f-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="c8c8f-124">資料在哪裡存在，您需要採取哪些步驟才能將資料轉換成位置資料庫所需的格式？</span><span class="sxs-lookup"><span data-stu-id="c8c8f-124">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="c8c8f-125">您會使用 CSV 檔案個別地新增位置，還是大量新增位置？</span><span class="sxs-lookup"><span data-stu-id="c8c8f-125">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="c8c8f-126">**您是否有已包含位置對應的協力廠商資料庫？**</span><span class="sxs-lookup"><span data-stu-id="c8c8f-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="c8c8f-127">透過使用 Lync Server 的 [次要位置資訊服務] 選項來連線至協力廠商資料庫，您可以使用離線平臺來分組及管理位置。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="c8c8f-128">這種方法的優點是，除了將位置與網路識別碼相關聯之外，您還可以將位置與使用者建立關聯。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="c8c8f-129">這表示位置資訊服務可以傳回多個位址（源自次要位置資訊服務）至 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="c8c8f-130">然後，使用者可以選擇最適合的位置。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="c8c8f-131">若要整合位置資訊服務，協力廠商資料庫必須遵循 Lync Server 位置要求/回應架構。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="c8c8f-132">如需詳細資訊，\[請參閱「\]MS-E911WS：適用于 E911 的 Web 服務<http://go.microsoft.com/fwlink/p/?linkid=213819>支援通訊協定說明」。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="c8c8f-133">如需有關部署次要位置資訊服務的詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定次要位置資訊服務](lync-server-2013-configure-a-secondary-location-information-service.md)。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c8c8f-134">如需有關填充位置資料庫的詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md)。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="c8c8f-135">維護位置資料庫</span><span class="sxs-lookup"><span data-stu-id="c8c8f-135">Maintaining the Location Database</span></span>

<span data-ttu-id="c8c8f-136">在您填入 location 資料庫之後，您需要開發一個策略，在網路設定變更時更新資料庫。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-136">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="c8c8f-137">下列問題將協助您決定如何維護位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-137">The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="c8c8f-138">**如何更新位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="c8c8f-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="c8c8f-139">有幾種情況需要更新位置資料庫，包括新增 WAPs、office recabling （產生不同的切換作業），以及子網延伸。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-139">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="c8c8f-140">您是否會直接更新每個個別位置，或是使用 CSV 檔案執行所有位置的大量更新？</span><span class="sxs-lookup"><span data-stu-id="c8c8f-140">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="c8c8f-141">**您會使用 SNMP 應用程式，將 Lync 用戶端 MAC 位址與埠和交換器識別碼搭配使用嗎？**</span><span class="sxs-lookup"><span data-stu-id="c8c8f-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="c8c8f-142">如果您使用的是 SNMP 應用程式，您必須開發手動程式，以保持 SNMP 應用程式和位置資料庫之間的切換底盤和埠資訊一致。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="c8c8f-143">如果 SNMP 應用程式傳回的是不包含在資料庫中的主機殼 IP 位址或埠 ID，位置資訊服務將無法傳回用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="c8c8f-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

