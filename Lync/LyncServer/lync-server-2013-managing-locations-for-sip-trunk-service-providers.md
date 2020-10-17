---
title: Lync Server 2013：管理 SIP 主幹服務提供者的位置
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
ms.openlocfilehash: b6aa7dce34aea04c851608f67d1412c1c3da4069
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498170"
---
# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="78933-102">在 Lync Server 2013 中管理 SIP 主幹服務提供者的位置</span><span class="sxs-lookup"><span data-stu-id="78933-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78933-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="78933-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="78933-104">若要將 Lync Server 設定為自動在網路中尋找用戶端，您必須使用網路線路圖填入位置資訊服務資料庫，併發布位置，或連結至已經包含正確對應的外部資料庫。</span><span class="sxs-lookup"><span data-stu-id="78933-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="78933-105">在此程式中，您必須使用 E9-1-1 服務提供者驗證位置的市政位址。</span><span class="sxs-lookup"><span data-stu-id="78933-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="78933-106">如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md) 。</span><span class="sxs-lookup"><span data-stu-id="78933-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="78933-107">您可以使用 ERL) （包含市政位址及大樓內的特定位址） (的 [緊急回應] 位置，填入位置資訊服務資料庫。</span><span class="sxs-lookup"><span data-stu-id="78933-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="78933-108">位置資訊服務 **位置** 欄位是大樓內的特定位置，其最大長度為20個字元 (包含空格) 。</span><span class="sxs-lookup"><span data-stu-id="78933-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="78933-109">在此有限長度內，嘗試包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="78933-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="78933-110">易於辨識的名稱，可識別911呼叫者的位置，以協助確保緊急回應程式在到達市政位址時立即找到特定位置。</span><span class="sxs-lookup"><span data-stu-id="78933-110">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="78933-111">此位置名稱可以包含大樓編號、底價編號、翼標示符、會議室編號等等。</span><span class="sxs-lookup"><span data-stu-id="78933-111">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="78933-112">避免只有員工知道的昵稱，這可能會造成緊急回應程式進入錯誤的位置。</span><span class="sxs-lookup"><span data-stu-id="78933-112">Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="78933-113">一個位置識別碼，可協助使用者輕鬆查看其 Lync 用戶端是否已挑選正確的位置。</span><span class="sxs-lookup"><span data-stu-id="78933-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="78933-114">Lync 用戶端會自動連接並顯示其頁首中已探索的 **位置** 和 **城市** 欄位。</span><span class="sxs-lookup"><span data-stu-id="78933-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="78933-115">最佳作法是將大樓的街道位址新增至每個位置識別碼 (例如，"第一層 \<street number\> " ) 。</span><span class="sxs-lookup"><span data-stu-id="78933-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="78933-116">沒有街道位址，「第一層」等一般位置識別碼可以套用到城市中的任何辦公樓。</span><span class="sxs-lookup"><span data-stu-id="78933-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="78933-117">如果位置是由無線存取點所決定，您可以在 (附近新增文字，例如，「接近第一層1234」 ) 。</span><span class="sxs-lookup"><span data-stu-id="78933-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78933-118">新增至中央位置資料庫的位置直到使用 Lync Server 管理命令介面命令加以發佈，而且會複製到集區的本機存放區，才可供用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="78933-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="78933-119">如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-publish-the-location-database.md">從 Lync Server 2013 發佈位置資料庫</A> 。</span><span class="sxs-lookup"><span data-stu-id="78933-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="78933-120">下列各節討論在填充及維護位置資料庫時，需要考慮的考慮事項。</span><span class="sxs-lookup"><span data-stu-id="78933-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="78933-121">填充位置資料庫</span><span class="sxs-lookup"><span data-stu-id="78933-121">Populating the Location Database</span></span>

<span data-ttu-id="78933-122">下列問題可協助您決定如何填入位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="78933-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="78933-123">**您將使用哪個程式填入位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="78933-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="78933-124">資料存在的位置，以及您需要採取哪些步驟將資料轉換成位置資料庫所需的格式？</span><span class="sxs-lookup"><span data-stu-id="78933-124">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="78933-125">是否要使用 CSV 檔案個別新增位置，還是大量使用 CSV 檔案？</span><span class="sxs-lookup"><span data-stu-id="78933-125">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="78933-126">**您是否有已包含位置對應的協力廠商資料庫？**</span><span class="sxs-lookup"><span data-stu-id="78933-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="78933-127">使用 Lync Server 的次要位置資訊服務選項來連線至協力廠商資料庫，您可以使用離線平臺來分組和管理位置。</span><span class="sxs-lookup"><span data-stu-id="78933-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="78933-128">這種方法的好處是，除了將位置與網路識別碼相關聯之外，也可以將位置與使用者產生關聯。</span><span class="sxs-lookup"><span data-stu-id="78933-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="78933-129">這表示位置資訊服務可以傳回多個來自次要位置資訊服務的位址給 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="78933-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="78933-130">然後，使用者可以選擇最適合的位置。</span><span class="sxs-lookup"><span data-stu-id="78933-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="78933-131">若要與位置資訊服務整合，協力廠商資料庫必須遵循 Lync Server 位置要求/回應架構。</span><span class="sxs-lookup"><span data-stu-id="78933-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="78933-132">如需詳細資訊，請參閱中的「 \[ MS-E911WS \] ： E911 支援通訊協定規格的 Web 服務」 <https://go.microsoft.com/fwlink/p/?linkid=213819> 。</span><span class="sxs-lookup"><span data-stu-id="78933-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="78933-133">如需部署次要位置資訊服務的詳細資訊，請參閱部署檔中的 [Configure a 輔 Location information service In Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) 。</span><span class="sxs-lookup"><span data-stu-id="78933-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="78933-134">如需有關填充位置資料庫的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定位置資料庫](lync-server-2013-configure-the-location-database.md) 。</span><span class="sxs-lookup"><span data-stu-id="78933-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="78933-135">維護位置資料庫</span><span class="sxs-lookup"><span data-stu-id="78933-135">Maintaining the Location Database</span></span>

<span data-ttu-id="78933-136">填滿位置資料庫之後，您需要開發一個策略，以在網路設定變更時更新資料庫。</span><span class="sxs-lookup"><span data-stu-id="78933-136">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="78933-137">下列問題可協助您決定如何維護位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="78933-137">The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="78933-138">**您將如何更新位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="78933-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="78933-139">有幾個案例需要更新位置資料庫，包括新增 Wap、office recabling (產生不同的切換指派) 及子網擴充。</span><span class="sxs-lookup"><span data-stu-id="78933-139">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="78933-140">您是否會直接更新每個個別位置，或是使用 CSV 檔案執行所有位置的大量更新？</span><span class="sxs-lookup"><span data-stu-id="78933-140">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="78933-141">**您是否會使用 SNMP 應用程式，將 Lync 用戶端 MAC 位址與埠及切換識別碼對應？**</span><span class="sxs-lookup"><span data-stu-id="78933-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="78933-142">如果您使用 SNMP 應用程式，則必須開發手動程式，以在 SNMP 應用程式和位置資料庫之間保持切換底盤及埠資訊的一致性。</span><span class="sxs-lookup"><span data-stu-id="78933-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="78933-143">如果 SNMP 應用程式傳回資料庫中未包含的主機殼 IP 位址或埠識別碼，則位置資訊服務將無法傳回用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="78933-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

