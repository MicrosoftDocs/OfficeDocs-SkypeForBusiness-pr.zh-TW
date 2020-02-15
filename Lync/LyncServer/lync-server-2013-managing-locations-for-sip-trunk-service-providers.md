---
title: Lync Server 2013： 管理 SIP 主幹服務提供者的位置
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
ms.openlocfilehash: d2ffa9b16a2c582af2de990eab52b55c175121bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="e4c48-102">管理 Lync Server 2013 中的 SIP 主幹服務提供者的位置</span><span class="sxs-lookup"><span data-stu-id="e4c48-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4c48-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="e4c48-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e4c48-104">若要設定自動尋找網路內的用戶端的 Lync Server，您需要填入網路接線圖位置資訊服務資料庫及發佈的位置，或連結至已經包含正確的外部資料庫對應。</span><span class="sxs-lookup"><span data-stu-id="e4c48-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="e4c48-105">此程序的一部分，您需要驗證 E9-1-1 服務提供者那邊位置的市街地址。</span><span class="sxs-lookup"><span data-stu-id="e4c48-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="e4c48-106">如需詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的位置資料庫](lync-server-2013-configure-the-location-database.md)。</span><span class="sxs-lookup"><span data-stu-id="e4c48-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e4c48-107">您填入位置資訊服務資料庫與緊急回應位置 (ERL)，其中包括市街地址和建置內的特定地址。</span><span class="sxs-lookup"><span data-stu-id="e4c48-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="e4c48-108">位置資訊服務**位置**] 欄位中，也就是建置內的特定位置，具有長度上限為 20 個字元 （包括空格）。</span><span class="sxs-lookup"><span data-stu-id="e4c48-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="e4c48-109">在該限制的長度，嘗試包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="e4c48-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="e4c48-110">容易理解名稱，可識別 911 來電者可協助您確保的緊急回應者的特定位置迅速時找到它們都會送達市街地址的位置。</span><span class="sxs-lookup"><span data-stu-id="e4c48-110">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="e4c48-111">此位置名稱可能包含建築物編號、 底板數字、 蝶形指示項，會議室號碼等等。</span><span class="sxs-lookup"><span data-stu-id="e4c48-111">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="e4c48-112">避免只有知道可能會導致移至錯誤的位置的緊急回應者的員工的暱稱。</span><span class="sxs-lookup"><span data-stu-id="e4c48-112">Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="e4c48-113">協助使用者輕鬆地查看，挑選的正確位置其 Lync 用戶端位置識別碼。</span><span class="sxs-lookup"><span data-stu-id="e4c48-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="e4c48-114">Lync 用戶端會自動將串連，並顯示探索到的**位置**] 和 [**縣/市**欄位標頭中。</span><span class="sxs-lookup"><span data-stu-id="e4c48-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="e4c48-115">很好的作法是將建置的街道地址新增至每個位置識別碼 (例如，"1st Floor\<街道號碼\>」)。</span><span class="sxs-lookup"><span data-stu-id="e4c48-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="e4c48-116">街道地址，而 「 1st 樓 」 等的一般位置識別碼無法套用至任何建置在 [縣/市。</span><span class="sxs-lookup"><span data-stu-id="e4c48-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="e4c48-117">如果因為它由無線存取點決定的概略位置，您可以加入 near 的字詞 （例如 「 靠近 1st 樓 1234年）。</span><span class="sxs-lookup"><span data-stu-id="e4c48-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4c48-118">除非他們發佈使用 Lync Server 管理命令介面命令，並且會複寫到集區的本機存放區，並不適用於用戶端新增至中央位置資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="e4c48-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="e4c48-119">如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-publish-the-location-database.md">發佈位置資料庫從 Lync Server 2013</A> 。</span><span class="sxs-lookup"><span data-stu-id="e4c48-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="e4c48-120">下列各節將討論您需要考慮當填入和維護位置資料庫時的考量。</span><span class="sxs-lookup"><span data-stu-id="e4c48-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="e4c48-121">填入位置資料庫</span><span class="sxs-lookup"><span data-stu-id="e4c48-121">Populating the Location Database</span></span>

<span data-ttu-id="e4c48-122">下列問題可協助您決定如何填入位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="e4c48-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="e4c48-123">**您將使用何種程序填入位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="e4c48-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="e4c48-124">其中是否存在的資料，以及您需要將資料轉換成位置資料庫所需的格式採取哪些步驟？</span><span class="sxs-lookup"><span data-stu-id="e4c48-124">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="e4c48-125">將您新增位置會個別或大量使用 CSV 檔案？</span><span class="sxs-lookup"><span data-stu-id="e4c48-125">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="e4c48-126">**您必須已經包含位置對應的協力廠商資料庫？**</span><span class="sxs-lookup"><span data-stu-id="e4c48-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="e4c48-127">使用 Lync Server 的次要位置資訊服務] 選項，以連線至協力廠商資料庫，您可以群組，並使用離線平台管理位置。</span><span class="sxs-lookup"><span data-stu-id="e4c48-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="e4c48-128">這種方法的好處是，除了建立關聯至網路識別碼的位置，您可以建立關聯的使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="e4c48-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="e4c48-129">這表示位置資訊服務可以傳回多個地址，源自次要位置資訊服務，Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="e4c48-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="e4c48-130">然後，使用者可以選擇最適合的位置。</span><span class="sxs-lookup"><span data-stu-id="e4c48-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="e4c48-131">若要整合與位置資訊服務，協力廠商資料庫必須遵循 Lync 伺服器位置要求讀回應結構描述。</span><span class="sxs-lookup"><span data-stu-id="e4c48-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="e4c48-132">如需詳細資訊，請參閱 「\[MS E911WS\]: E911 支援通訊協定規格的 Web 服務 」 在<http://go.microsoft.com/fwlink/p/?linkid=213819>。</span><span class="sxs-lookup"><span data-stu-id="e4c48-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="e4c48-133">如需部署次要位置資訊服務的詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的次要位置資訊服務](lync-server-2013-configure-a-secondary-location-information-service.md)。</span><span class="sxs-lookup"><span data-stu-id="e4c48-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e4c48-134">如需填入位置資料庫的詳細資訊，請參閱部署文件中的[設定 Lync Server 2013 中的位置資料庫](lync-server-2013-configure-the-location-database.md)。</span><span class="sxs-lookup"><span data-stu-id="e4c48-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="e4c48-135">維護位置資料庫</span><span class="sxs-lookup"><span data-stu-id="e4c48-135">Maintaining the Location Database</span></span>

<span data-ttu-id="e4c48-136">填入位置資料庫之後，您需要開發更新資料庫作為網路組態變更的策略。</span><span class="sxs-lookup"><span data-stu-id="e4c48-136">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="e4c48-137">下列問題可協助您決定如何維護位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="e4c48-137">The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="e4c48-138">**您要如何更新位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="e4c48-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="e4c48-139">有幾種情況，需要更新至位置資料庫，包括新增 Wap、 office recabling （產生不同的參數指派），和子網路擴充。</span><span class="sxs-lookup"><span data-stu-id="e4c48-139">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="e4c48-140">將您直接更新每個個別的位置，或將使用 CSV 檔案來執行的所有位置大量更新？</span><span class="sxs-lookup"><span data-stu-id="e4c48-140">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="e4c48-141">**您將使用 SNMP 應用程式符合 Lync 用戶端 MAC 位址來連接埠和交換器識別碼？**</span><span class="sxs-lookup"><span data-stu-id="e4c48-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="e4c48-142">如果您使用 SNMP 應用程式，您需要開發將交換器底座和連接埠資訊保持一致 SNMP 應用程式和資料庫位置之間的手動程序。</span><span class="sxs-lookup"><span data-stu-id="e4c48-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="e4c48-143">如果 SNMP 應用程式傳回底座 IP 位址或連接埠編號不包含在資料庫中，將位置資訊服務將無法傳回給用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="e4c48-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

